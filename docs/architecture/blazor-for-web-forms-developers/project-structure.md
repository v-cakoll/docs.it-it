---
title: Struttura del progetto per le app Blazor
description: Informazioni sul confronto tra le strutture di progetto di ASP.NET Web Form e progetti Blazor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401578"
---
# <a name="project-structure-for-blazor-apps"></a>Struttura del progetto per le app Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nonostante le differenze significative della struttura del progetto, ASP.NET Web Form e Blazor condividono molti concetti simili. Qui, esamineremo la struttura di un progetto Blazor e confrontarlo con un progetto Web Form ASP.NET.

Per creare la tua prima app Blazor, segui le istruzioni nella procedura introduttiva di [Blazor.](/aspnet/core/blazor/get-started) È possibile seguire le istruzioni per creare un'app Blazor Server o un'app Blazor WebAssembly ospitata in ASP.NET Core.You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core. Ad eccezione della logica specifica del modello di hosting, la maggior parte del codice in entrambi i progetti è lo stesso.

## <a name="project-file"></a>File di progetto

Le app per server Blazor sono progetti .NET Core. Il file di progetto per l'app Blazor Server è semplice come si può ottenere:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Il file di progetto per un'app Blazor WebAssembly sembra leggermente più complesso (i numeri di versione esatti possono variare):

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

I progetti WebAssembly Blazor sono destinati a .NET Standard anziché a .NET Core perché vengono eseguiti nel browser in un runtime .NET basato su WebAssembly. Non è possibile installare .NET in un browser Web come si può su un server o un computer di sviluppo. Di conseguenza, il progetto fa riferimento al framework Blazor utilizzando singoli riferimenti al pacchetto.

In confronto, un progetto Web Form ASP.NET predefinito include quasi 300 righe di codice XML nel relativo file *con estensione csproj,* la maggior parte dei quali elenca in modo esplicito i vari file di codice e di contenuto nel progetto. Molte delle semplificazioni nei progetti basati su .NET Core e .NET Standard provengono dalle destinazioni `Microsoft.NET.Sdk.Web` e dalle proprietà predefinite importate facendo riferimento all'SDK, spesso definito semplicemente Web SDK. Web SDK include caratteri jolly e altre funzionalità che semplificano l'inclusione di file di codice e di contenuto nel progetto. Non è necessario elencare i file in modo esplicito. Quando è destinato a .NET Core, Web SDK aggiunge anche riferimenti a framework sia per .NET Core che per ASP.NET framework condivisi. I framework sono visibili dal nodo **Framework dipendenze** > **Frameworks** nella finestra **Esplora soluzioni.** The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.

Sebbene siano supportati, i singoli riferimenti agli assembly sono meno comuni nei progetti .NET Core.Although they're supported, individual assembly references are less common in .NET Core projects. La maggior parte delle dipendenze di progetto vengono gestite come riferimenti al pacchetto NuGet.Most project dependencies are handled as NuGet package references. È sufficiente fare riferimento alle dipendenze dei pacchetti di primo livello nei progetti .NET Core.You only need to reference top-level package dependencies in .NET Core projects. Le dipendenze transitive vengono incluse automaticamente. Anziché utilizzare il file *packages.config* comunemente disponibile nei progetti Web Form di ASP.NET `<PackageReference>` fare riferimento ai pacchetti, i riferimenti ai pacchetti vengono aggiunti al file di progetto utilizzando l'elemento .

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Punto di ingresso

Il punto di ingresso dell'app Blazor Server è definito nel file *di Program.cs,* come si vedrebbe in un'app console. Quando l'app viene eseguita, crea ed esegue un'istanza dell'host Web usando valori predefiniti specifici per le app Web. L'host Web gestisce il ciclo di vita dell'app Blazor Server e configura i servizi a livello di host. Esempi di tali servizi sono la configurazione, la registrazione, l'inserimento delle dipendenze e il server HTTP. Questo codice è per lo più boilerplate e viene spesso lasciato invariato.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

Le app Blazor WebAssembly definiscono anche un punto di ingresso in *Program.cs*. Il codice ha un aspetto leggermente diverso. Il codice è simile in quanto sta configurando l'host dell'app per fornire gli stessi servizi a livello di host all'app. L'host dell'app WebAssembly, tuttavia, non configura un server HTTP perché viene eseguito direttamente nel browser.

