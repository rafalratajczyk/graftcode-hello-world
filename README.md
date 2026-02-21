Running the project locally with Graftcode Gateway
Prerequisites
- .NET SDK (matching the project version, e.g. .NET 9)
- Graftcode Gateway (gg) installed and available in PATH
- A valid Project Key from the Graftcode Portal


1. From the project root directory:
cd HelloService
dotnet publish -c Release

This will generate the compiled assembly at:
bin/Release/net9.0/publish/HelloService.dll

2. Run the Gateway and point it directly to the compiled .dll:

gg --projectKey YOUR_PROJECT_KEY \
   --modules ./HelloService/bin/Release/net9.0/publish/HelloService.dll


If everything is configured correctly, the Gateway will:
- connect to Graftcode using the Project Key
- load the local .NET module
- expose public methods for remote access
