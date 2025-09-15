# Student Commute Optimizer

This project is a carpool and route-sharing app for students.  
It helps students who go in the same direction to travel together instead of going alone.  

#Project Overview
- Students enter home and destination on a map.  
- The system checks for other students going on the same or nearby route.  
- If a match is found, it shows their profile with a unique username (not real name).  
- Students can click on an icon and chat directly with each other.  
- Identity is hidden to keep things safe and private.  


# Architecture (Simple View)

flowchart TD
    A[Student App (Frontend - React, Map)] --> B[Backend Server (Node.js/Express)]
    B --> C[(Database - Routes & Users)]
    B --> D[Route Matching Logic]
    A --> E[Chat (Socket.IO)]
    E --> B


# Tech Used

* Frontend: HTML, CSS, JavaScript, React
* Backend: Node.js, Express.js
* Database: MongoDB / PostgreSQL
* Maps: Mapbox / Leaflet
* Chat: Socket.IO

# Flowchart

          ┌────────────────────┐
          │ Student Registers  │
          │ (Unique Username)  │
          └─────────┬──────────┘
                    │
                    ▼
          ┌────────────────────┐
          │ Enter Home &       │
          │ Destination        │
          └─────────┬──────────┘
                    │
                    ▼
          ┌────────────────────┐
          │ Route Generated    │
          │ (via Map API)      │
          └─────────┬──────────┘
                    │
                    ▼
          ┌────────────────────┐
          │ Store Route in DB  │
          │ (Users + Routes)   │
          └─────────┬──────────┘
                    │
                    ▼
          ┌────────────────────┐
          │ Compare Routes      │
          │ (Matching Engine)   │
          └─────────┬──────────┘
                    │
          ┌─────────▼──────────┐
          │ Matches Found?      │
          └─────────┬──────────┘
         Yes        │        No
          ▼         │         ▼
┌─────────────────┐ │  ┌───────────────────┐
│ Show Nearby      │ │  │ No Match Found   │
│ Students on Map  │ │  │ (Wait for others)│
└─────────┬────────┘ │  └──────────────────┘
          │          │
          ▼          │
 ┌────────────────────┐
 │ Chat Anonymously   │
 │ (Socket.IO)        │
 └─────────┬──────────┘
           │
           ▼
 ┌────────────────────┐
 │ Share Ride & Travel│
 └────────────────────┘

 



# Future Scope

* Add group rides with more than 2 students.
* Add ride scheduling for daily use.
* Add ratings and reviews for trust and safety.


