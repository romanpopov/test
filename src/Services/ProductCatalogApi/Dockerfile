FROM microsoft/dotnet:2.2-sdk as build

WORKDIR /code

COPY . .
RUN dotnet restore
RUN dotnet publish --output /out/ --configuration Release

FROM microsoft/dotnet:2.2-aspnetcore-runtime
COPY --from=build /out /app/
WORKDIR  /app
EXPOSE 80/tcp
ENTRYPOINT ["dotnet","ProductCatalogApi.dll"]

