# NeXroll Intros for Jellyfin 10.10

Builds the NeXroll Intros plugin for Jellyfin 10.10.x servers. It compiles the
same sources as the 10.11 plugin in `../NeXroll.Jellyfin`, against the 10.10.0
Jellyfin packages on .NET 8.

The only source difference is the `User` entity namespace, which is
`Jellyfin.Data.Entities` on 10.10 and `Jellyfin.Database.Implementations.Entities`
on 10.11. The `JELLYFIN1010` symbol selects it in `NexrollIntroProvider.cs`.

The assembly version comes from `../NeXroll.Jellyfin/Properties/AssemblyInfo.cs`.
Keep `meta.json` "version" in step with it; `package.ps1` fails if they differ.

```powershell
./package.ps1
```

Produces `NeXroll.Jellyfin1010-<version>.zip` with the DLL, `meta.json`, and
`thumb.png`.
