# Concertrip

## Introduction

Concertrip is a web-based application developed during my time as a Fellow with the Insight Data Science program. Using user-supplied itinerary information and musical preference, it ranks and recommends concerts that best match the user's trip.

Concertrip is built using a number of different technologies and frameworks, including:
- Python
- JavaScript
- Flask
- MySQL
- Mapbox/Leaflet

## Algorithm

The functionality of Concertrip consists of two pieces: **artist ranking** and **distance optimization**. Both of these pieces rely on the Python library [NetworkX][networkx] for the fundamental calculations.

### Artist ranking

A large musical similarity graph was pre-constructed using data scraped from Billboard and LastFM. After the user inputs their itinerary up-to-date event information is pulled from Bandsintown.com. The shortest network path distance from each event artist to the one entered on the input page is used as a measure of similarity, and it is this metric is used to select the best event for each date/location combination.

### Distance optimization

A second network is constructed among the best events selected from the previous section, and NetworkX is again used to find the shortest path from the starting location to the end location. 

## Visualization

Back-end processing returns a list of best-fit events, which are mapped out for the user with Mapbox and Leaflet.js
