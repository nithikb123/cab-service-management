CREATE DATABASE Cab_booking;
USE cab_booking;
CREATE TABLE Cab_details(
Cab_no int primary key NOT NULL UNIQUE,
Cab_model VARCHAR(50) NOT NULL,
Cab_discription VARCHAR(200) NOT NULL,
Capacity int NOT NULL
);
CREATE TABLE passenger(
passenger_id int primary key NOT NULL,
name VARCHAR(50) NOT NULL,
username VARCHAR(50) NOT NULL,
email VARCHAR(50) NOT NULL UNIQUE,
password VARCHAR(50) NOT NULL,
phone_no int NOT NULL 
);

CREATE TABLE booking(
id int primary key AUTO_INCREMENT,
pick_up VARCHAR(50) NOT NULL,
Drop_off VARCHAR(50) NOT NULL,
Date DATE,
Time TIME,
Cost INT NOT NULL,
Cab_no int NOT NULL,
passenger_id int not null,
CONSTRAINT fk_cab_no foreign key(Cab_no) references Cab_details(Cab_no),
CONSTRAINT fk_passenger_id foreign key(passenger_id) references passenger(passenger_id)
);
CREATE TABLE Driver_details(
id int primary key not null,
name VARCHAR(50) NOT NULL,
email VARCHAR(50) NOT NULL,
Mobile_no int NOT NULL,
Address VARCHAR(200) NOT NULL,
Cab_num int not null,
CONSTRAINT fk_cab_num foreign key(Cab_num) references Cab_details(Cab_no)
);

