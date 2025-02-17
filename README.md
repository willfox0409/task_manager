# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# Check For Understanding

1. Define CRUD.

- C stands for Create. It adds new data to the database e.g. POST request in API
- R stands for Read. It retrieves existing data e.g. GET request to fetch (read) records
- U stands for Update. It modifies existing data e.g. PATCH or PUT request to edit existing data.
- D stands for Delete. Removes data from the database e.g. DELETE request.

These are the four fundamental operations for managing data in an application. In our case we are using Postman, which is a tool for making API requests, simulating how a frontend or other service would interact with our Rails backend. It helps you test your API endpoints by sending POST, GET, PATCH and DELETE requests to your rails app. Rails, which is the application manager, uses ActiveRecord to manipulate data in the database based on the requests received. 

	- Postman = API request simulator
	- Rails = Application manager
	- PostgreSQL (or another DB) = Data storage 

2. Define MVC.

MVC stands for Model-View-Controller. It is a design pattern that separates an application into three interconnected components. Model manages the data and business logic, interacts with the database. View handles what the user sees (renders UI or JSON responses). Controller acts as the middleman, processing requests, fetching/updating data via the Model and sending responses via the View. Rails uses the MVC design pattern by default to implement the CRUD actions for in our case, the Task Manager app.


3. What two files would you need to create/modify for a Rails application to respond to a GET request to /api/v1/tasks, assuming you have a Task model.

To make Rails respond to a GET request to /api/v1/tasks, you need to modify two files:
- config/routes.rb – This file defines the URL path and connects it to the correct controller action.
- app/controllers/api/v1/tasks_controller.rb – This file contains the logic for handling the request and returning the data (in this case, all tasks as JSON).

4. What are params? Where do they come from?

Params is short for “parameters”. They are data sent with an HTTP request that Rails can access and use in controller actions. They come from different sources, such as:
- Query strings (e.g., ?id=1 in GET /tasks?id=1)
- Route segments (e.g., :id in GET /tasks/:id)
- Request bodies (e.g., JSON data sent in a POST or PATCH request)

In Rails, params are stored in the params hash and accessed like params[:id] or params[:task].

5. What is the purpose of a serializer?

A serializer in Rails formats model data into JSON for API responses, ensuring only relevant attributes are returned. It helps structure and clean up the data before sending it to the frontend. In our case, the serializer removed the timestamps (created_at and updated_at) to simplify the JSON response and only include relevant task attributes.