Le app Blazor hanno una `Startup` classe anziché un file *Global.asax* per definire la logica di avvio per l'app. La `Startup` classe viene utilizzata per configurare l'app e tutti i servizi specifici dell'app. Nell'app Blazor Server, la `Startup` classe viene utilizzata per configurare l'endpoint per la connessione in tempo reale utilizzata da Blazor tra i browser client e il server. Nell'app Blazor WebAssembly, la `Startup` classe definisce i componenti radice per l'app e la posizione in cui deve essere eseguito il rendering. Esamineremo più a fondo `Startup` la classe nella sezione [Avvio](./app-startup.md) app.

## <a name="static-files"></a>File statici

A differenza di ASP.NET progetti Web Form, non tutti i file in un progetto Blazor possono essere richiesti come file statici. Solo i file nella cartella *wwwroot* sono indirizzabili sul Web. Questa cartella si riferisce alla "radice web" dell'app. Qualsiasi elemento al di fuori della radice web dell'app *non è* indirizzabile al Web. Questa configurazione fornisce un ulteriore livello di sicurezza che impedisce l'esposizione accidentale di file di progetto sul Web.

## <a name="configuration"></a>Configurazione

La configurazione in ASP.NET app Web Form viene in genere gestita utilizzando uno o più file *web.config.* Le app Blazor in genere non dispongono di file *web.config.* In caso affermativo, il file viene utilizzato solo per configurare le impostazioni specifiche di IIS quando è ospitato in IIS. Al contrario, le app Blazor Server usano le astrazioni di configurazione ASP.NET Core (le app Blazor WebAssembly non supportano attualmente le stesse astrazioni di configurazione, ma che potrebbero essere una funzionalità aggiunta in futuro). Ad esempio, l'app predefinita Blazor Server memorizza alcune impostazioni in *appsettings.json*.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

Ulteriori informazioni sulla configurazione verranno fornite in progetti ASP.NET Base nella sezione Configurazione.We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.

## <a name="razor-components"></a>Componenti Razor

La maggior parte dei file nei progetti Blazor sono file *.razor.* Razor è un linguaggio di modelli basato su HTML e C , che viene utilizzato per generare dinamicamente l'interfaccia utente Web. I file *.razor* definiscono i componenti che costituiscono l'interfaccia utente dell'app. Per la maggior parte, i componenti sono identici per le applicazioni Blazor Server e Blazor WebAssembly. I componenti in Blazor sono analoghi ai controlli utente in ASP.NET Web Form.

Ogni file del componente Razor viene compilato in una classe .NET quando il progetto viene compilato. La classe generata acquisisce lo stato del componente, la logica di rendering, i metodi del ciclo di vita, i gestori eventi e altre logiche. Esamineremo i componenti di creazione nella sezione [Building reusable UI components with Blazor.](./components.md)

I file *_Imports.razor* non sono file di componenti Razor. Al contrario, definiscono un set di direttive Razor da importare in altri file *.razor* all'interno della stessa cartella e nelle relative sottocartelle. Ad esempio, un file *_Imports.razor* è `using` un modo convenzionale per aggiungere istruzioni per gli spazi dei nomi di uso comune:For example, a _Imports.razor file is a conventional way to add statements for commonly used namespaces:

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>Pagine

Dove sono le pagine nelle applicazioni Blazor? Blazor non definisce un'estensione di file separata per le pagine indirizzabili, ad esempio i file *aspx* in ASP.NET applicazioni Web Form. Al contrario, le pagine vengono definite assegnando cicli di lavorazione ai componenti. Una route viene in `@page` genere assegnata utilizzando la direttiva Razor.A route is typically assigned using the Razor directive. Ad esempio, `Counter` il componente creato nel file *Pages/Counter.razor* definisce la seguente route:

```razor
@page "/counter"
```

Il routing in Blazor viene gestito sul lato client, non sul server. Quando l'utente si sposta nel browser, Blazor intercetta la navigazione e quindi esegue il rendering del componente con la route corrispondente.

