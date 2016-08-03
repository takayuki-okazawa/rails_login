# rails_login

### Version
```bash
$ ruby -v
ruby 2.2.4p230 (2015-12-16 revision 53155) [x86_64-linux-gnu]

$ rails -v
Warning: Running `gem pristine --all` to regenerate your installed gemspecs (and deleting then reinstalling your bundle if you use bundle --path) will improve the startup performance of Spring.
Rails 4.2.6

$ mongo -version
MongoDB shell version: 3.2.1
```

### Step
1. Install 'MongoDB' and Setting
2. Install 'device' and Setting
3. Create Model and Controller
4. Edit Controller
5. Let's Test!

## 1. Setting MongoDB of Rails

Add GemFile(Gemfile)
```
gem 'mongoid'
```

Create Config File(config/mongoid.yml)
```
$ rails g mongoid:config
```

## 2. Add Gem and Setting

Add GemFile(Gemfile)
```
gem 'devise'
```

Install
```
bundle install
```

Create Config File(config/initializers/devise.rb)
```
$ rails g devise:install
```

## 3. Create Controller

Create Model(app/models/user.rb)
```
rails generate devise User
```

Create Controller(app/controllers/home_controller.rb)
```
rails g controller home index authentication
```

Edit Controller(app/controllers/home_controller.rb)
```
classs HomeController < ApplicationController
  before_action :authenticate_user!,only: :authentication
  def index
```

Edit Controller(app/controllers/home_controller.rb)
```
before_action :authenticate_user!,only: :authentication
```

## 5. Let's Test!

Start Rails
```
$ sudo rails s -b 0.0.0.0
```

1. Access URL(192.168.33.10 -> YOUR_HOST)  
http://192.168.33.10:3000/home/authentication

2. Can't viwe URL -> Redirect  
http://192.168.33.10:3000/users/sign_up

3. Input Form and Sign up  

4. Re Access URL  
http://192.168.33.10:3000/home/authentication
