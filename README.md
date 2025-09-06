# data-analyst-BI 
# Power BI Airline Data Analysis Project

## Overview

This project analyzes airline operations data using Power BI to provide insights into flight schedules, passenger details, and ticketing systems. The goal is to improve operational efficiency and enhance customer satisfaction through effective data visualization and analysis. 

## Problem Statement

The airline industry operates with numerous complexities, requiring effective data management and analysis to gain insights into flight schedules, passenger information, and ticketing trends. [cite: 22, 23]

## Datasets Used

The project utilizes the following datasets: 

1.  Flight Information (FlightID, FlightNumber, Airline, Destination, Status)
2.  Passenger Information (PassengerID, FlightID, SeatNumber) 
3.  Ticket Information (TicketID, FlightID, Booking Status) 

## Objectives

* Analyze and visualize airline data for operational insights.
* Provide insights for passenger management. 
* Analyze ticket booking trends.

## Key Tasks and Steps

1.  **Data Preparation and Cleaning:**
    * Imported all three datasets (Flight Information, Passenger Information, and Ticket Information) into Power BI using Power Query Editor.
    * Removed duplicate rows to ensure data uniqueness. [cite: 2]
    * Formatted all columns correctly (ID columns to Text, status fields to categorical Text, seat numbers to Text). 

2.  **Data Modeling:**
    * Created relationships between the datasets in Power BI's model view. 
    * Used `FlightID` as the common key to link the tables. 
    * Defined one-to-many relationships with `Flight_Information` as the primary table. 

3.  **Enhanced Data Insights:**
    * Created a conditional column named `FlightRating` to classify flights as "Best" if the status was "On Time," and "To Be Improved" otherwise. 
    * Extracted the numeric portion of the `FlightNumber` using "Column from Examples". 

4.  **Calculations using DAX:**
    * Calculated total passengers using the DAX formula: `PassengersPerFlight = CALCULATE(COUNT(Passenger_Information[PassengerID]))`
    * Calculated total confirmed tickets using the DAX formula: `Total Tickets Booked = CALCULATE(COUNT(Ticket_Information[TicketID]), Ticket_Information[BookingStatus] = "Confirmed")` 
    * Created a new table to display only "Best" flights using the DAX formula: `BestFlights = FILTER(Flight_Information, Flight_Information[FlightRating] = "Best")` 

5.  **Visualization and Interactive Features:**
    * Created a bar chart to show the passenger count by airline.
    * Built a matrix visual to display the number of flights by airline and destination. 
    * Used a donut chart to visualize ticket booking statuses (Booked, Pending, Cancelled). 
    * Used a stacked bar chart to compare flight counts across destinations for each airline.
    * Added slicers for Airline and Destination to make the dashboard interactive. 
    * Applied filters to show data for specific airlines and used bookmarks and buttons for navigation between airline-specific pages.

6.  **Final Dashboard and Power BI Service Configuration:**
    * Designed a comprehensive dashboard in Power BI Desktop with key visuals and filters.
    * Configured Row-Level Security (RLS) in Power BI Service to filter data for "Airline A" and assigned the role to a user. 
    * Set up a scheduled refresh in Power BI Service to update the dashboard data daily at 5 PM. 

## Key Findings
* Passenger count varies across airlines (refer to the bar chart).
* Ticket booking statuses are distributed as shown in the donut chart (Confirmed, Cancelled, Pending).
* Flight counts vary by destination (refer to the bar chart).
* The matrix visual shows the distribution of flights by airline and destination.


## Author

Himani-Barmase
