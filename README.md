# Boiler Plate For Rails 4.2

## Before you start

1. Rename Application

config/application.rb

    module BoilerPlate # <= Rename
      class Application < Rails::Application
      # ...

config/initializers/session_store.rb

    Rails.application.config.session_store :cookie_store, key: '_boiler_plate_session' # <= Rename


/home/webonise/sample/boiler-plate-4.2/app/views/layouts/application.html.erb

    <!DOCTYPE html>
    <html>
      <head>
        <title>BoilerPlate</title> <!-- Rename -->
        <!-- ... -->

## Add database.yml, secrets.yml

Copy the contents of `database.example.yml` to `database.yml`.
Uncomment the required configuration as per the database requirement.

Copy the contents of `secrets.example.yml` to `secrets.yml`
Generate new secrets with `rake secret` and replace with the old ones.

    rake secret

## HAML Support

In case you want HAML uncomment the following lines in `Gemfile`

    # ...
    gem 'haml'
    # ...
    group :development do
      # ...
      gem 'erb2haml'
      # ...
    end
    # ...

Execute the following tasks to convert or replace all .erb files.

    rake haml:replace_erbs # Delete the original .erb files
    rake haml:convert_erbs # Keep the original .erb files

Additional gems you may want to add

    group :development, :test do
      gem 'awesome_print'
      # ...
    end

    group :test do
      gem 'factory_bot_rails'
      gem 'faker'
      # ...
    end

    group :development do
      gem 'annotate'
      gem 'bullet'
      gem 'erb2haml'
      gem 'xray-rails'
    end

## Change the ruby-version you want to use and the gemset

    # .ruby-version
    2.3.3

    # .ruby-gemset
    default

## bundle

    bundle install

*Welcome to Rails :+1: *
