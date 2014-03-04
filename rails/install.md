1. update 
	sudo apt-get update 
2. install lib packages 
	sudo apt-get install  g++ curl libssl-dev apache2-utils git-core ia32-libs libmysqlclient-dev git 
	2.1  config git 
		ssh-keygen -t rsa -C 'your_email'
		cat ~/.ssh/id_rsa.pub
		add ssh key 
	    check 
		sh -T git@github.com
 
3. re do 1
4.install nodejs 
	git@github.com:joyent/node.git
5.install rvm 
	curl -L get.rvm.io | bash -s stable
6.source rvm 
	echo "source ~/.bashrc" >>  ~/.bash_profile  
	echo "source ~/.rvm/scripts/rvm" >> ~/.bashrc
	source ~/.bashrc
   check if success 
	rvm -v 
7. install ruby
	rvm install [2.0.0-p247]
	ruby -v 
	rvm use 2.0.0 --default
	which ruby 
8. install rails 
	gem install rails  --version 4.0.0 --no-ri --no-rdoc   
	rails -v 
	which rails 

9. gem install passenger 
	rvmsudo passenger-install-nginx-module  

10 config nginx 
	git clone git@github.com:aiyuelian/railsStartShell.git  
	sudo cp /path/to/nginx /etc/init.d/  
	sudo chmod +x /etc/init.d/nginx
	sudo update-rc.d nginx defaults

	server {
	   	listen 你的端口号;
   		server_name www.yourhost.com;
  		root /home/railsu/project/public;   # <--- 这里是你项目的public目录
  		passenger_enabled on;
   		rails_env production;
	}

	clone your project 
	sudo /etc/init.d/nginx start 







