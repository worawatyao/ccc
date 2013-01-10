require 'bundler/capistrano'

role :deployer, "admin@hivitamin.com"
set :current_time, Time.new().strftime("%Y-%m-%d_%H-%M")

task :ls do
    run "ls -l"
end

namespace :ccc do

    desc "deploy"
    task :deploy do
        run "cd webapps/ccc; git pull"
        run "cd webapps/ccc; bundle exec rake assets:precompile"
	restart
    end



    desc "restart Apache"
    task :restart do
        run "touch webapps/ccc/tmp/restart.txt"
    end
end

