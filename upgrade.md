# Upgrade



<mark style="background-color:orange;">**Step by step, and use version control!**</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">Use Git to track changes after each step.</mark>

Yes, you should perform these Bundler update steps within your Rails application's directory, not in the home (`~`) directory. This is important because Bundler needs to access the `Gemfile` and `Gemfile.lock` specific to your Rails application. Here's how you should do it:

## Verify the version of Rails used in an app

<mark style="background-color:orange;">Note that the terminal commands will work only when you are inside the Rails application directory, otherwise, it will display the latest installed version of Rails on your system.</mark> If the application is using a different version specified in the Gemfile, it may not be accurate.

1\. Via the Gemfile.lock: The Gemfile.lock in a Rails application specifies the exact versions of each gem that the application is using. Look for the line specifying the rails gem version in this file.

2\. Via the command line:cIn the terminal, navigate to the directory of your Rails app and use the command `rails -v` . This will display the current version of Rails the application is using.

3\. Via the Rails console: Another option is to open the Rails console with the command rails console or `rails c`, then print the Rails version with `Rails.version`.

***

## Upgrade the Rails version for a Rails app

Change the Rails version in the `Gemfile` of a Rails app, then run

```
bundle update rails
```

<mark style="background-color:red;">Some one said then run this command, I not sure yet.</mark>

```
bin/rails app:update
```



***

## Upgrade the Bundler version of a Rails app

It's important to ensure that the newer Bundler version is compatible with your Rails 7 app and other gem dependencies.&#x20;

<mark style="background-color:red;">% 其實我認為，一般就用最新版的 Bundler。20231221 %</mark>

1. If the `Gemfile` explicitly specifies a Bundler version (like `gem 'bundler', '~> 2.4.13'`), update this line to allow the newer version. You might want to specify a version range that includes the new version but is still compatible with your app.
2.  Install the latest stable release of Bundler, or install a specific version:

    ```
    gem install bundler
    gem install bundler -v 2.4.13
    ```
3.  **Go to your Rails application's root directory to update Gemfile.lock.**

    ```bash
    bundle update --bundler
    ```

    This command updates the `BUNDLED WITH` section in your app's `Gemfile.lock` to the new Bundler version.
4.  After installing the required Bundler version, you can then run it specifically for your project. This command tells Bundler to use version 2.4.13 to manage your gems as specified in your `Gemfile`.

    ```bash
    bundle _2.4.13_ install
    ```

***

## Upgrade the gems of a Rails app&#x20;

1. Start by updating your `Gemfile`. For each gem, specify the latest version compatible with Rails 7. You might need to check each gem's documentation or repository for compatibility information.\
   <mark style="background-color:orange;">Update  gems incrementally. Avoid updating all gems at once</mark>, as this can introduce multiple breaking changes that are hard to debug. <mark style="background-color:orange;">Update one or a few gems at a time</mark>, then test your application to ensure it still works as expected.
2.  Once you've updated your `Gemfile`,  to update your `Gemfile.lock` with the new versions.

    ```sql
    bundle update
    ```


3.  To ensure all gems are installed correctly with the new Bundler version. This step will install the necessary gems based on your updated `Gemfile.lock`.

    ```bash
    bundle install
    ```

***

## Upgrade OS Ruby to the newest version

To upgrade Ruby on macOS using Homebrew:

1.  **Update Homebrew** to make sure you have the latest formulae for Ruby.&#x20;

    ```bash
    brew update
    ```
2.  **U**pgrade Ruby to the latest version available in Homebrew:

    ```bash
    brew upgrade ruby // or 
    brew upgrade ruby@3.3.0
    ```

## Upgrade Rails and all gems on macOS to the newest version

```
gem update // or
gem update rails
```
