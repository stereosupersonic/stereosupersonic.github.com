desc "Start the server"
task :start_server do
 %x{ open http://localhost:4000 }
 %x{ jekyll serve --watch }
end

GH_PAGES_DIR = "stereosupersonic.github.com"

desc "Build Jekyll site and copy files"
task :build do
  system "jekyll build"
  system "rm -r ../#{GH_PAGES_DIR}/*" unless Dir['../#{GH_PAGES_DIR}/*'].empty?
  system "cp -R _site/* ../#{GH_PAGES_DIR}/"
  system "touch  ../#{GH_PAGES_DIR}/.nojekyll"
end

namespace :post do

  desc "new blog post"
  task :new do
     #
  end
end
