---
ms.openlocfilehash: d00b8ecaa61b358e062d85a2b68ca8a95cada442
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803259"
---
### <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="7d979-101">Gheppio: modifiche di configurazione in fase di esecuzione rilevate per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="7d979-101">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="7d979-102">Il gheppio ora reagisce alle modifiche apportate alla `Kestrel` sezione dell'istanza del progetto `IConfiguration` (ad esempio, *appsettings.jsin*) in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d979-102">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="7d979-103">Per altre informazioni su come configurare gheppio usando *appsettings.json*, vedere l' *appsettings.js* ad esempio in [configurazione endpoint](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span><span class="sxs-lookup"><span data-stu-id="7d979-103">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="7d979-104">Il gheppio eseguirà l'associazione, l'annullamento del binding e la riassociazione degli endpoint, se necessario, per rispondere a queste modifiche di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d979-104">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="7d979-105">Per informazioni, vedere Issue [DotNet/aspnetcore # 22807](https://github.com/dotnet/aspnetcore/issues/22807).</span><span class="sxs-lookup"><span data-stu-id="7d979-105">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7d979-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="7d979-106">Version introduced</span></span>

<span data-ttu-id="7d979-107">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="7d979-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7d979-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="7d979-108">Old behavior</span></span>

<span data-ttu-id="7d979-109">Prima di ASP.NET Core 5,0 Preview 6, gheppio non supporta la modifica della configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d979-109">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="7d979-110">In ASP.NET Core 5,0 Preview 6 è possibile acconsentire esplicitamente al comportamento predefinito di reagire alle modifiche di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d979-110">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="7d979-111">È necessario scegliere manualmente la configurazione del gheppio di associazione:</span><span class="sxs-lookup"><span data-stu-id="7d979-111">Opting in required binding Kestrel's configuration manually:</span></span>

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

#### <a name="new-behavior"></a><span data-ttu-id="7d979-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="7d979-112">New behavior</span></span>

<span data-ttu-id="7d979-113">Per impostazione predefinita, gheppio reagisce alle modifiche di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d979-113">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="7d979-114">Per supportare questa modifica, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> chiama `KestrelServerOptions.Configure(IConfiguration, bool)` con `reloadOnChange: true` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7d979-114">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7d979-115">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="7d979-115">Reason for change</span></span>

<span data-ttu-id="7d979-116">È stata apportata la modifica per supportare la riconfigurazione dell'endpoint in fase di esecuzione senza riavviare completamente il server.</span><span class="sxs-lookup"><span data-stu-id="7d979-116">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="7d979-117">A differenza di un riavvio completo del server, gli endpoint non modificati non sono ancora temporaneamente associati.</span><span class="sxs-lookup"><span data-stu-id="7d979-117">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7d979-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="7d979-118">Recommended action</span></span>

* <span data-ttu-id="7d979-119">Per la maggior parte degli scenari in cui la sezione di configurazione predefinita di Gheppio non cambia in fase di esecuzione, questa modifica non ha alcun effetto e non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="7d979-119">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="7d979-120">Per gli scenari in cui la sezione di configurazione predefinita di Gheppio cambia in fase di esecuzione e il gheppio dovrebbe reagire, questo è ora il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="7d979-120">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="7d979-121">Per gli scenari in cui la sezione di configurazione predefinita di Gheppio viene modificata in fase di esecuzione e il gheppio non deve rispondere, è possibile rifiutare esplicitamente come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7d979-121">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

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

<span data-ttu-id="7d979-122">**Note:**</span><span class="sxs-lookup"><span data-stu-id="7d979-122">**Notes:**</span></span>

<span data-ttu-id="7d979-123">Questa modifica non modifica il comportamento dell' `KestrelServerOptions.Configure(IConfiguration)` Overload, che per impostazione predefinita è ancora il `reloadOnChange: false` comportamento.</span><span class="sxs-lookup"><span data-stu-id="7d979-123">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="7d979-124">È inoltre importante assicurarsi che l'origine della configurazione supporti il ricaricamento.</span><span class="sxs-lookup"><span data-stu-id="7d979-124">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="7d979-125">Per le origini JSON, il ricaricamento viene configurato chiamando `AddJsonFile(path, reloadOnChange: true)` .</span><span class="sxs-lookup"><span data-stu-id="7d979-125">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="7d979-126">Il ricaricamento è già configurato per impostazione predefinita per *appsettings.json* e *appSettings. { Environment}. JSON*.</span><span class="sxs-lookup"><span data-stu-id="7d979-126">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

#### <a name="category"></a><span data-ttu-id="7d979-127">Category</span><span class="sxs-lookup"><span data-stu-id="7d979-127">Category</span></span>

<span data-ttu-id="7d979-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7d979-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7d979-129">API interessate</span><span class="sxs-lookup"><span data-stu-id="7d979-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
