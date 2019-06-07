
# HTTP Request/Response Cycle - Lab

## Introduction 

In this lab, we'll make use of the `requests` module commands and properties seen in the previous lesson, to extract information for a web service called **"Open Notify"** to access NASA's space data. 

## Objectives

You will be able to:

* Understand and explain the HTTP Request/Response cycle
* Make http requests in Python using the ‘requests’ library

## Open Notify 

[Open Notify](http://open-notify.org/)  is an an open source project to provide a simple programming interface for some of NASA’s awesome data. This takes live raw data from NASA's systems and turn them into APIs related to space and spacecraft. We can access following information from open notify. 

* Current Location of the International Space Station

* Overhead Pass Predictions for the International Space Station

* Number of People in Space
    
### API endpoints

OpenNotify has several API endpoints. 
>An endpoint is a server route that is used to retrieve different data from the API. 

For example, the `/comments` endpoint on the Reddit API might retrieve information about comments, whereas the `/users` endpoint might retrieve data about users. To access them, you would add the endpoint to the base url of the API.

For the OpenNotify API, we have following end points 

1. Current Location of the International Space Station `/iss-now.json`
2. Overhead Pass Predictions for the International Space Station `/iss-pass.json`    
3. Number of People in Space `/astros.json`

The json extension simple tells us that the data is being returned in a JSON format.

In this lab, we'll be querying a this API to retrieve live data about the International Space Station (ISS). Details on OpenNofity , endpoints, syntax and services it offers can be viewed [Here](http://open-notify.org/Open-Notify-API/)

![](images/iss.jpg)

### Current location of International Space Station

The first endpoint we'll look at on OpenNotify is the` iss-now.json` endpoint (current location of international space station). This endpoint gets the current latitude and longitude of the International Space Station.  Perform following tasks 
* Make a get request to get the latest position of the international space station from the opennotify api's `iss-now` endpoint at http://api.open-notify.org/iss-now.json
* Check the status code of the response
* Interpret the returned code


```python
# You Code Here
```


```python
# Your comments 
```

* Print the contents of the response and identify its current location


```python
# You Code Here
```


```python
# Interpret your results using the API
```

### Check the next pass of International space station for a given location

Let's repeat the above for the second endpoint `iss-pass.json`. This end point is used to query the next pass of the space station on a given location. Let's just run as above and record your observations.


```python
# You Code Here
```


```python
# Your comments 
```

So clearly there is something wrong as we had a 400 response. This is how you should always test your responses for validity. 

if we look at the documentation for the OpenNotify API, we see that the ISS Pass endpoint requires two parameters.

> The ISS Pass endpoint returns when the ISS will next pass over a given location on earth. In order to compute this, we need to pass the coordinates of the location to the API. We do this by passing two parameters -- latitude and longitude.

We can do this by adding an optional keyword argument, params, to our request. In this case, there are two parameters we need to pass:

* lat -- The latitude of the location we want.
* lon -- The longitude of the location we want.

Perform the following tasks :
* Set parameters to reflect the lat and long of New York  (40.71, -74)
* Send a get request to OpenNotify passing in the lat long parameters as k:v pairs in a dictionary
* Check the status code and interpret
* Print the header information and the returned content


```python
# You Code Here
```


```python
# Check the API and interpret your results - when will ISS pass over NEW York next ?
```

### Finding the number of people in space

OpenNotify has one more API endpoint, `/astros.json`. It tells you how many people are currently in space. The format of the responses can be studied [HERE](http://open-notify.org/Open-Notify-API/People-In-Space/).

Read the above documentation and perform following tasks:

* Get the response from astros.json endpoint
* Count how many people are currently in space
* List the names of people currently in space.


```python
# You Code Here
```


```python
# Interpret the Results - How many people are in space and what are their names 
```

## Summary 

In this lesson we saw how we can use request and response methods to query an Open API. We also saw how to look at the contents returned with the API calls and how to parse them. Next, we'll look at connecting to APIs which are not OPEN, i.e. we would need to pass in some authentication information and filter the results. 
