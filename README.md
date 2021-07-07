# TruckReport

Test project
Truck report is a prototype application for collecting vehicle data and outputting the collected data into small reports.

The project consists of three modules:
1. ASP.NET core 3.1 API "TruckReportServer" for receiving \ entering \ updating information in the data warehouse.
2. The .NET Framework 4.5 "TruckReportLibF" class library, which contains data models and some auxiliary classes.
3. Client application .NET Framework 4.7.1 WPF "TruckReportClient".

Server:
The API is configured as a kestrel server.
When the "TruckReportServer" Api is launched, several test vehicles and several test reports are generated.
The data in the reports is refreshed automatically by a timer.
Each report is updated according to the frequency selected by the user.
When the data refresh timer is triggered, the reports are filled with random data to simulate changes in vehicle sensors.
The data warehouse is simulated using a standard list of class instances.
Test cars and reports are created in the "TruckCreator" and "Reports" classes in the "Services" folder.
For testing, a test mode was implemented, the description of which can be found in the "Reports" class, the "Services" folder.

Client application:
At startup, the application tries to get the list of vehicles by sending a request to the "TruckReportServer" API.
If the data request is unsuccessful, an error message will be displayed.
If the request is successful, the application receives a list of cars represented by car numbers.

User can add, delete and view reports. The user cannot edit reports, cannot add / remove / edit cars.

To add a report, the following conditions must be met:
  The position of the responsible person has been filled.
  Car number selected
  Report type selected
  Frequency of update of reports is selected
  
If the conditions are not met, a warning will be displayed.

To delete a report, the following conditions must be met:
  Select report
  
To update reports, the following conditions must be met:
  Choose a car

Report data is loaded as needed. Loading takes place for a specific selected vehicle.
When adding / deleting a report, the list of reports for a specific selected vehicle is updated.
The data of reports is refreshed manually by clicking the "Refresh reports" button. Information is updated for a specific selected vehicle.
When performing any action, a message about the action performed is displayed. The message is located under the "Refresh reports" button.
