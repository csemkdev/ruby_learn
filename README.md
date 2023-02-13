# Ruby Learn

## Ruby on Rails basic installation & setup
### Installing Ruby
-----Step 1-----
> sudo apt install curl

> curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

> curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

> echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list


> sudo apt-get update

> sudo apt-get install git-core zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn


-----Step 2-----
-----rbenv installation-----

> git clone https://github.com/rbenv/rbenv.git ~/.rbenv

> echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc

> echo 'eval "$(rbenv init -)"' >> ~/.bashrc

> exec $SHELL


> git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

> echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc

> exec $SHELL


> rbenv install 3.0.1

> rbenv global 3.0.1

> ruby -v



-----Step 3-----
-----Install bundler-----

> gem install bundler
Error: `mkdir': Permission denied @ dir_s_mkdir - /home/mlpl/.gem/specs (Errno::EACCES) ERROR:  While executing gem ... (Errno::EACCES)
Fix: To resolve use sudo gem install bundler


-----Step 4-----
-----Installing Rails-----
Problems faces and their fixes are also mentioned below

> sudo gem install rails -v 6.1.7

Error: Error installing rails:
	ERROR: Failed to build gem native extension.
current directory: /var/lib/gems/2.5.0/gems/nokogiri-1.10.10/ext/nokogiri
/usr/bin/ruby2.5 -r ./siteconf20201103-8654-1qa2ptr.rb extconf.rb
mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h

extconf failed, exit code 1

Gem files will remain installed in /var/lib/gems/2.5.0/gems/nokogiri-1.10.10 for inspection.

Tried:
> which rails

> gem list | grep rails

> sudo gem install nokogiri (giving same error)

Fix:

> sudo apt-get install build-essential patch ruby-dev zlib1g-dev liblzma-dev

> sudo gem install nokogiri


> sudo gem install rails -v 6.1.7

> rbenv rehash

> rails -v

Error: can't find gem railties (>= 0.a) with executable rails (Gem::GemNotFoundException)
Tried:

> sudo gem update (still getting same error)

Fix:

> rvm cleanup all

> rvm reset

> rails -v



-----Step 5-----
-----Set up postgresql-----

> sudo apt install postgresql-11 libpq-dev

Error: Unable to locate package postgresql-11

Fix:

> sudo apt install postgresql postgresql-contrib

> sudo apt-get install postgresql-client


> sudo -i -u postgres

\q (to exit)

psql -V


> sudo -u postgres psql
