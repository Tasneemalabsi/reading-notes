# REST

***REST** is a set of architectural constraints, not a protocol or a standard. API developers can implement REST in a variety of ways.*

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON (Javascript Object Notation), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular programming language to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines. *

**REST stands for representational state transfer and was created by computer scientist Roy Fielding**

### In order for an API to be considered RESTful, it has to conform to these criteria:

- A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
- Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
- Cacheable data that streamlines client-server interactions.
- A uniform interface between components so that information is transferred in a standard form. 
- A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
- Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality. 

**Examples of API servers :**

1. [locationiq](https://locationiq.com/)
which has some endpoints that helps in the determination of different locations around the world using the latitude and longitude lines. These end points might render all of the information about a specific location using JSON format as well as the map and routing for that location.
2. [weatherbit](https://www.weatherbit.io/) provides information about the weather in JSON format
3. [moviedb](https://developers.themoviedb.org/3/getting-started/introduction) has a huge movie database, To register for an API key, click the  from within your account settings page. You can also view the screenshots below for help:

- Click on your avatar or initials in the main navigation 
- Click the "Settings" link 
- Click the "API" link in the left sidebar 
- Click "Create" or "click here" on the API page

4. [yelp](https://www.yelp.com/developers/documentation/v3/business_search)  The endpoint of this server returns up to 1000 businesses based on the provided search criteria. It has some basic information about the business.


