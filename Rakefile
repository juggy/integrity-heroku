require File.dirname(__FILE__) + "/init"

desc "Create the Integrity database"
task :db do
  DataMapper.auto_migrate!
end

task :deploy do
  %w( 186 187 191 ).each do |ruby_version|
    sh "git push #{ruby_version} master"
  end
end