# Rails Structure

## Rails in one sentence

Rails is a development framework for creating <mark style="background-color:orange;">database-backed web applications</mark> according to the MVC pattern.

## MVC

<mark style="background-color:yellow;">% The Model handles business logic, the Controller handles application logic and the View handles presentation logic.</mark> %

<mark style="background-color:yellow;">% Controllers 負責生成並發回 HTTP Response，這個 HTTP Response  的內容主體（body）是一個HTML（或JSON等），而這個HTML是基於把某個template填充數據來完成的——被稱為 render。這些數據的填充是由Controller action決定的。Action中命令會操控某些Model進而訪問數據庫來準備好數據。20231219 %</mark>

### Model layer

The _**Model layer**_ represents the domain model (such as Account, Product, Person, Post, etc.) and encapsulates the business logic specific to your application.&#x20;

In Rails, <mark style="background-color:orange;">database-backed model classes</mark> are derived from `ActiveRecord::Base`. Active Record allows you to present the data from database rows as objects and embellish these data objects with business logic methods.&#x20;

Although most Rails models are backed by a database, models can also be ordinary Ruby classes, or Ruby classes that implement a set of interfaces as provided by the Active Model module.

### View layer

The _**View layer**_ is composed of "templates" that are responsible for providing appropriate representations of your application's resources. Templates can come in a variety of formats, but most view templates are HTML with embedded Ruby code (ERB files). Views are typically <mark style="background-color:orange;">rendered to generate a controller response</mark> . In Rails, View generation is handled by Action View.

### Controller layer

<mark style="background-color:orange;">The Controller works at a higher level, processing the HTTP requests and preparing the HTTP responses.</mark>

The _**Controller layer**_ is responsible for handling incoming HTTP requests and providing a suitable response. Usually, this means returning HTML. Controllers load and manipulate models, and render view templates in order to generate the appropriate HTTP response.&#x20;

In Rails, incoming requests are routed by Action Dispatch to an appropriate controller, and controller classes are derived from `ActionController::Base`.&#x20;

## Other Frameworks and libraries

Rails also comes with:

* Action Mailer, a library to generate and send emails
* Action Mailbox, a library to receive emails within a Rails application
* Active Job, a framework for declaring jobs and making them run on a variety of queuing backends
* Action Cable, a framework to integrate WebSockets with a Rails application
* Active Storage, a library to attach cloud and local files to Rails applications
* Action Text, a library to handle rich text content
* Active Support, a collection of utility classes and standard library extensions that are useful for Rails, and may also be used independently outside Rails

The model represents the '**state**' of the application.

The View presents the model data to the users and also enables them to modify the data. The View does not use the data from Model directly, but through the Controller, namely <mark style="background-color:orange;">the View has not direct connection with the Model.</mark>

The Controller is the bridge between the Model and the View and is responsible for application logic. It handles the user's input and interactions and updates the model and view accordingly.

In the Model-View-Controller (MVC) architecture, the View does not directly communicate with the Model. Instead, the Controller serves as the intermediary: Controller receives user input and makes calls to the Model.&#x20;

Model performs the business logic (like data manipulations or database interactions) and returns the results to the Controller. <mark style="background-color:orange;">Controller takes the data from the Model and decides how to present it</mark>, which is often by passing it to a View. View then uses this data to render the appropriate user interface.

<mark style="background-color:orange;">The View just renders the HTML, but does not "send" HTML back to the Browser.</mark>

The Controller then takes this rendered HTML from the View and sends it back as a response to the client (browser).



Here's a simplified version of how this flow generally works in a framework like Rails:

* The browser sends an HTTP request to the application.
* <mark style="background-color:orange;">The router within the application decides which controller should handle the request,</mark> based on the routing rules defined in the application.
* The controller receives the request and based on the request, might interact with a Model (which communicates with a database) to retrieve or manipulate data.
* The controller then passes this data to the View.
* The View uses this data the View might need to render the HTML.
* The HTML from the View is sent back to the Controller, which then includes it in an HTTP response. This HTTP response is sent back to the client by the web server.



***

**WHL: Who decides whether an interaction with the database is needed, the Controller or the Model?**

ChatGPT: <mark style="background-color:orange;">The Controller decides when an interaction with the database is necessary based on the business logic of the application.</mark>

When a request comes into the application, the Controller is the component that first handles the request. It then determines what needs to be done to satisfy that request.

If the Controller determines that data needs to be fetched, created, updated, or deleted from the database, it will interact with the appropriate Model to do so. The Model is responsible for handling the actual interaction with the database, but it's the Controller that initiates the process.

The Controller will then take the data returned by the Model (if any), and pass it to the View.&#x20;

In this way, the Controller acts as a kind of director, deciding when and how the other components of the application should do their work. The Model and the View, meanwhile, focus on their specific responsibilities: interacting with the database and generating HTML, respectively.

## Routes

Routes' primary purpose is to connect view to controller, and they also serve as a UI element--URL.

Rules:

* Always use canonical routes that conform to Rails’ defaults.
* Avoid custom actions in favor of creating new resources that use Rails’\
  default actions.
* User-friendly URLs should be added in addition to the canonical routes.

<mark style="background-color:orange;">Using resources to define routes:</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">`resources :widgets`</mark><mark style="background-color:orange;">. It's the best way.</mark>

`bin/rails routes -g widgets`

If the app’s routes are made up entirely of calls to resources, it becomes easy to understand the app at a high level.
