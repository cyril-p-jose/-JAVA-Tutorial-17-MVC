# Tutorial 17: Model-View-Controller (MVC) Architecture in Java

This repository contains the Java Swing and JDBC implementation for **Tutorial 17** of the Object-Oriented Programming (OOP) course. The project demonstrates the **Model-View-Controller (MVC)** design pattern by implementing a database-driven Visitor Counter application.

---

## 📌 Project Overview

| Details | Description |
| :--- | :--- |
| **Course Name** | Object Oriented Programming |
| **Course Code** | 24SJPBCST304 |
| **Academic Year** | 2026-2027 |
| **Module No.** | Module 4 |
| **Topic** | MVC (Model-View-Controller) Architecture |
| **IDE** | Eclipse Java IDE |
| **Database** | MySQL (`mydb`) |

---

## 📝 Problem Statement

Design a **Visitor Counter** application using the MVC architectural pattern. The system tracks the number of visitors and updates the display each time a user clicks a button. The visitor count is persistently stored in a database table named `counter` with a single field: `visitor_count`.

### Requirements Breakdown:
1. **Model (`CounterModel`)**:
   * Connects to the database (`mydb`).
   * Reads the current visitor count from the `counter` table.
   * Increments and updates the visitor count in the database.
2. **View (`CounterView`)**:
   * Java Swing interface containing a button labeled `"Click Here to See Visitor Count"`.
   * Includes an initially blank label to display the visitor number.
   * Provides a method to update the label with the new visitor count.
3. **Controller (`CounterController`)**:
   * Listens for the button click event.
   * Requests the Model to increment the visitor count.
   * Passes the updated visitor count from the Model to update the View.
4. **Main (`MainApp`)**:
   * Instantiates the Model, View, and Controller.
   * Launches the Swing GUI.

---

## 🎯 Expected Behavior

* When the GUI loads, the visitor count label is initially blank.
* Clicking the button increments the visitor count stored in the database.
* The label updates to display: `"You are visitor No: X"`.

---

## 🗄️ Database Setup

Run the following SQL commands in MySQL Workbench or Command Line before launching the application:

```sql
-- Create Database
CREATE DATABASE IF NOT EXISTS mydb;
USE mydb;

-- Create Counter Table
CREATE TABLE IF NOT EXISTS counter (
    visitor_count INT DEFAULT 0
);

-- Insert Initial Record (only 1 row needed)
INSERT INTO counter (visitor_count) VALUES (0);
