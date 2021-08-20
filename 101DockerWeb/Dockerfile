#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:3.1 
WORKDIR /src
COPY ["101DockerWeb/101DockerWeb.csproj", "101DockerWeb/"]
RUN dotnet restore "101DockerWeb/101DockerWeb.csproj"
COPY . .
WORKDIR "/src/101DockerWeb"
RUN dotnet build "101DockerWeb.csproj" -c Release -o /app/build
ENTRYPOINT ["dotnet", "101DockerWeb.dll"]

