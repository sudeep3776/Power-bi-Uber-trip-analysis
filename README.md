# Project Title
# Uber Trip Analysis Dashboard 

# dataset used 
- <a href="https://github.com/sudeep3776/Power-bi-Uber-trip-analysis/blob/main/Uber%20Trip%20Details.xlsx"> Dataset view </a>
- <a href="https://github.com/sudeep3776/Power-bi-Uber-trip-analysis/blob/main/UBER%20DASHBOARD.pbix"> Dashboard view </a>

   Screenshot <img width="1387" height="830" alt="Screenshot dashboard" src="https://github.com/user-attachments/assets/1e81879a-4143-441d-82c0-f04e2d959391" />

## Overview

The dashboard features a clean navigation system across three report pages — Overview Analysis, Time Analysis, and Details (Raw Data) — with dynamic slicers for date range, city, and a custom parameter-driven measure selector.

## Problem Statement
 
Ride-hailing platforms generate massive volumes of trip data every day, but raw data alone does not surface actionable patterns. Business stakeholders need answers to questions such as:

When is demand highest and how should driver supply be adjusted?
Which vehicle categories generate the most revenue?
What payment methods do customers prefer?
Which locations have the highest pickup frequency?
How do day vs. night trips compare in volume and value?

This dashboard consolidates all these dimensions into a single, filterable report — reducing the time-to-insight from hours of manual analysis to seconds of self-service exploration.

## Dataset

The analysis is built on two primary tables:
### Trip Details Table
Contains one record per Uber trip with the following fields:
ColumnDescriptionTrip IDUnique identifier for each tripPickup TimeExact date and time of passenger pickupDrop Off TimeExact date and time of drop-offPassenger CountNumber of passengers per tripTrip DistanceDistance covered (in miles)PULocationIDNumeric pickup location codeDOLocationIDNumeric drop-off location codePayment TypeMode of payment (Uber Pay, Cash, Amazon Pay, Google Pay)Fare AmountBase fare before additional chargesSurge FeeExtra charge applied during peak demandVehicle TypeUber service category (UberX, UberL, Uber Black, SUV, etc.)
### Location Table
Maps numeric location IDs to human-readable names and cities.
ColumnDescriptionLocationIDUnique identifier for each zoneLocationArea or neighborhood nameCityCity in which the location exists
Date Range: July 2024 onward
Granularity: Individual trip level

## Tools & Technologies
ToolPurposePower BI DesktopDashboard development, data modeling, and visualizationDAX (Data Analysis Expressions)Custom measures and KPIsPower Query (M Language)Data transformation and cleaningCalendar TableCustom date table for time intelligenceParameter FieldsDynamic measure switching on visuals

## Methods

Data Ingestion — Loaded trip and location CSV data into Power BI via Power Query.
Data Cleaning — Handled nulls, standardized date/time formats, and validated location ID joins.
Data Modeling — Built a star schema: Trip Details (fact table) linked to Location Table and Calendar Table (dimension tables).
DAX Measures — Created key performance metrics:

Total Bookings — Count of distinct Trip IDs
Total Booking Value — Sum of all fare amounts
Avg Booking Value — Average fare per trip
Total Trip Distance — Sum of all trip miles
Avg Trip Distance — Average miles per trip
Avg Trip Time — Average duration in minutes
Most Frequent Pickup Point — Top pickup location by count
Most Frequent Dropoff Point — Top drop-off location by count
Fastest Trip — Minimum trip duration


Dynamic Measure Parameter — Implemented a field parameter allowing users to switch the Y-axis metric across all trend charts simultaneously.

Time Intelligence — Used the Calendar Table to break down trends by day of week, pickup hour bins, and date hierarchy.

Report Design — Built 3 pages with a consistent navigation panel, KPI cards with icons, and interactive cross-filtering.


## Key Insights
### Overview

Total Bookings, Total Revenue, Avg Booking Value, Total Distance, and Avg Distance are surfaced as prominent KPI cards for instant executive-level visibility.

Payment Type breakdown (Uber Pay, Cash, Amazon Pay, Google Pay) reveals digital wallet dominance and cash usage trends.

Day vs. Night Trips — Donut chart comparing day and night trip volumes highlights demand shifts across the clock.

Vehicle Category Performance — Pivot table comparing all vehicle types across Total Distance, Avg Booking Value, and Total Bookings allows direct comparison of fleet segments.

Location-based Demand — Bar chart of pickup counts by location identifies the highest-demand zones for driver positioning.

### Time Analysis

Peak Hour Distribution — Bookings broken down by pickup hour bins reveal morning and evening rush patterns.

Day-of-Week Trends — Mid-week days (Tuesday–Thursday) show consistently higher booking volumes compared to weekends.

Hourly × Day Heatmap — A combined hour-and-day matrix pinpoints exact peak windows (e.g., Thursday evenings, Wednesday mornings).

Surge Fee Patterns — Surge fees correlate with identified peak hours, confirming demand-driven pricing behavior.

###  Details

Full drillthrough table showing individual trip records with Booking Value, No. of Passengers, Distance, Pick Date, Pickup Hour, and Pick Location for granular audit and exploration.


### Dashboard Preview

Report Pages

PageDescriptionOverview AnalysisKPI cards, payment type, day/night split, vehicle table, location chartTime AnalysisHourly trends, day-of-week bars, pickup time bins, combined heatmapDetailsRaw trip-level data table with all key fields
To view the live dashboard, open UBER_DASHBOARD.pbix in Power BI Desktop 

