# ERD Diagram Overview

This folder contains the Entity-Relationship Diagram (ERD) and related documentation for the ALX Airbnb database project.

## Entity-Relationship Diagram

![ERD Diagram](./airbnb-erd.png)

This diagram shows the relationships between the main entities in the Airbnb clone database project:

- **User**: Can be a guest or host. Hosts own properties.
- **Property**: Linked to a host. Can have multiple bookings and reviews.
- **Booking**: Connects a user to a property for a specific date range.
- **Payment**: Linked to a booking. Tracks how the booking was paid for.
- **Review**: Linked to a user and property. Allows rating and feedback.
- **Message**: Tracks communication between users.
