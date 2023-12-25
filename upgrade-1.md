---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: false
  outline:
    visible: true
  pagination:
    visible: false
---

# Upgrade



The most difficult part is kicking-off, which usually very confusign and frustraiting. The following are quick start pilot books.

## For a brand new Rails app

1. Upgrade Ruby to the newest version, using brew on macOS.
2. Use RubyGems to upgrade Rails to the newes version, by runing ...
3. Install or start PostgreSQL database, using brew services to check its status or brew install postgresql@16 .





***

## To upgrade an existing Rails app with outdated gems or Rails

To upgrade an old Rails 7 application with outdated gems, you can follow these steps:

Before any action, use Git to set up a baseline for each upgrade step, therefore if something goes wrong, you can easily revert to a previous state.



**Step 1: Update the app's Bundler**

It's important to ensure update within the Rails app's directory, where your `Gemfile` is located, not in the home (`~`) directory.

1.  Install the specific version of Bundler required by your application. Use the command:

    ```
    gem install bundler -v 2.4.13
    ```
2.  **Use the Specific Bundler Version for Dependency Management:** After installing the required Bundler version, you can then run it specifically for your project:

    ```
    bundle _2.4.13_ install
    ```

    This command tells Bundler to use version 2.4.13 to manage your gems as specified in your `Gemfile`.

By performing these steps within your Rails application's directory, you ensure that the correct versions of your gems are installed and managed according to the application's dependencies and requirements.&#x20;

<mark style="background-color:red;">% 我认为，一般用最新版的 Bundler 就好。所以，要把 app 的 Gemfile 中的 bundler 版本改为跟系统一样的最新版本。 %</mark>

**Step 2: Update the app's Gems:**

* Start by updating your `Gemfile`. For each gem, specify the latest version compatible with Rails 7. You might need to check each gem's documentation or repository for compatibility information.
* Update your gems incrementally. Avoid updating all gems at once, as this can introduce multiple breaking changes that are hard to debug. Update one or a few gems at a time, then test your application to ensure it still works as expected.

1.  **Run Bundler:** Once you've updated your `Gemfile`, run:

    ```
    bundle update
    ```

    This will update your `Gemfile.lock` with the new versions.
2. **Test Your Application:** After updating the gems, thoroughly test your application to catch any breaking changes or deprecations. You might need to update your application code to be compatible with the new gem versions.
3. **Update Rails:** If you also need to update Rails, change the Rails version in your `Gemfile` and then run `bundle update rails`. Again, test your application extensively after this update.
4. **Resolve Dependencies Issues:** If you encounter any dependency issues, carefully read the error messages. They often provide clues on what needs to be resolved. You might need to update other dependencies or modify version constraints in your `Gemfile`.
5.
6. **Consult Documentation and Community:** For specific gems that are causing trouble, consult their documentation or community forums. Sometimes, there might be known issues with certain versions or additional steps required for upgrading.
7. **Consider a Step-by-Step Upgrade Guide:** If available, follow a step-by-step guide for upgrading Rails applications. These guides often provide specific instructions and best practices for a smooth upgrade process.
8. **Use a Continuous Integration (CI) System:** If you have a CI system, use it to run tests automatically. This will help you identify issues quickly as you upgrade.

Remember, upgrading a large application with many outdated dependencies can be a complex task. It's important to proceed methodically and test thoroughly at each step.

