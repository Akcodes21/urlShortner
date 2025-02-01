# URL Shortener Application

## Overview
This project is a URL Shortener application built with **Spring Boot**. It enables users to convert long URLs into shorter, manageable links and supports redirection to the original links. Additionally, URLs can be set with expiration times for added functionality.

---

## Features
- Generate short URLs for any given long URL.
- Redirect users from short URLs to the original URLs.
- Set expiration dates for short URLs.
- Error handling for invalid or expired URLs.

---

## Technologies Used
- **Spring Boot**: Framework for building REST APIs.
- **JPA**: Database interactions.
- **Google Guava**: Generating hash-based short URLs.
- **H2 Database (In-Memory)**: Database for testing.
- **Maven**: Dependency management.

---

## Project Structure
- **Controller Layer:**
  - `UrlShorteningController`: Manages API endpoints for URL generation and redirection.

- **Model Layer:**
  - `Url`: Entity for storing URL information.
  - `UrlResponseDto`: DTO for success responses.
  - `UrlErrorResponseDto`: DTO for error responses.

- **Service Layer:**
  - `UrlService`: Interface for URL operations.
  - `UrlServiceImpl`: Implementation of URL operations.

- **Repository Layer:**
  - `UrlRepository`: Manages database interactions.

- **Main Application:**
  - `UrlShortnerApplication`: Entry point for running the Spring Boot application.

---

## API Endpoints

### 1. Generate Short URL
**POST:** `/generate`

**Request Body:**
```json
{
  "url": "https://github.com/Akcodes21"  
}
```

**Response:**
- success:
```json
{
    "originalUrl": "https://github.com/Akcodes21",
    "shortLink": "b39ff76e",
    "expirationDate": "2025-02-01T07:37:54.6933075"
}
```
- error:
```json
{
  "status": "404",
  "error": "There was an error"
}
```
### 2. Redirect to Original URL
**GET:** `/{shortLink}`
- response:
Redirects to original URL.

---
## Running the Application
### Prerequisites
- Java 17 or higher
- Maven 3.6+

### Steps to Run
#### Clone the repository: 
```json
git clone <repository-url>
cd <repository-folder>
```
#### Build the project using Maven:
```json
mvn clean install
```
#### Run the application:

```json 
mvn spring-boot:run
```

Access the application at ```http://localhost:8080```.

---
## Error Handling
- **Invalid URL:** Returns a `400` error.
- **Expired URL:** Returns a `400` error indicating that the URL has expired.
- **Non-existent Short Link:** Returns a `404` error.

---

## Future Improvements
- Support for custom short URLs.
- User authentication for managing URLs.
- Improved error handling and validation.
- Integration with frontend UI.

---

## License
This project is open-source and available under the [MIT License](LICENSE).





