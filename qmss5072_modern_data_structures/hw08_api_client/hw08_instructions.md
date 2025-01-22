# QMSS G5072 Homework 8

# Writing a Simple API Client in Python

In this assignment, you will interact with web APIs using Python's `requests` package. You'll choose an API, fetch data from it, and then write a simple API client function to make this task easier.

Writing a simple API client
============================

### Choose your API

To accommodate your different interests and data needs, this exercise asks you to choose a data API yourself. It is perfectly fine if the data collection from such an API is useful for another class, project, or your thesis. 

Here are a couple of suggestions for API choices:

**Select one API of your choice**:

- A huge list of ~40k APIs – you should have no trouble finding one you have some interest in! https://rapidapi.com/hub

Here are some fun ones: 

- **NASA API**:
  
  - **Description**: Offers access to a wide range of NASA data, including asteroid information, and Mars Rover photos.
  - **API Documentation**: [NASA API](https://api.nasa.gov/)
  - **Example Data**: Asteroid information, Mars Rover photos.

- **IP Geolocation API**:
  
  - **Description**: Provides information about an IP address, including country, city, timezone, latitude, and longitude.
  - **API Documentation**: [IP Geolocation API](https://ipgeolocation.io/)
  - **Example Data**: Location information based on IP address.

- **PokéAPI**:
  
  - **Description**: Provides data on Pokémon, including information on species, abilities, and moves.
  - **API Documentation**: [PokéAPI](https://pokeapi.co/)
  - **Example Data**: Pokémon species, abilities, moves, types, etc.

- **Open-Meteo API**:
  
  - **Description**: Offers global weather forecast API for non-commercial use.
  - **API Documentation**: [Open-Meteo](https://open-meteo.com/)
  - **Example Data**: Temperature, wind speed, precipitation, etc.

- **Rick and Morty API**:
  
  - **Description**: Provides information about the characters, episodes, and locations from the "Rick and Morty" TV show.
  - **API Documentation**: [Rick and Morty API](https://rickandmortyapi.com/)
  - **Example Data**: Characters, episodes, and locations details.

- **JokeAPI**:
  
  - **Description**: Serves programming jokes and general jokes through a simple endpoint.
  - **API Documentation**: [JokeAPI](https://v2.jokeapi.dev/)
  - **Example Data**: Text-based jokes categorized by type.

- **REST Countries API**:
  
  - **Description**: Provides information about countries, such as name, population, area, and languages spoken.
  - **API Documentation**: [REST Countries](https://restcountries.com/)
  - **Example Data**: Country details including population, area, languages, etc.

- **ExchangeRate-API**:
  
  - **Description**: Provides exchange rate information between different currencies.
  - **API Documentation**: [ExchangeRate-API](https://www.exchangerate-api.com/)
  - **Example Data**: Currency conversion rates.

... or any other data API you can find on the internet.

### Task

The task is to use the `requests` package (do not use possibly existing specific python packages for the API) to:  

- interact with the API  
- create a dataset with multiple records by requesting data from the API using the `requests` package  
- write a simple API client, i.e. a function that would make downloading/interacting with the API simple for a Python user who does not know `requests` 

#### 1. Choose an API

a) For this assignment, select a web Application Programming Interface (API). You can choose from the suggestions above or find one that interests you. Ensure that the API you choose is not one we've already covered in class (e.g., NYTimes, Github, etc.).  

#### 2. Authentication

a) Briefly explain how the API authenticates the user. 
b) If required, apply for an API key and explain how others can do the same (with relevant URL). Do **not** include your API key in your submission.

#### 3. Send a Simple GET request

a) Use the `requests` package to send a GET request and fetch a small amount of data from your API. Describe and use a few query parameters in your request. If you have a choice of the output the API returns (e.g. XML or JSON), I suggest to choose JSON because it easier to work with. Your output here should include the code for the `GET` request, including the query parameters, as well as a snippet of the output.    

b) Check and display the status of your request.   

c) Identify and display the type of the response (e.g., JSON, XML, CSV).  

#### 4. Parse the response and create a dataset

a) Convert the API response into a usable Python object (e.g., list, vector, pandas data frame). Show the code how this is done.  

b) Use the API to create a dataset with multiple records (sample size > 100). Include some interesting features.

c) Provide summary statistics of your dataset. Include the data frame in a .csv file named `data.csv` with your submission.

#### 5. Write an API Client Function

a) Wrap your code from the previous sections into a simple API client function. This function should:

- Allow users to specify query parameters.
- Run a `GET` request with these parameters.
- Check the request's status and inform users of any errors.
- Parse the response and return a Python object (list or data frame).
- Include docstrings explaining the parameters, output, and a usage example.
  Run the function with default values and display the output.

Note: There is no need to make this into an Python package here. A simple function is sufficient.

In the notebook, include your full function to access the API functionality. Set some sensible default values for the query parameters.

Run the function with default values and display the output.

For this part of the question, I am not expecting a full-fledged API client. Rather, I want you to wrap some of the code from the previous questions into a function and generalize a bit.

### Submission

Please follow the [instructions](/Exercises/homework_submission_instructions.md) to submit your homework. The homework is due on Wednesday, November 6 at 5pm.
