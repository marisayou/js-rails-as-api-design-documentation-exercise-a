# API Design Exercise - A

## Part I - Backend API Documentation

To access information from the Dogs API, first navigate to the correct directory and run "bundle install" in the terminal. Then, to set up and seed the database, run "rails db:migrate" followed by "rails db:seed" in the terminal.

### Accessing Resources
Fetch information about dogs from http://localhost:3000/dog_search in JSON format. The data is contained in an array of dog objects, with each object representing a different dog. Each dog object in the array will be in the following format:
```
{
    "id": 141,
    "name": "Abby",
    "breed": "Sussex Spaniel",
    "age": "adult",
    "size": "large",
    "phrase": "they're good dogs Brent",
    "created_at": "2020-11-30T17:33:29.955Z",
    "updated_at": "2020-11-30T17:33:29.955Z"
}
```

### Searching For Dogs
Dogs can be searched for given a search term. Search terms are not case-sensitive and should be passed into params with a key of `:query`. Any dogs whose name, breed, phrase, or size contain the search term will be displayed as a result. Longer search terms will result in narrower searches with fewer dogs being displayed while shorter search terms will result in broader searches with more dogs being displayed. For example, a search term of "Abby" will result in a list of dogs, each with the name "Abby" while a search term of "A" will result in a list of any dog whose name, breed, phrase, or size contain the letter "A."

### Sorting Dogs
Dogs can also be sorted alphabetically by any of their attributes (name, breed, age, size, or phrase). By default, dogs are sorted by their names. To sort by a different attribute, pass the name of the attribute (for example, "breed" to sort by breed) into params with a key of `:sort_field`. 

## Part II - Build a Frontend Feature

Your partner will send you a markdown file documenting an API. Using that documentation, add the following feature to your frontend app.

Build out the coffee search page in the `coffee-frontend` directory. It should

- When the page loads, display a list of the first 5 coffees
- When the user types an origin into the origin input, show the first 5 coffees whose origin matches
- When displaying coffees, only show 5 results at a time
- When the user clicks the 'Next' button, show the next 5 results
