Multi-threaded Event Reservation System
Overview
This project implements a concurrent event reservation system using POSIX threads (pthread). The system supports booking, canceling, and querying event tickets through multiple worker threads. It utilizes mutexes and condition variables to ensure thread safety and proper synchronization.

Features
Concurrent Reservation Handling: Manages event reservations through multiple worker threads.
Thread Synchronization: Uses mutexes and condition variables to maintain data consistency.
Dynamic Query Processing: Handles various types of queries including ticket booking, ticket cancellation, and seat availability checks.
Simulation of Operation Time: Introduces delays to simulate processing times and system load.
Project Structure
main.c: Contains the main logic of the reservation system, including thread creation, synchronization, and query processing.
Makefile: (If applicable) Provides instructions to compile the project.
Installation and Setup
Clone the Repository:

bash
Copy code
git clone https://github.com/vinyl5200/Systems-Lab.git
cd Systems-Lab
Compile the Code:

Ensure you have the necessary development tools and libraries installed (e.g., gcc).

bash
Copy code
gcc -o reservation_system main.c -lpthread
Run the Program:

bash
Copy code
./reservation_system
Code Overview
Shared Data Structures: sharedTable structure is used to manage active queries. The ActiveQueries array keeps track of ongoing queries, and reservationStatus maintains the number of reserved tickets for each event.
Thread Functions: doWork function simulates a worker thread handling random queries related to event reservation.
Synchronization Mechanisms: Utilizes pthread_mutex_t for mutual exclusion and pthread_cond_t for managing thread synchronization.
Key Functions
isQueryRunningForSameEvent(int eventNumber): Checks if there is an ongoing query for the specified event.
getSlotInTable(int queryType, int eventNumber, long ID): Finds an available slot in the ActiveQueries table for a new query.
getAvailableSeats(int eventNumber): Displays the number of available seats for a given event.
bookTickets(int eventNumber, int ticketCount, int *bookedHistory): Books tickets for an event if seats are available.
cancelBookedTicket(int eventNumber, int *bookingHistory): Cancels a booked ticket for an event.
getRandomQuery(int *queryType, int *eventNumber, int *ticketCount, int *bookingHistory): Generates random queries for testing.
Dependencies
POSIX Threads (pthread): Required for multi-threading and synchronization.
Usage
Start the Program: The program will initialize worker threads, simulate event queries, and handle reservations.
Monitor Output: The program outputs information about query processing, booking status, and thread operations.
Notes
The system simulates a multi-threaded environment where threads periodically perform operations related to event reservations.
Adjust #define constants in the code to change the number of events, capacity, or worker threads as needed.
Contributing
Feel free to submit issues or pull requests to enhance the system.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or feedback, please contact vinyl5200.


