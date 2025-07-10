# CS-UY Introduction to Databases Final Project

## Use Cases Overview

### Customer Use Cases

#### 1. Purchase Ticket
**Functionality:** Allows a user to purchase a ticket for a specified flight.  
**Process:** Upon accessing the ticket purchase page, the user fills out a form with flight details (flight number, departure time). When submitted, the purchase information is stored in the database.

#### 2. View My Flights
**Functionality:** Enables users to view upcoming flights they've booked.  
**Process:** After login verification, the system retrieves flights with departure times later than the current time and displays them.

#### 3. Cancel Ticket
**Functionality:** Allows users to cancel a purchased ticket.  
**Process:** Checks if the flight's departure time is more than 24 hours away. If so, deletes the ticket record and redirects to "My Flights" with a status message.

#### 4. Rate Flights
**Functionality:** Lets users rate and comment on past flights.  
**Process:** Fetches completed flights (arrival time in the past) and displays them for rating submissions.

#### 5. Customer Profile
**Functionality:** Displays the logged-in user's profile information.  
**Process:** Verifies login status and retrieves personal details (e.g., email) from the Customer table.

#### 6. Submit Rating
**Functionality:** Processes rating submissions for completed flights.  
**Process:** Inserts or updates the rating/comment in the Ratings table and confirms the submission.

#### 7. Logout
**Functionality:** Logs out the current user.  
**Process:** Clears the session and redirects to the login page.

### Authentication & Flight Search Use Cases

#### Logging In
**Functionality:** Authenticates users as customers or airline staff.  
**Process:** Single form with two submit buttons (customer or staff). The system checks credentials and handles errors or initiates a session.

#### Registration
**Functionality:** Registers new customers and airline staff.  
**Process:** Separate templates for customers and staff; the system validates input, checks for existing usernames or invalid airline references, and handles errors.

#### Display One-Way & Return Flights
**Functionality:** Searches for one-way and return flights based on origin and destination.  
**Process:** Form with two submit buttons; different SQL queries join airport, flight, ticket, and airplane tables to fetch flight information and prices, with error handling for nonexistent flights.

#### Check Flight Status
**Functionality:** Retrieves the status of a specific flight.  
**Process:** User inputs flight details; the system queries the database and displays status or error messages if not found.

### Airline Staff Use Cases

#### 1. Profile View
**Functionality:** Shows the airline staff member's profile and associated airline.  
**Process:** Validates staff login and retrieves profile details.

#### 2. View Future Flights
**Functionality:** Lists all upcoming flights for the staff member's airline within 30 days.  
**Process:** Executes a date-filtered query and displays results.

#### 3. Create New Flight
**Functionality:** Allows scheduling of new flights.  
**Process:** Staff submits flight details via form; data is inserted and the updated flight list is shown.

#### 4. Change Flight Status
**Functionality:** Updates the operational status of flights.  
**Process:** Validates flight existence, updates status, and confirms the change.

#### 5. Add New Airplane
**Functionality:** Adds a new aircraft to the fleet.  
**Process:** Staff enters airplane details; the system validates and inserts a new record.

#### 6. Add New Airport
**Functionality:** Registers new airports.  
**Process:** Checks for duplicates and inserts new airport data.

#### 7. View Flight Ratings
**Functionality:** Displays passenger ratings and comments for flights.  
**Process:** Queries the evaluations database and shows average and individual ratings.

#### 8. Schedule Maintenance
**Functionality:** Schedules maintenance for airplanes.  
**Process:** Validates airplane ID, checks conflicts, and logs maintenance sessions.

#### 9. View Earned Revenue
**Functionality:** Calculates revenue from ticket sales over selected periods.  
**Process:** Summarizes sales data for last month and year.

#### 10. View Frequent Customers
**Functionality:** Identifies frequent flyers.  
**Process:** Retrieves customer travel history and frequency.

