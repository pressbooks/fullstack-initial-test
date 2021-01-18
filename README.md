# Pre-screening Pressbooks challenge

To complete this challenge, create an API with 1 main endpoint: a book list in JSON format. Use the `books.json` file in this repo for the challenge. Create a GitHub or GitLab repository with your implementation and email a link to the project repo to jobs@pressbooks.com.

## Implementation requirements:
- Must be written in PHP (using any framework and/or libraries you prefer)
- Must use a MySQL-based database
- Must contain at least one unit test
- Should provide documentation about the app and the setup environment

Each book in the list should have the following properties:
- `title` (string)    
- `url` (string)    
- `subject` (An object: `{Identifier: Integer, Name: string}`)
- `language` (only 5 allowed: `AR`, `EN`, `ES`, `FR`, `ZH`)
- `word_count` (integer)
- `is_original` (boolean) [*this property indicates whether the book is an original or a copy based on another book*]
- `based_on` (optional) (string) [*Must be present if is_original is false and should contain the value of the URL of the book which it is based on*]

The API should support the following optional GET parameters:
- `per_page`: Integer. Quantity of books displayed per page. [1, 100]. Default: 10
- `page`: Integer. Page number. [1, n]. Default: 1 
- `search`: String. Search pattern. Fields to search: `title` and `subject.Name`.
- `is_original`: Integer. [0, 1]. Filters the list based on the is_original boolean value (i.e. returns books for which is_original is true if value is 1, returns all books for which is_original is false if value is 0)
- `subject`: Integer. Filters the list based on the subject Identifier ID (i.e. returns all books with the specified subject Identifier value).