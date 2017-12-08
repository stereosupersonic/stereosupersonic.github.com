---
layout: post
title: Migrate a Rails Application from ruby 1.9.3 to ruby 2.2
---

{{ page.title }}
================

As first step to migrate all Rails 3 application to 5.1, we moved
from ruby 1.9.3 to ruby 2.2.

## Problems

1. YAML serializer was moved from Syck to Psych. There are some issues with utf-8 encodings.

script to migrate to Psych:
  
  ```
  require "ruby-progressbar"
  require "syck"

  def yaml_field_to_psych(model, field)
    id = model.id
    sql = "Select #{field} from #{model.class.table_name} where id = #{id}"
    result = ActiveRecord::Base.connection.execute(sql)

    yaml = result.first.first
    if yaml.present?
      syck_yaml = Syck.load(yaml)
      psych_yaml = Psych.dump(syck_yaml)
      ActiveRecord::Base.connection.execute("update #{model.class.table_name} set #{field}= #{ActiveRecord::Base.sanitize(psych_yaml)} where id = #{id}")
      true
    else
      false
    end
  rescue => e
    puts "Error: #{e} in #{model.class.name} field:#{field} id:#{id}"
  end

  puts "start fixing yaml fields"
  fixed = 0
  total = 0

  cnt = MyModel.count
  total += cnt
  progress_bar = ProgressBar.create(title: "fix MyModel", total: cnt, format: "%t %c/%C: |%B| %E")
  MyModel.find_each do |obj|
    fixed += 1 if yaml_field_to_psych(obj, :my_yaml_field)
    progress_bar.increment
  end

  puts "fixed:#{fixed}/#{total}"
  ```

2. ```iconv``` must be added to the Gemfile

3. ```test-unit```  must be added to the Gemfile

4. with ruby2.2 you get warnings when you have duplicate keys in a Hash

## Improvments

* the Application uses only have of the memory that leads to a overall performance
