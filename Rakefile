begin
  require File.dirname(__FILE__) + "/init"

  desc "Create the Integrity database"
  task :db do
    DataMapper.auto_migrate!
  end
rescue Exception => e
  puts "Can't initialize app.  #{e.class.to_s}: #{e.message}"
end

desc "Deploy to all 3 heroku apps"
task :deploy do
  def deploy(branch, version)
     sh "git push #{version} #{branch}:master"
  end

  deploy("186", "186")
  deploy("master", "187")
  deploy("master", "191")
end

desc "Run a heroku command against all 3 heroku apps"
task :heroku do
  %w( 186 187 191 ).each do |ruby_version|
    sh "heroku #{ENV['COMMAND']} --app integrity#{ruby_version}"
  end
end