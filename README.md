## Magazine Domain Code Challenge

# Overview

This project simulates a Magazine domain using a database-backed system with three main models:

Author: Represents an author who writes articles.

Article: Represents an article written by an author and published in a magazine.

Magazine: Represents a magazine that publishes articles.

The relationships between these models are as follows:

An Author has many Articles.

A Magazine has many Articles.

An Article belongs to both an Author and a Magazine.

Author and Magazine share a many-to-many relationship through Article.

This application uses Python, SQLite, and SQLAlchemy to implement database models and methods.

## Setup Instructions

Install project dependencies:

pipenv install

Enter the pipenv shell:

pipenv shell

Initialize the database:

python3 app.py

Use the provided test suite to verify your implementation:

pytest

## Models and Deliverables

# Author

Initialization and Properties

__init__(self, id, name)

Initializes an Author instance and creates a new entry in the authors table.

property id

Returns the author's ID from the database.

Must be of type int.

property name

Returns the author's name.

Name must be a str and at least 1 character long.

Name cannot be changed after instantiation.

# Methods

articles()

Returns all articles associated with the author using SQL JOIN.

magazines()

Returns all magazines associated with the author using SQL JOIN.

# Magazine

Initialization and Properties

__init__(self, id, name, category)

Initializes a Magazine instance and creates a new entry in the magazines table.

property id

Returns the magazine's ID from the database.

Must be of type int.

property name

Returns and sets the magazine's name.

Name must be a str and between 2 and 16 characters.

property category

Returns and sets the magazine's category.

Category must be a str and at least 1 character long.

 Methods

articles()

Returns all articles associated with the magazine using SQL JOIN.

contributors()

Returns all authors who have written articles for the magazine using SQL JOIN.

article_titles()

Returns a list of article titles for the magazine. Returns None if no articles exist.

contributing_authors()

Returns a list of authors with more than 2 articles for the magazine. Returns None if no such authors exist.

# Article

Initialization and Properties

__init__(self, author, magazine, title)

Initializes an Article instance and creates a new entry in the articles table using the author and magazine IDs as foreign keys.

property title

Returns the article's title.

Title must be a str and between 5 and 50 characters.

Title cannot be changed after instantiation.

Methods

author

Returns the author of the article using SQL JOIN.

magazine

Returns the magazine of the article using SQL JOIN.

# Development Tips

Draw the domain on paper to understand the relationships between models.

Prioritize working methods over completing all deliverables.

Test each method incrementally as you develop.

# Refactoring

Extract repeated logic into helper methods.

Use Python's getattr() and hasattr() where appropriate to enforce immutability.

Use SQLAlchemy relationships for simplifying joins.

# Testing

Run the test suite to ensure your implementation meets the requirements:

pytest

Ensure all tests pass before submission.

