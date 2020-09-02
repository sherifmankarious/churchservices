dotnet new sln -o ChurchServices

cd ChurchServices
dotnet new mvc -o ChurchServices.Core
dotnet new mvc -o ChurchServices.Events
dotnet sln ChurchServices.sln add ./ChurchServices.Core/ChurchServices.Core.csproj ./ChurchServices.Events/ChurchServices.Events.csproj

cd churchservices.core
dotnet add package OrchardCore.Application.Targets -v 1.0.0-rc2-13450

cd ..
cd churchservices.events
dotnet add package OrchardCore.Module.Targets -v 1.0.0-rc2-13450

dotnet add ./ChurchServices.Core/ChurchServices.Core.csproj reference ./ChurchServices.Events/ChurchServices.Events.csproj