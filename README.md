# 1. Create solution & projects

// NOTE: The "ProjectName.Template" is th name of solution aka sln.

dotnet new sln -n ProjectName.Template

dotnet new webapi -n ProjectName.Api -f net8.0
dotnet new classlib -n ProjectName.Application -f net8.0
dotnet new classlib -n ProjectName.Domain -f net8.0
dotnet new classlib -n ProjectName.Infrastructure -f net8.0
dotnet new classlib -n ProjectName.Shared -f net8.0

# 2. Add projects to solution

dotnet sln add ProjectName.Api/ProjectName.Api.csproj
dotnet sln add ProjectName.Application/ProjectName.Application.csproj
dotnet sln add ProjectName.Domain/ProjectName.Domain.csproj
dotnet sln add ProjectName.Infrastructure/ProjectName.Infrastructure.csproj
dotnet sln add ProjectName.Shared/ProjectName.Shared.csproj

# 3. Add project references

// Api
dotnet add ProjectName.Api/ProjectName.Api.csproj reference ProjectName.Application/ProjectName.Application.csproj
dotnet add ProjectName.Api/ProjectName.Api.csproj reference ProjectName.Infrastructure/ProjectName.Infrastructure.csproj
dotnet add ProjectName.Api/ProjectName.Api.csproj reference ProjectName.Shared/ProjectName.Shared.csproj

// Application
dotnet add ProjectName.Application/ProjectName.Application.csproj reference ProjectName.Domain/ProjectName.Domain.csproj
dotnet add ProjectName.Application/ProjectName.Application.csproj reference ProjectName.Shared/ProjectName.Shared.csproj

// Infrastructure
dotnet add ProjectName.Infrastructure/ProjectName.Infrastructure.csproj reference ProjectName.Application/ProjectName.Application.csproj
dotnet add ProjectName.Infrastructure/ProjectName.Infrastructure.csproj reference ProjectName.Domain/ProjectName.Domain.csproj
dotnet add ProjectName.Infrastructure/ProjectName.Infrastructure.csproj reference ProjectName.Shared/ProjectName.Shared.csproj

// Domain
dotnet add ProjectName.Domain/ProjectName.Domain.csproj reference ProjectName.Shared/ProjectName.Shared.csproj

# 4. Add Nugget Package

# 5. Create folders inside projects

// Api layer
mkdir -p ProjectName.Api/Controllers
mkdir -p ProjectName.Api/Middleware
mkdir -p ProjectName.Api/Filters
mkdir -p ProjectName.Api/Contracts/Requests
mkdir -p ProjectName.Api/Contracts/Responses
mkdir -p ProjectName.Api/Extensions


// Application layer
mkdir -p ProjectName.Application/Interfaces
mkdir -p ProjectName.Application/Services
mkdir -p ProjectName.Application/DTOs
mkdir -p ProjectName.Application/Behaviors


// Domain layer
mkdir -p ProjectName.Domain/Entities
mkdir -p ProjectName.Domain/ValueObjects
mkdir -p ProjectName.Domain/Aggregates
mkdir -p ProjectName.Domain/Events
mkdir -p ProjectName.Domain/Services
mkdir -p ProjectName.Domain/Exceptions
mkdir -p ProjectName.Domain/Specifications


// Infrastructure layer
mkdir -p ProjectName.Infrastructure/Data/Configurations
mkdir -p ProjectName.Infrastructure/Data/Repositories
mkdir -p ProjectName.Infrastructure/Data/Migrations
mkdir -p ProjectName.Infrastructure/Messaging
mkdir -p ProjectName.Infrastructure/Caching
mkdir -p ProjectName.Infrastructure/Security
mkdir -p ProjectName.Infrastructure/Services
mkdir -p ProjectName.Infrastructure/Extensions


// Shared layer
mkdir -p ProjectName.Shared/Constants
mkdir -p ProjectName.Shared/Enums
mkdir -p ProjectName.Shared/Models
mkdir -p ProjectName.Shared/Extensions
