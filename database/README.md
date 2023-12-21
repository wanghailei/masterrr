# Database

## Using the same database for all environments.

It's generally not recommended to use different databases for development and production in a Rails app. Something that works in SQLite may not work in PostgreSQL and vice versa. Using different databases can expose your app to potential database-specific bugs only in production.

## Setup and Reset the Database

The `rails db:setup` command will create the database, load the schema, and initialise it with the seed data.

The `rails db:reset` command will drop the database and set it up again. This is functionally equivalent to `rails db:drop db:setup`.

## `ActiveRecord::NoDatabaseError`

在T003實驗中，rails new 和 bundle install 之後，rails sever，會收到這個錯誤信息。因為，我沒有創建 PostgreSQL數據庫。

```ruby
We could not find your database: tiny2_development. 
Which can be found in the database configuration file located at config/database.yml.
```

點擊網頁上的一個按鈕就可以了 "Create database"。

並且，有一個提示：To create your database, run: `bin/rails db:create`

我做了T003實驗，在完成T002實驗的步驟後，我運行了 `bin/rails db:create`。此時再 `bin/rails server`，網頁運行正常。



