# DataScienceCourse3_Project
**Airline Data Management and Analysis Using Power BI**  
Course: DS PGC Course 3 — Final Project

---

## 📘 Project overview
This project analyses **airline operations** using three datasets (Flight_Information, Passenger_Information, Ticket_Information) and builds an interactive Power BI dashboard for operational insights, passenger management, and ticket booking trends.

**Deliverables:** cleaned data screenshots, data model, DAX calculations, visuals, interactive features, final dashboard with RLS, scheduled refresh, and a 3–5 minute video explaining the project.

---

## 📂 Files included
- `DataScienceCourse3ProjectProblemStatement.pdf` — Project problem statement and dataset references.  
- `DataScienceCourse3ProjectSolutionReport.pdf` — Full written report (screenshots, steps, findings).  
- `DataScienceCourse3ProjectVisualSolution.pdf` — Power BI visuals exported (screenshots of dashboards and charts).

---

## 🧩 Tasks & what I did (summary)
1. **Data Preparation & Cleaning (10)** — Power Query: removed duplicates, filled/handled missing values, standardized columns; screenshot of final cleaned table included.  
2. **Data Modeling (10)** — Created relationships using `FlightID` as key (Flight ↔ Passenger, Flight ↔ Ticket); set proper cardinality and cross-filter direction; screenshot of model included.  
3. **Enhanced Data Insights (10)** — Added conditional column `Flight Category` (Best / To Be Improved) based on Status; used Column From Examples to extract `FlightNumber`.  
4. **Calculations using DAX (10)** — Measures for: Total Passengers (per flight), Total Tickets Booked, Filtered table for Best flights; screenshots of DAX and results included.  
5. **Visualizations & Interactive Features (20)** — Visuals: Passenger count by Airline, Ticket booking status distribution, Flights by Airline & Destination; interactive slicers for Destination & Airline; airline-specific quick views and pages.  
6. **Final Dashboard & Power BI Service (20)** — Comprehensive dashboard; Row-Level Security (RLS) configured for Airline A; scheduled refresh at 5:00 PM daily; screenshot of published dashboard and RLS included.  
7. **Video (20)** — 3–5 minute video explaining introduction, problem statement, key findings, and navigation of the dashboard (link included in report).

---

## 🧮 Key formulas / DAX samples
```DAX
TotalPassengers_Flight :=
CALCULATE( COUNTROWS(Passenger_Information), Passenger_Information[FlightID] = SELECTEDVALUE(Flight_Information[FlightID]) )

TotalTickets_Booked :=
CALCULATE( COUNTROWS(Ticket_Information), Ticket_Information[BookingStatus] = "Confirmed" )

BestFlightsTable :=
FILTER(
  ADDCOLUMNS(Flight_Information, "Category", IF(Flight_Information[Status] = "On Time", "Best", "To Be Improved")),
  [Category] = "Best"
)
```

---

## 🔍 How to review / run locally
1. Download the report PDF and visuals PDF.  
2. Open Power BI Desktop (latest).  
3. Recreate Power Query transformations (Open → Transform data).  
4. Load data model and confirm relationships (Model view).  
5. Check the DAX measures in the Report view and the visuals match the screenshots.

---

## 📌 Notes for grader
- Each deliverable (cleaned data, model, DAX, visuals, RLS, scheduled refresh) has clear screenshots in the solution report.  
- The report includes a Google Drive link to raw datasets and the video walkthrough.

---

## 👤 Author
**Utkarsh Anand** — DS PGC Course 3 Final Project
