FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY . /src/
RUN dotnet publish -c Release -o /app
FROM mcr.microsoft.com/dotnet/runtime:7.0
WORKDIR /app
COPY --from=build /app /app
CMD [ "dotnet", "Worker.dll" ]