FROM mcr.microsoft.com/dotnet/sdk AS build-env
WORKDIR /app
COPY . .
RUN dotnet publish -c Release --property:PublishDir=/out

FROM mcr.microsoft.com/dotnet/aspnet
WORKDIR /app
COPY --from=build-env /out .

ENTRYPOINT dotnet TestApp.dll