begin
  require File.dirname(__FILE__) + "/init"

  desc "Create the Integrity database"
  task :db do
    DataMapper.auto_migrate!
  end
rescue Exception => e
  puts "Can't initialize app.  #{e.class.to_s}: #{e.message}"
end

task :deploy do
  %w( 186 187 191 ).each do |ruby_version|
    sh "git push #{ruby_version} master"
  end
end

task :heroku do
  %w( 186 187 191 ).each do |ruby_version|
    sh "heroku #{ENV['COMMAND']} --app integrity#{ruby_version}"
  end
end