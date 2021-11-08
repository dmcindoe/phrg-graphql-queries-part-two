# Overfetching Queries

Chances are in the last lesson you overfetched from the pokemon database. If not, good for you! Nevertheless, it is good to recognize that GraphQL queries should only request what is needed and nothing more. When more than is needed is queried, it is called overfetching, and it is taxing on your database and response time.

For this lesson, we need to build GraphQL queries that **only** request what is asked for and nothing more.

## Pokemon

Use [Pokemon-GraphQL](https://graphql-pokemon.now.sh/) to form queries that only return the requested data.

1. Pokemon names and their respective fast attack names for the first 10 pokemon.
1. The amount required for Squirtle to evolve, the name of Squirtle's evolutions, the amount required for those evolutions to evolve again, and the names of the Squirtle's evolved evolutions.
1. The minimum wieght and height of the first 5 pokemon, along with their number.
1. Sandshrew's classification, weaknesses, types, and image url.

## Geography

We also want to drill into some infomation on the world's countries and languages and GraphiQL is not the only GraphQL Interactive Development Environment (IDE) out there.

[Countries](https://countries.trevorblades.com/) uses a GraphQL IDE with a slightly different interface. Use this site to form queries that only return the requested data. Be sure to explore the "docs" tab on the right of the page.

1. All the continent names.
{
  continents{
    name 
  }
}
1. All countries names and their capitols.

{
  continents{
    name 
    countries {name capital}
  }
}
1. All countries names, codes, and all the languages spoken in each country.
{
  continents{
    name 
    countries {
      code 
      name 
      capital
      languages{name}
    }
  }
}
1. The code for Brazil is "BR". Query for its name, native name, phone code, flag (emoji), and all of its states.
{
    country(code: "BR") {
      code 
      name 
      native
      phone
      emoji
      states{name}
  }
}

1. The code for Dutch is "nl". Query the language's name, whether it reads right-to-left, and what it is referred to natively.
{
    language(code: "nl") {
      name 
      native
      rtl
  }
}


1. The code for Europe is "EU". Query the continent's name, and its countries names and currencies.
{
  continent (code: "EU"){
    name
    countries {
      name 
     currency
    }
  }
}
