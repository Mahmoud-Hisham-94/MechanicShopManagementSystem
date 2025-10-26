# 🔧 Mechanic Shop Management System

[![.NET](https://img.shields.io/badge/.NET-9.0-512BD4?style=for-the-badge&logo=.net)](https://dotnet.microsoft.com/)
[![Blazor](https://img.shields.io/badge/Blazor-WebAssembly-512BD4?style=for-the-badge&logo=blazor)](https://blazor.net/)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

A modern, full-featured mechanic shop management system built with **Clean Architecture** principles, featuring a Blazor WebAssembly frontend and ASP.NET Core Web API backend.

## 🚀 Features

### 👥 Customer Management
- **Customer Profiles**: Complete customer information management
- **Vehicle Registry**: Track customer vehicles with detailed specifications
- **Service History**: Comprehensive maintenance and repair history

### 🛠️ Work Order Management
- **Work Order Creation**: Streamlined work order workflow
- **Task Assignment**: Assign repair tasks to mechanics
- **Progress Tracking**: Real-time work order status updates
- **Service Bay Management**: Optimize shop floor operations

### 💰 Billing & Invoicing
- **Automated Billing**: Generate invoices from completed work orders
- **Line Item Management**: Detailed breakdown of parts and labor
- **Payment Tracking**: Monitor payment status and history

### 👨‍🔧 Employee Management
- **Staff Profiles**: Manage mechanic and staff information
- **Role-based Access**: Secure access control system
- **Performance Tracking**: Monitor employee productivity

### 📊 Dashboard & Reporting
- **Real-time Analytics**: Live business metrics and KPIs
- **Performance Insights**: Track shop efficiency and profitability
- **Custom Reports**: Generate detailed business reports

### 🔄 Real-time Updates
- **Live Notifications**: Instant updates via SignalR
- **Status Changes**: Real-time work order and task updates
- **Team Collaboration**: Enhanced communication between staff

## 🏗️ Architecture

This application follows **Clean Architecture** principles with clear separation of concerns:

```
🏢 MechanicShop.Api          # Web API & Blazor Host
🖥️  MechanicShop.Client       # Blazor WebAssembly SPA
⚡ MechanicShop.Application   # Business Logic & Use Cases
🏛️  MechanicShop.Domain       # Domain Entities & Business Rules
🔧 MechanicShop.Infrastructure # Data Access & External Services
📋 MechanicShop.Contracts     # API Contracts & DTOs
```

## 🛠️ Technology Stack

### Backend
- **Framework**: ASP.NET Core 9.0 Web API
- **Database**: SQL Server with Entity Framework Core
- **Authentication**: JWT-based authentication system
- **Real-time**: SignalR for live updates
- **API Documentation**: OpenAPI/Swagger with Scalar UI

### Frontend
- **Framework**: Blazor WebAssembly
- **State Management**: Built-in Blazor state management
- **Authentication**: WebAssembly Authentication API
- **Real-time**: SignalR Client

### DevOps & Monitoring
- **Containerization**: Docker & Docker Compose
- **Monitoring**: OpenTelemetry, Prometheus, Grafana
- **Logging**: Structured logging with Seq
- **API Versioning**: ASP.NET Core API Versioning

### Testing
- **Unit Tests**: Comprehensive domain and application testing
- **Integration Tests**: API endpoint testing
- **Subcutaneous Tests**: End-to-end application testing

## 🚀 Quick Start

### Prerequisites
- [.NET 9.0 SDK](https://dotnet.microsoft.com/download/dotnet/9.0)
- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- [SQL Server](https://www.microsoft.com/sql-server) (or use Docker container)

### Option 1: Docker Compose (Recommended)

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/mechanic-shop-management-system.git
   cd mechanic-shop-management-system
   ```

2. **Start all services**
   ```bash
   docker-compose up -d
   ```

3. **Access the application**
   - **Web Application**: http://localhost:5001
   - **API Documentation**: http://localhost:5001/scalar/v1
   - **Seq Logs**: http://localhost:8081
   - **Prometheus**: http://localhost:9090
   - **Grafana**: http://localhost:3000 (admin/YourStrongPwd)

### Option 2: Local Development

1. **Clone and restore**
   ```bash
   git clone https://github.com/yourusername/mechanic-shop-management-system.git
   cd mechanic-shop-management-system
   dotnet restore
   ```

2. **Update connection string**
   ```json
   // src/MechanicShop.Api/appsettings.Development.json
   {
     "ConnectionStrings": {
       "DefaultConnection": "YourSqlServerConnectionString"
     }
   }
   ```

3. **Run database migrations**
   ```bash
   dotnet ef database update --project src/MechanicShop.Infrastructure
   ```

4. **Start the application**
   ```bash
   dotnet run --project src/MechanicShop.Api
   ```

## 🏗️ Development

### Project Structure
```
📁 src/
├── 🏢 MechanicShop.Api/           # Web API project
├── 🖥️ MechanicShop.Client/        # Blazor WebAssembly client
├── ⚡ MechanicShop.Application/   # Application services & use cases
├── 🏛️ MechanicShop.Domain/        # Domain entities & business logic
├── 🔧 MechanicShop.Infrastructure/ # Data access & infrastructure
└── 📋 MechanicShop.Contracts/     # Shared contracts & DTOs

📁 tests/
├── 🧪 MechanicShop.Api.IntegrationTests/
├── 🧪 MechanicShop.Application.SubcutaneousTests/
├── 🧪 MechanicShop.Application.UnitTests/
├── 🧪 MechanicShop.Domain.UnitTests/
└── 🧪 MechanicShop.Tests.Common/
```

### Building & Testing
```bash
# Build the solution
dotnet build

# Run all tests
dotnet test

# Run with coverage
dotnet test --collect:"XPlat Code Coverage"
```

### API Testing
Use the provided HTTP requests in the `requests/` folder:
```bash
# Test API endpoints
GET {{baseUrl}}/api/v1/customers
GET {{baseUrl}}/api/v1/workorders
POST {{baseUrl}}/api/v1/workorders
```

## 📊 Monitoring & Observability

The system includes comprehensive monitoring and observability:

- **📈 Metrics**: Prometheus metrics collection
- **📊 Dashboards**: Pre-configured Grafana dashboards
- **📝 Logging**: Structured logging with Seq
- **🔍 Tracing**: OpenTelemetry distributed tracing
- **🩺 Health Checks**: Application and database health monitoring

Access monitoring tools:
- **Grafana**: http://localhost:3000
- **Prometheus**: http://localhost:9090
- **Seq**: http://localhost:8081

## 🤝 Contributing

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

## 📋 Roadmap

- [ ] **Mobile App**: React Native mobile application
- [ ] **Inventory Management**: Parts and tools inventory system
- [ ] **Appointment Scheduling**: Customer appointment booking system
- [ ] **SMS Notifications**: Customer notification system
- [ ] **Reporting Engine**: Advanced reporting and analytics
- [ ] **Multi-tenant Support**: Support for multiple shop locations

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with ❤️ using **Clean Architecture** principles
- **ASP.NET Core** and **Blazor** teams for amazing frameworks
- **Entity Framework** team for excellent ORM
- Open source community for inspiration and tools

---

<div align="center">
  <strong>⭐ If you found this project helpful, please give it a star! ⭐</strong>
</div>