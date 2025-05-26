# RRA Vehicle Management System

A comprehensive vehicle management system for the Rwanda Revenue Authority (RRA), built with Spring Boot. This system handles vehicle registration, ownership transfers, and plate number management.

## Features

- 🔐 **Authentication & Authorization**
  - User registration and login
  - JWT-based authentication
  - Role-based access control
  - OTP-based account verification
  - Password reset functionality

- 🚗 **Vehicle Management**
  - Vehicle registration
  - Plate number management
  - Ownership transfer tracking
  - Vehicle history

- 👤 **Owner Management**
  - Owner registration
  - Automatic plate number generation
  - Owner search functionality
  - Owner-vehicle association

- 📧 **Email Notifications**
  - Account verification emails
  - Password reset emails
  - Plate creation notifications
  - Ownership transfer notifications

## Tech Stack

- **Backend**
  - Java 17
  - Spring Boot 3.x
  - Spring Security
  - Spring Data JPA
  - PostgreSQL
  - Redis (for OTP management)
  - JWT for authentication
  - Thymeleaf (for email templates)

- **Documentation**
  - Swagger/OpenAPI
  - SpringDoc

## Prerequisites

- Java 17 or higher
- Maven
- PostgreSQL
- Redis
- SMTP server (for email functionality)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/BYUMVUHOREAimable/RRAVehicleMS.git
   cd RRAVehicleMS
   ```

2. **Configure PostgreSQL**
   - Create a database named `rra_vehicles`
   - Update `application.properties` with your database credentials

3. **Configure Redis**
   - Install Redis on your system
   - Default configuration uses localhost:6379

4. **Configure Email Settings**
   - Update email configuration in `application.properties`
   - Configure SMTP settings for your email provider

5. **Build the project**
   ```bash
   mvn clean install
   ```

6. **Run the application**
   ```bash
   mvn spring-boot:run
   ```

## API Documentation

Access the Swagger UI at: http://localhost:9094/swagger-ui/index.html

### Key Endpoints

#### Authentication
- `POST /api/v1/auth/register` - Register new user
- `POST /api/v1/auth/login` - User login
- `PATCH /api/v1/auth/verify-account` - Verify account with OTP
- `POST /api/v1/auth/initiate-password-reset` - Request password reset
- `PATCH /api/v1/auth/reset-password` - Reset password with OTP

#### Vehicle Management
- `POST /api/v1/vehicles` - Register new vehicle
- `GET /api/v1/vehicles/{id}` - Get vehicle details
- `GET /api/v1/vehicles/owner/{ownerId}` - Get vehicles by owner

#### Owner Management
- `POST /api/v1/owners` - Register new owner
- `GET /api/v1/owners/{id}` - Get owner details
- `GET /api/v1/owners/search` - Search owners

#### Plate Management
- `POST /api/v1/plates` - Register new plate
- `GET /api/v1/plates/owner/{ownerId}` - Get plates by owner

#### Ownership Transfer
- `POST /api/v1/ownership/transfer` - Transfer vehicle ownership
- `GET /api/v1/ownership/history/plate/{plateNumber}` - Get ownership history by plate
- `GET /api/v1/ownership/history/chassis/{chassisNumber}` - Get ownership history by chassis

## Security Features

- Rate limiting for API endpoints
- JWT-based authentication
- Password encryption
- OTP-based verification
- Role-based access control

## Rate Limiting

- Authentication endpoints: 10 requests per 30 seconds
- OTP endpoints: 2 requests per 10 minutes

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Author

- **BYUMVUHORE Aimable**
- Email: aimablebyumvuhore@gmail.com

## Acknowledgments

- Rwanda Revenue Authority (RRA)
- Spring Boot Team
- All contributors and maintainers 