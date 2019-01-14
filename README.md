### Personal page. Visit anilcelik.io for live version.

## To Run locally:

* Install ruby
```
sudo apt install ruby-full
```
* Install bundler
```
gem install bundler
```
* Install gem packages
```
bundle install
```
* If nokogiri package throws off an error(Better if you do this step before 'bundle install')
```
sudo apt install build-essential patch ruby-dev zlib1g-dev liblzma-dev
```
* Build the site
```
jekyll build
```
* Run it on localhost
```
jekyll serve
```
* Open website with localhost:4000
