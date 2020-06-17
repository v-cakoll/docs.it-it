---
ms.openlocfilehash: d00b8ecaa61b358e062d85a2b68ca8a95cada442
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803259"
---
### <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a>Gheppio: modifiche di configurazione in fase di esecuzione rilevate per impostazione predefinita

Il gheppio ora reagisce alle modifiche apportate alla `Kestrel` sezione dell'istanza del progetto `IConfiguration` (ad esempio, *appsettings.jsin*) in fase di esecuzione. Per altre informazioni su come configurare gheppio usando *appsettings.json*, vedere l' *appsettings.js* ad esempio in [configurazione endpoint](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).

Il gheppio eseguirà l'associazione, l'annullamento del binding e la riassociazione degli endpoint, se necessario, per rispondere a queste modifiche di configurazione.

Per informazioni, vedere Issue [DotNet/aspnetcore # 22807](https://github.com/dotnet/aspnetcore/issues/22807).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="old-behavior"></a>Comportamento precedente

Prima di ASP.NET Core 5,0 Preview 6, gheppio non supporta la modifica della configurazione in fase di esecuzione.

In ASP.NET Core 5,0 Preview 6 è possibile acconsentire esplicitamente al comportamento predefinito di reagire alle modifiche di configurazione in fase di esecuzione. È necessario scegliere manualmente la configurazione del gheppio di associazione:

```csharp
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args) =>
        CreateHostBuilder(args).Build().Run();

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

#### <a name="new-behavior"></a>Nuovo comportamento

Per impostazione predefinita, gheppio reagisce alle modifiche di configurazione in fase di esecuzione. Per supportare questa modifica, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> chiama `KestrelServerOptions.Configure(IConfiguration, bool)` con `reloadOnChange: true` per impostazione predefinita.

#### <a name="reason-for-change"></a>Motivo della modifica

È stata apportata la modifica per supportare la riconfigurazione dell'endpoint in fase di esecuzione senza riavviare completamente il server. A differenza di un riavvio completo del server, gli endpoint non modificati non sono ancora temporaneamente associati.

#### <a name="recommended-action"></a>Azione consigliata

* Per la maggior parte degli scenari in cui la sezione di configurazione predefinita di Gheppio non cambia in fase di esecuzione, questa modifica non ha alcun effetto e non è necessaria alcuna azione.
* Per gli scenari in cui la sezione di configurazione predefinita di Gheppio cambia in fase di esecuzione e il gheppio dovrebbe reagire, questo è ora il comportamento predefinito.
* Per gli scenari in cui la sezione di configurazione predefinita di Gheppio viene modificata in fase di esecuzione e il gheppio non deve rispondere, è possibile rifiutare esplicitamente come indicato di seguito:

    ```csharp
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

**Note:**

Questa modifica non modifica il comportamento dell' `KestrelServerOptions.Configure(IConfiguration)` Overload, che per impostazione predefinita è ancora il `reloadOnChange: false` comportamento.

È inoltre importante assicurarsi che l'origine della configurazione supporti il ricaricamento. Per le origini JSON, il ricaricamento viene configurato chiamando `AddJsonFile(path, reloadOnChange: true)` . Il ricaricamento è già configurato per impostazione predefinita per *appsettings.json* e *appSettings. { Environment}. JSON*.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
