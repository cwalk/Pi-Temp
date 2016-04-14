## Introduction
Web server using a Raspberry Pi and DHT22 sensor to graph the humidity and temperature in my apartment over time. The data can be accessed over a web browser.

Skills I learned during this project:
- Setup the minimal Raspbian operating system to the RPi, called Minibian
- Install and use Python, and the Python virtual environment
- Install and use Flask, a Python-based web micro-framework
- Install and use uWSGI as the application server for Flask
- Install and use Nginx light-weight web server
- Use Skeleton to make the web UI look better
- Use the RPi GPIOs as digital input and outputs
- Use a DHT22 humidity and temperature sensor
- Install and use the SQLite database to store sensor data
- Add a cron job to store sensor data every so many minutes
- Use the Google Chart API to create visual representations of the sensor data
- Use Javascript/JQuery to add interactivity to web pages
- Use Plotly for graphical analysis of sensor data

## Summary

The `lab_app` folder contains the code for the project (The html folder, button.py, and blink.py were just for testing purposes).

Inside `lab_app` you will find the main python server, `lab_app.py`. This uses a cronjob to take a temperature and humidity reading every so many minutes, and stores it in a sqlite database. The web server has 2 views, `lab_temp.html` and `lab_env_db.html`, which I refer to as current view and historic view respectively.

## Current

In the current view, the current temperature and humidity taken from the sensor is displayed on the web page. This page updates every 10 seconds, and has a link to the historic view.

## Historic

The historic view has a couple features. The first is a to and from date input, which uses a date time picker plugin. Combined with a submit button, this allows you to view the temperature and humidity data within any date time range easily. The next feature are four radio buttons, to easily see the last 3, 6, 12, and 24 hours of data. There are two links, one to the current view, and another to export the data to Plotly. Clicking this link will send you to plotly and show you a graph of Temperature vs Humidity.

The main view are 2 tables combined with Google Charts graphs. The tables both scroll, and the charts display data across the time selected. The times are displayed in your own time zone, as it is determined from your browser.

## YouTube

YouTube: https://www.youtube.com/watch?v=hFqNiZ4p0Ss

## Circuit Diagram

![Circuit Diagram](/Circuit.png?raw=true "Circuit Diagram")
