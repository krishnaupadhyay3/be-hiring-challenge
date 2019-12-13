# Backend API Hiring Challenge

# Introduction

Datapane is an API-driven product that provides client libraries / commandline applications that talk to an API server to handle and process datasets.

This challenge involves building a small API server and corresponding command-line client, both in Python, that allow uploading and processing CSV files, such as those included in the repo.


# Task

For this task we'll be building a very simple Python 3-based REST API server and command-line client. 

You may use any Python libraries and technologies of your choice, for instance Django, Flask, Starlette, etc, to build the API server (internally we use Django/DRF so recommend that).

## API Server

The API server should have a single root endpoint, `/dataset/`, that allows list and CRUD operations over a dataset object via the following API / HTTP verbs:

 - `GET /datasets/` - list the uploaded datasets
 - `POST /datasets/` - creates a dataset. This endpoint takes a CSV file as input, and stores it somewhere/how on the server as a pandas dataframe. A reference to this created object is returned by the endpoint, for instance an `id` or `url`.
 - `GET /datasets/<id>/` - return the file name, and size of the dataset object
 - `DELETE /datasets/<id>/` - delete the dataset object
 - `GET /datasets/<id>/excel/` - export the dataset as an excel file
 - `GET /datasets/<id>/stats/` - return the the stats generated by running `df.describe()` on the pandas dataframe as a json object
 - `GET /datasets/<id>/plot/` - generate and return a PDF containing a list of histograms of all the numerical columns in the dataset

## Client Library

The client app should be a fully standalone command-line python application, that is easily installable and runnable. The app should provide command-line arguments that correspond and support each of the API actions above - how you structure the command line arguments and what you call them is left up to yourselves.

## Technologies

- A Python 3 framework that supports generating JSON APIs (we highly recommend Django and DRF as we use these ourselves)
- Build systems, tools, and scripts of your choice, e.g. poetry, setup.py, docker, etc.
- Any libraries you may find useful to help your task, we prioritise using existing libraries to accomplish tasks rather than building in-house

## Requirements

- Multi-user support and log-in is NOT required for this project
- Instructions should be provided on how to build / bundle / start the system
- You should aim to use the latest Python language features, ecosystem, tooling, and libraries where possible

### Optional Requirements

- As CSVs can be untrusted, you should consider running the CSV importing within a container / sandbox

# Review

Please don't spend more than 2-4 hours on this - we're looking to see how you approached the problem and the decisions made rather than a complete solution. This should be a fun challenge rather than a stressful endeavour.

There is no right answer as such, we will mainly be looking at code quality, software architecture skills, completeness of the solution from a software engineering perspective, and clarity of thought.

Once completed, please create a PR containing your work, send us an email, and book a second follow-up interview via angellist (https://angel.co/schedule/mandeep-gill-2).