  This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.
  
  Steps:
  1. User accesses AdminDashboard or Appointment pages and can interact with this pages. Also other iformation can called throught REST API
  2. The action is routed to the appropriate Thymeleaf or REST Controller. In controller request validated, continue it's journey.
  3. The controller calls the service layer and the service runs approtiate logic and the end of process return result to the controller.
  4. The service uses repository layer for database management, Spring JPA for SQL database or Spring MongoDB for document based NoSQL database.
  5. MySQL uses stores entites with their schema and constraints and Mongodb stores flexible document based data structures.
  6. Through data binding MySQL convert data to JPA entities that represent database rows and annotated with @Entity. Mongodb maps document objects to object. They annotated with @Document and stored in Mongodb as BSON/JSON collections.
  7. Thymeleft takes model and renders html documents for browsers using prepared templates, REST Controllers return results with HTTP response, serializing objects to JSON. 
