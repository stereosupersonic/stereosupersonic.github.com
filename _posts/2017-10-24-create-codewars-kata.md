---
layout: post
title: Codewars Katas
---

{{ page.title }}
================


# Codewars Katas

Sometimes I challenge my self and try one of the code katas from [coderwars](http://www.codewars.com/). I'll try to finish it within one [pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique) means 25 minutes. The setup on my local machine looks like this:

* go to my katas dir and create a new folder

* inside the folder, i create one lib and one spec folder

* add a *README.md* with the link to the kata

```
# Two old ages

http://www.codewars.com/kata/two-oldest-ages-1/train/ruby
```

* add a Gemfile:

```
source 'http://rubygems.org'

gem "guard-rspec"
```

* then init the project

```
bundle install
guard init
```

* create a function class under ```lib/```

```
class TwoOldAges
  def self.call(numbers)
    Array(numbers).sort.last(2)
  end
end
```

* and spec inside ```spec/```

```
require_relative '../lib/two_old_ages'

RSpec.describe "TwoOldAges" do

  it "test something" do
    expect(TwoOldAges.call([1,5])).to eq([1,5])
  end

  ....
end

```

* start Guard with ```bundle exec guard```

## Hapy Hacking!!!
