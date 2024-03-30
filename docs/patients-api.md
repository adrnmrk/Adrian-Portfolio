# Patients API Documentation
## Overview
The Patients API is a backend service developed to manage patient data and clinical records for the Patient Management mobile application. Built using Node.js for the backend logic and MongoDB as the database, this API seamlessly integrates with the front-end, which is developed using React Native.
### Technologies
- Backend: Node.js
- Database: MongoDB
- Front-end: React Native
 
### Target Audience
This documentation is intended for developers involved in building or maintaining the Patient Management mobile application.

### Project Repositories
- [Node.js API](https://github.com/adrnmrk/MAPD_712_713_Patient_Management/tree/b2b58b727e2e340c7cebe57720468df652738896/MAPD-713-Group_Project)
- [React Native Patient Management App](https://github.com/adrnmrk/react-patient-project.git)

### Base URL
- **iOS Base URL**: `http://127.0.0.1:3000`
- **Android Base URL**: `http://10.0.2.2:3000`

## Endpoints
### Get all patients
`GET http://127.0.0.1:3000/patients`

**Description**: This endpoint makes an HTTP GET request to retrieve a list of patients. 

**Response**: Returns a list of all patients. The response will be a JSON array containing patient objects with attributes such as first name, last name, date of birth, contact information, and so on.

**Request Example**:

    curl --location --request GET 'http://127.0.0.1:3000/patients

**Response Example**:

    [
    {
        "_id": "65f382d7076a0b12026fdb6b",
      "firstName": "Sam",
      "lastName": "Rihan",
      "dateOfBirth": "1999-01-12T00:00:00.000Z",
      "age": 25,
      "gender": "Female",
      ...
      },
      ...
      ]

#### GET /patients/:id
- **Description**: Get a single patient by their patient ID.
- **Parameters**:
  - `id`: The unique ID of the patient.
- **Response**: Returns the patient data if found, otherwise returns a 404 error.

#### POST /patients
- **Description**: Create a new patient in the system.
- **Request Body**: JSON object containing patient information.
- **Response**: Returns the created patient data with a status code of 201.

#### PUT /patients/:id
- **Description**: Update user details with the given ID.
- **Parameters**:
  - `id`: The unique ID of the patient.
- **Request Body**: JSON object containing the updated patient information.
- **Response**: Returns the updated patient data if successful, otherwise returns a 404 error.

#### DELETE /patients/:id
- **Description**: Delete a patient with the given ID along with their associated clinical data.
- **Parameters**:
  - `id`: The unique ID of the patient.
- **Response**: Returns the deleted patient data if successful, otherwise returns a 404 error.

#### POST /patients/:id/clinicaldata
- **Description**: Add clinical data for a specific patient and update the critical condition status.
- **Parameters**:
  - `id`: The unique ID of the patient.
- **Request Body**: JSON object containing clinical data.
- **Response**: Returns the created clinical data with a status code of 201.

#### GET /patients/:id/clinicaldata
- **Description**: Retrieve all clinical data for a specific patient.
- **Parameters**:
  - `id`: The unique ID of the patient.
- **Response**: Returns a list of clinical data associated with the patient.

#### DELETE /patients/:id/clinicaldata/:clinicalDataId
- **Description**: Delete specific clinical data for a patient by ID.
- **Parameters**:
  - `id`: The unique ID of the patient.
  - `clinicalDataId`: The unique ID of the clinical data to delete.
- **Response**: Returns a success message if the clinical data is deleted successfully, otherwise returns a 404 error.

#### GET /patients/critical
- **Description**: Retrieve patients in critical condition based on their latest clinical data.
- **Response**: Returns a list of patients in critical condition.
