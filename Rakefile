desc "Serve the site locally on ENV['port'] (Default = 8000)"
task :serve do
  ENV['port'] ||= '8000'
  system "ruby -run -ehttpd . -p#{ENV['port']}"
end

desc "Start compass watcher to render SASS"
task :watch_sass do
  system "compass watch"
end
