
## MySQL Database Design

### Table: patients
- id: INT, Primary Key, Auto Increment
- fullName: VARCHAR(255), Not Null,
- dob: DATE, Not Null,
- gender: VARCHAR(1), Not Null

### Table: doctors
- id: INT, Primary Key, Auto Increment
- fullName: VARCHAR(255), Not Null,
- degree: VARCHAR(128), Not Null,
- specialization: VARCHAR(128), Not Null,
- dob: DATE,
- gender: VARCHAR(1)

### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)

### Table: admin
- id: INT, Primary Key, Auto Increment
- fullName: VARCHAR(255), Not Null,
- username: VARCHAR(50), Not Null, UNIQUE

## MongoDB Collection Design

### Collection: prescriptions
```json
{
  "_id": "ObjectId('64abc123456')",
  "patientName": "John Smith",
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
```

### Collection: feedback

```json
{
  "_id": "ObjectId('64abc123456')",
  "patientId": 51,
  "doctorId": 51,
  "content": "Good doctor",
  "rating": 5
}
```

### Collection: logs

```json
{
  "_id": "ObjectId('64abc123456')",
  "system": "Patient Service",
  "logLevel": "INFO",
  "content": "Patient created successfully",
  "tags": ["patient", "info"]
}
```

### Collection: messages

```json
{
  "_id": "ObjectId('64abc123456')",
  "author": "John Doe",
  "receiver": "Anna Doe",
  "title": "Appointment date",
  "content": "We move your apoointment to tomorrow"
}
```