Le route dei componenti non vengono attualmente dedotte dal percorso del file del componente come sono con le pagine *aspx.* Questa funzionalità potrebbe essere aggiunta in futuro. Ogni route deve essere specificata in modo esplicito nel componente. L'archiviazione dei componenti instradabili in una cartella *Pages* non ha alcun significato speciale ed è puramente una convenzione.

Esamineremo più in dettaglio il routing in Blazor nella sezione [Pagine, routing e layout.](./pages-routing-layouts.md)

## <a name="layout"></a>Layout

Nelle app Web Form ASP.NET il layout di pagina comune viene gestito utilizzando le pagine master (*Site.Master*). Nelle app Blazor il layout di pagina viene gestito utilizzando i componenti di layout (*Shared/MainLayout.razor*). I componenti di layout verranno descritti in modo più dettagliato nella sezione [Pagina, instradamento e layout.](./pages-routing-layouts.md)

## <a name="bootstrap-blazor"></a>Bootstrap Blazor

Per bootstrap Blazor, l'applicazione deve:

- Specificare dove deve essere eseguito il rendering del componente radice (*App.Razor*).
- Aggiungere lo script del framework Blazor corrispondente.

Nell'app Blazor Server, la pagina host del componente radice è definita nel file *_Host.cshtml.* Questo file definisce una pagina Razor, non un componente. Le pagine Razor utilizzano la sintassi Razor per definire una pagina indirizzabile al server, molto simile a una pagina *aspx.* Il `Html.RenderComponentAsync<TComponent>(RenderMode)` metodo viene utilizzato per definire dove deve essere eseguito il rendering di un componente a livello di radice. L'opzione `RenderMode` indica il modo in cui deve essere eseguito il rendering del componente. Nella tabella seguente vengono `RenderMode` descritte le opzioni supportate.

|Opzione                        |Descrizione       |
|------------------------------|------------------|
|`RenderMode.Server`           |Rendering interattivo una volta stabilita una connessione con il browser|
|`RenderMode.ServerPrerendered`|Prima il prerendering e quindi il rendering in modo interattivo|
|`RenderMode.Static`           |Rendering come contenuto statico|

Il riferimento allo script *di _framework/blazor.server.js* stabilisce la connessione in tempo reale con il server e quindi gestisce tutte le interazioni utente e gli aggiornamenti dell'interfaccia utente.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

Nell'app Blazor WebAssembly la pagina host è un semplice file HTML statico *wwwroot/index.html*. L'elemento `<app>` viene utilizzato per indicare dove deve essere eseguito il rendering del componente radice.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

Il componente specifico di cui eseguire `Startup.Configure` il rendering viene configurato nel metodo dell'app con un selettore CSS corrispondente che indica dove deve essere eseguito il rendering del componente.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>Output della compilazione

Quando viene compilato un progetto Blazor, tutti i file di codice e di componente Razor vengono compilati in un unico assembly. A differenza ASP.NET progetti Web Form, Blazor non supporta la compilazione in fase di esecuzione della logica dell'interfaccia utente.

## <a name="run-the-app"></a>Eseguire l'app

Per eseguire l'app Blazor Server, premere `F5` in Visual Studio. Le app Blazor non supportano la compilazione di runtime. Per visualizzare i risultati delle modifiche al markup del codice e del componente, ricompilare e riavviare l'app con il debugger collegato. Se si esegue senza il`Ctrl+F5`debugger collegato ( ), Visual Studio controlla le modifiche ai file e riavvia l'app quando vengono apportate modifiche. Aggiornare manualmente il browser quando vengono apportate modifiche.

Per eseguire l'app Blazor WebAssembly, scegliere uno degli approcci seguenti:

- Eseguire il progetto client direttamente utilizzando il server di sviluppo.
- Eseguire il progetto server quando si ospita l'app con ASP.NET Core.

Le app Blazor WebAssembly non supportano il debug con Visual Studio. Per eseguire l'app, utilizzare `Ctrl+F5` instead di `F5`. È invece possibile eseguire il debug delle applicazioni WebAssembly Blazor direttamente nel browser. Per informazioni dettagliate, vedere [Debug ASP.NET Core Blazor .See Debug ASP.NET Core Blazor.](/aspnet/core/blazor/debug)

>[!div class="step-by-step"]
>[Successivo](hosting-models.md)
>[precedente](app-startup.md)
