require 'pathname'
require 'bourbon/generator'
require 'neat/generator'

namespace :update do
  task :bourbon do
    Dir.chdir '_sass' do
      puts "Updating Bourbon in #{Dir.pwd}"
      Bourbon::Generator.new.update
    end
  end

  task :neat do
    Dir.chdir '_sass' do
      puts "Updating Neat in #{Dir.pwd}"
      Neat::Generator.new(['update']).run
    end
  end
end

desc "Serve the site locally on ENV['port'] (Default = 8000)"
task :serve do
  ENV['port'] ||= '8000'
  system "ruby -run -ehttpd . -p#{ENV['port']}"
end

desc "Start compass watcher to render SASS"
task :watch_sass do
  system "compass watch"
end

task :deploy do
  puts "=== Running Compass"
  system 'compass compile -e production'
  puts "=== Pushing Changes"
  system 'git push'
end
