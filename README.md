# Meeting-Manager
Introduction
The Meeting Manager project is a comprehensive meeting scheduling system designed to streamline meeting organization and reduce scheduling conflicts. The system provides a robust backend solution for managing one-to-one online meetings and offline group meetings in a room.

#Features
User registration
Room registration
One-to-one meeting scheduling
Offline room meeting scheduling
Meeting scheduling algorithm to prevent conflicts


#Technical Requirements
Java 8 or later
Spring Boot 2.3 or later
PostgreSQL 12 or later
Apache Maven 3.6 or later

#System Architecture
The Meeting Manager project follows a monolithic architecture, with services for user management, room management, and meeting scheduling. The system uses a relational database to store user, room, and meeting data.

#API Endpoints
The Meeting Manager project provides the following API endpoints:
/meeting/addUser: Register a new user
/meeting/addMeetingRoom: Register a new room
/meeting/oneToOneMeeting: Schedule a one-to-one meeting
/meeting/roomMeeting: Schedule an offline room meeting

#Database Design
The Meeting Manager project uses a relational database to store user, room, and meeting data. The database design includes the following tables:
user_registration_table: Stores user information
room_registration_table: Stores room information
slot_registration_table: Stores meeting information
meeting_user_relation_table: Stores meeting attendees

#Future Enhancements
Interday Meeting Scheduling:
Online room meeting scheduling

#Setup Guide
update the datasource details in yml file. (src/main/resources/application-dev.yml)
create the below tables (provided scripts are for postgres DB)

create table user_registration_table
(
user_id bigserial Primary Key,
user_name character varying,
password character varying
);

Create table meeting_user_relation_table
(
sr bigserial Primary Key,
user_name character varying,
meeting_id bigint
);

create table room_registration_table
(
room_id bigserial Primary Key,
room_name character varying
);

create table slot_registration_table
(
meeting_id bigserial Primary Key,
in_time time(0) without time zone,
out_time time(0) without time zone,
room_id bigint,
date_of_meeting timestamp without time zone
);

Update the pom file as per your requirement






