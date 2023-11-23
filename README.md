# 2023 Elections Application

This application is designed to simulate the 2023 elections in Argentina. It uses official data provided by the Ministry of the Interior of the Nation Argentina, which has been exposed in a RESTful API.

## Application Overview
The application provides several functionalities:

- **District Information:** The application provides an API that exposes all the districts and allows users to search for a district by its name.

- **Available Positions:** The application provides an API that exposes the data of the positions available to vote for in a given district.

- **Section Information:** The application provides an API that exposes all the sections of a given district or allows users to search for a specific section of a district.

- **Election Results:** The application provides an API that exposes a summary of the election results for a given section and district. The results are ordered from highest to lowest according to the number of votes obtained by each political group. Please note that in the `/resultados` API, only data for district 4 (Córdoba), section 26 (Unión), and position 1 (PRESIDENT AND VICE) will be exposed.

## Running the Application
The application can be run using Docker Compose, which allows you to run multiple Docker containers simultaneously. In this case, two Docker images are used: one for the server and one for the client application.

Here’s a basic example of a `docker-compose.yml` file that can be used to run the application:

```yaml
version: '3'
services:
  server:
    image: tupfrcutn/elecciones-2023:1.0.0
    ports:
      - "8080:8080"
  client:
    build: .
    ports:
      - "8081:8081"
In this example, the server service uses the `tupfrcutn/elecciones-2023:1.0.0` image and exposes port 8080. The client service is built from the `Dockerfile` in the current directory and exposes port 8081.

To run the application, navigate to the directory containing the `docker-compose.yml` file and use the following command:

```bash
docker-compose up
