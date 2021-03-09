Items API with Authentication and Unit tests using Laravel 5.3 and Angularjs for example test implementation of the API using the api_token authentication.

# Environment setup

edit mysql credentials and copy or rename .env.example to .env

edit accordingly config/database.php mysql credentials

write permissions necessary to be set eventually for directories

storage/

# Automatic Install Database

php artisian migrate

php artisan db:seed --class=UsersTableSeeder

# Manual Install Database

sample_database.sql 


# Angularjs auth config 
Angularjs module should be authentication and server request variables are loaded automatically as vars from the system in the home template

# PHP Unit Tests
Unit test use also api_token of some available users
If you use authomatic laravel seeding or sample database install, a change in tests/ApiTest.php api_token var will not be necessary, otherwise just update it with the api_token value of some of the new added users 


# Description 
- The Idea was to build sample Items API with authentication.

	List of the api resources:

	GET|HEAD  | api/v1/items             | items.index   | App\Http\Controllers\ItemController@index                            

	POST      | api/v1/items             | items.store   | App\Http\Controllers\ItemController@store                              

	GET|HEAD  | api/v1/items/create      | items.create  | App\Http\Controllers\ItemController@create                             

	GET|HEAD  | api/v1/items/{item}      | items.show    | App\Http\Controllers\ItemController@show                                

	PUT|PATCH | api/v1/items/{item}      | items.update  | App\Http\Controllers\ItemController@update                              

	DELETE    | api/v1/items/{item}      | items.destroy | App\Http\Controllers\ItemController@destroy                             

	GET|HEAD  | api/v1/items/{item}/edit | items.edit    | App\Http\Controllers\ItemController@edit   

- Login and register functionalities added with default Laravel tools for convinience
  	- login
    - register
    - forgotten password

- The home controller after login loads the API entries and manipulates them using the API resource 
	
- PHP Unit Tests added for testing the API future changes
	- Home page test - test/HomeTest.php
	- Register and Login tests - tests/RegistrationLoginTest.php
	- API tests - test/ApiTest.php

	In project's directory execute:

	phpunit