FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:6.0
EXPOSE 5272

WORKDIR /app

ENV ASPNETCORE_URLS="http://localhost:5272"

COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "weather-api.dll"]