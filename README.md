An example of `ruby_speech` on Heroku Cedar-10. You don't need to do this for Cedar-14 because it already has the dependencies.

```
$ git push heroku master
Counting objects: 6, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 416 bytes | 0 bytes/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote: 
remote: -----> Fetching custom git buildpack... done
remote: -----> Multipack app detected
remote: =====> Downloading Buildpack: https://github.com/ddollar/heroku-buildpack-apt.git
remote: =====> Detected Framework: Apt
remote: -----> Updating apt caches
remote:        Get:1 http://apt.postgresql.org lucid-pgdg Release.gpg [836B]
remote:        Ign http://apt.postgresql.org/pub/repos/apt/ lucid-pgdg/9.2 Translation-en_US
remote:        Get:2 http://apt.postgresql.org lucid-pgdg Release [29.3kB]
remote:        Get:3 http://archive.ubuntu.com lucid Release.gpg [189B]
remote:        Ign http://archive.ubuntu.com/ubuntu/ lucid/main Translation-en_US
remote:        Ign http://archive.ubuntu.com/ubuntu/ lucid/universe Translation-en_US
remote:        Get:4 http://archive.ubuntu.com lucid-security Release.gpg [198B]
remote:        Ign http://archive.ubuntu.com/ubuntu/ lucid-security/main Translation-en_US
remote:        Get:5 http://archive.ubuntu.com lucid-updates Release.gpg [198B]
remote:        Ign http://archive.ubuntu.com/ubuntu/ lucid-updates/main Translation-en_US
remote:        Ign http://apt.postgresql.org lucid-pgdg Release
remote:        Get:6 http://archive.ubuntu.com lucid Release [57.2kB]
remote:        Get:7 http://apt.postgresql.org lucid-pgdg/9.2 Packages [1,866B]
remote:        Get:8 http://archive.ubuntu.com lucid-security Release [58.7kB]
remote:        Get:9 http://archive.ubuntu.com lucid-updates Release [185kB]
remote:        Get:10 http://archive.ubuntu.com lucid/main Packages [1,383kB]
remote:        Get:11 http://archive.ubuntu.com lucid/universe Packages [5,430kB]
remote:        Get:12 http://archive.ubuntu.com lucid-security/main Packages [624kB]
remote:        Get:13 http://archive.ubuntu.com lucid-updates/main Packages [809kB]
remote:        Fetched 8,580kB in 3s (2,435kB/s)
remote:        Reading package lists...
remote: -----> Fetching .debs for libpcre3-dev
remote:        Reading package lists...
remote:        Building dependency tree...
remote:        The following extra packages will be installed:
remote:          libpcrecpp0
remote:        The following NEW packages will be installed:
remote:          libpcre3-dev libpcrecpp0
remote:        0 upgraded, 2 newly installed, 0 to remove and 20 not upgraded.
remote:        Need to get 362kB of archives.
remote:        After this operation, 905kB of additional disk space will be used.
remote:        Get:1 http://archive.ubuntu.com/ubuntu/ lucid/main libpcrecpp0 7.8-3build1 [98.2kB]
remote:        Get:2 http://archive.ubuntu.com/ubuntu/ lucid/main libpcre3-dev 7.8-3build1 [264kB]
remote:        Fetched 362kB in 0s (3,913kB/s)
remote:        Download complete and in download only mode
remote: -----> Installing libpcre3-dev_7.8-3build1_amd64.deb
remote: -----> Installing libpcrecpp0_7.8-3build1_amd64.deb
remote: -----> Writing profile script
remote: =====> Downloading Buildpack: https://github.com/heroku/heroku-buildpack-ruby.git
remote: =====> Detected Framework: Ruby
remote: -----> Compiling Ruby
remote: -----> Using Ruby version: ruby-2.0.0
remote: -----> Installing dependencies using 1.7.12
remote:        Purging Cache. Changing stack from cedar-14 to cedar
remote:        Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin -j4 --deployment
remote:        Fetching gem metadata from https://rubygems.org/.........
remote:        Installing minitest 5.6.0
remote:        Installing i18n 0.7.0
remote:        Installing mini_portile 0.6.2
remote:        Using bundler 1.7.12
remote:        Installing thread_safe 0.3.5
remote:        Installing tzinfo 1.2.2
remote:        Installing json 1.8.2
remote:        Installing activesupport 4.2.1
remote:        Installing nokogiri 1.6.6.2
remote:        Installing ruby_speech 2.3.2
remote:        Your bundle is complete!
remote:        Gems in the groups development and test were not installed.
remote:        It was installed into ./vendor/bundle
remote:        Bundle completed (15.92s)
remote:        Cleaning up the bundler cache.
remote: 
remote: ###### WARNING:
remote:        You have not declared a Ruby version in your Gemfile.
remote:        To set your Ruby version add this line to your Gemfile:
remote:        ruby '2.0.0'
remote:        # See https://devcenter.heroku.com/articles/ruby-versions for more information.
remote: 
remote: ###### WARNING:
remote:        No Procfile detected, using the default web server (webrick)
remote:        https://devcenter.heroku.com/articles/ruby-default-web-server
remote: 
remote: Using release configuration from last framework (Ruby).
remote: -----> Discovering process types
remote:        Procfile declares types     -> (none)
remote:        Default types for Multipack -> console, rake
remote: 
remote: -----> Compressing... done, 14.1MB
remote: -----> Launching... done, v6
remote:        https://enigmatic-cove-7991.herokuapp.com/ deployed to Heroku
remote: 
remote:  !   Cedar-10 will reach end-of-life on November 4th, 2015.
remote:  !   Upgrade to Cedar-14 at your earliest convenience.
remote:  !   For more information, check out the following Dev Center article:
remote:  !   https://devcenter.heroku.com/articles/cedar-14-migration
remote: 
remote: Verifying deploy... done.
```

```
$ heroku run bash
Running `bash` attached to terminal... up, run.9367
~ $ irb
irb(main):001:0> require 'ruby_speech'
=> true
irb(main):002:0> RubySpeech::VERSION
=> "2.3.2"
```
