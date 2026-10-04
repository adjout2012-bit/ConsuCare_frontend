# ConsuCare Frontend

Blazor WebAssembly client for ConsuCare, a peer-support platform for people navigating chronic illness.

## Local development

This repository includes a copy of `ConsuCare.Shared` so the frontend builds independently of the backend repository.

```powershell
dotnet run --project src\ConsuCare.Client\ConsuCare.Client.csproj
```

The development settings point to `http://localhost:5180`. Configure `ApiBaseUrl` in `src\ConsuCare.Client\wwwroot\appsettings.json` to the deployed backend URL before a production deployment. Until a backend is deployed and reachable, API-backed actions are unavailable.

## Vercel

Import this repository into Vercel. `vercel.json` configures the **Other** framework preset, build command `bash build-vercel.sh`, and output directory `src/ConsuCare.Client/bin/Release/net8.0/publish/wwwroot`. The rewrite sends client-side routes to the Blazor app.

## Shared contracts

`src/ConsuCare.Shared` is also copied into the backend repository. Keep DTO and model changes synchronized in both repositories when the API contract changes.
