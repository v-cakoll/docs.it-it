---
title: Struttura del progetto per le app Blazer
description: Informazioni su come vengono confrontate le strutture di progetto dei progetti ASP.NET Web Form e blazer.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 7e622663bedce13c93b8d72f5a699d076e8139b7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394773"
---
# <a name="project-structure-for-blazor-apps"></a>Struttura del progetto per le app Blazer

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nonostante le differenze significative della struttura di progetto, ASP.NET Web Forms e blazer condividono molti concetti simili. In questo articolo verrà esaminata la struttura di un progetto blazer e il confronto con un progetto Web Form ASP.NET.

Per creare la prima app blazer, seguire le istruzioni riportate nella procedura introduttiva di [Blazer](/aspnet/core/blazor/get-started). È possibile seguire le istruzioni per la creazione di un'app del server blazer o di un'app webassembly Blazer ospitata in ASP.NET Core. Fatta eccezione per la logica specifica del modello di hosting, la maggior parte del codice in entrambi i progetti è la stessa.

## <a name="project-file"></a>File di progetto

Le app del server blazer sono progetti .NET Core. Il file di progetto per l'app del server blazer è semplice quanto è possibile ottenere:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Il file di progetto per un'app webassembly blazer è leggermente più occupato (i numeri di versione esatti possono variare):

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

I progetti di webassembly Blazer hanno come destinazione .NET Standard anziché .NET Core perché vengono eseguiti nel browser in un Runtime .NET basato su webassembly. Non è possibile installare .NET in un Web browser, ad esempio in un server o in un computer di sviluppo. Di conseguenza, il progetto fa riferimento al Framework di Blaze usando singoli riferimenti ai pacchetti.

Per confronto, un progetto Web Form ASP.NET predefinito include quasi 300 righe di codice XML nel file con estensione *csproj* , la maggior parte dei quali elenca in modo esplicito i vari file di codice e di contenuto del progetto. Molte delle semplificazioni nei progetti basati su .NET Core e .NET Standard provengono dalle destinazioni predefinite e dalle proprietà importate facendo riferimento all' `Microsoft.NET.Sdk.Web` SDK, spesso noto semplicemente come Web SDK. Web SDK include caratteri jolly e altre convenienze che semplificano l'inclusione del codice e dei file di contenuto nel progetto. Non è necessario elencare i file in modo esplicito. Quando la destinazione è .NET Core, Web SDK aggiunge anche riferimenti a Framework sia per .NET Core che ASP.NET Core Framework condivisi. I Framework sono visibili dal nodo Framework **dipendenze**  >  **Frameworks** nella finestra **Esplora soluzioni** . I Framework condivisi sono raccolte di assembly installati nel computer durante l'installazione di .NET Core.

Sebbene siano supportati, i singoli riferimenti ad assembly sono meno comuni nei progetti .NET Core. La maggior parte delle dipendenze del progetto viene gestita come riferimenti ai pacchetti NuGet. È sufficiente fare riferimento alle dipendenze del pacchetto di primo livello nei progetti .NET Core. Le dipendenze transitive vengono incluse automaticamente. Anziché usare il file *packages. config* comunemente presente nei progetti Web Form ASP.NET per fare riferimento ai pacchetti, i riferimenti al pacchetto vengono aggiunti al file di progetto usando l' `<PackageReference>` elemento.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Punto di ingresso

Il punto di ingresso dell'app Server Blazer viene definito nel file *Program.cs* , come si può notare in un'app console. Quando l'app viene eseguita, crea ed esegue un'istanza dell'host web usando le impostazioni predefinite specifiche per le app Web. L'host Web gestisce il ciclo di vita dell'app Server Blaze e configura i servizi a livello di host. Esempi di tali servizi sono configurazione, registrazione, inserimento di dipendenze e il server HTTP. Questo codice è per lo più standard e viene spesso lasciato invariato.

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

Le app webassembly Blazer definiscono anche un punto di ingresso in *Program.cs*. Il codice ha un aspetto leggermente diverso. Il codice è simile in quanto configura l'host dell'applicazione per fornire gli stessi servizi a livello di host all'app. Tuttavia, l'host dell'app webassembly non configura un server HTTP perché viene eseguito direttamente nel browser.

Le app Blazer hanno una `Startup` classe anziché un file *Global. asax* per definire la logica di avvio per l'app. La `Startup` classe viene usata per configurare l'app e tutti i servizi specifici dell'app. Nell'app Server Blazer la `Startup` classe viene usata per configurare l'endpoint per la connessione in tempo reale usata da Blazer tra i browser client e il server. Nell'app webassembly Blazer la `Startup` classe definisce i componenti radice per l'app e la posizione in cui devono essere sottoposti a rendering. Verrà esaminata in maniera più approfondita la `Startup` classe nella sezione relativa all' [avvio dell'app](./app-startup.md) .

## <a name="static-files"></a>File statici

A differenza dei progetti Web Form ASP.NET, non tutti i file in un progetto Blazer possono essere richiesti come file statici. Solo i file nella cartella *wwwroot* sono indirizzabili sul Web. Questa cartella viene definita "radice Web" dell'app. Qualsiasi elemento all'esterno della radice Web dell'app *non è* indirizzabile sul Web. Questa configurazione offre un livello di sicurezza aggiuntivo che impedisce l'esposizione accidentale dei file di progetto sul Web.

## <a name="configuration"></a>Configurazione

La configurazione nelle app Web Form ASP.NET viene in genere gestita usando uno o più file *Web. config* . Le app Blazer non dispongono in genere di file *Web. config* . In caso affermativo, il file viene usato solo per configurare le impostazioni specifiche di IIS se ospitate in IIS. Al contrario, le app del server Blazer usano le astrazioni di configurazione ASP.NET Core (le app webassembly Blazer non supportano attualmente le stesse astrazioni di configurazione, ma potrebbe essere una funzionalità aggiunta in futuro). Ad esempio, l'app Server Blazer predefinita archivia alcune impostazioni in *appSettings. JSON*.

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

Nella sezione [configurazione](./config.md) verranno fornite ulteriori informazioni sulla configurazione nei progetti ASP.NET Core.

## <a name="razor-components"></a>Componenti Razor

La maggior parte dei file nei progetti di blazer sono file con *estensione Razor* . Razor è un linguaggio di modello basato su HTML e C# usato per generare dinamicamente l'interfaccia utente Web. I file con *estensione Razor* definiscono i componenti che costituiscono l'interfaccia utente dell'app. Nella maggior parte dei casi, i componenti sono identici per entrambe le app Blazer server e blazer webassembly. I componenti in blazer sono analoghi ai controlli utente nei Web Form ASP.NET.

Ogni file del componente Razor viene compilato in una classe .NET quando viene compilato il progetto. La classe generata acquisisce lo stato del componente, la logica di rendering, i metodi del ciclo di vita, i gestori eventi e altre logiche. Verranno esaminati i componenti di creazione nella sezione [creazione di componenti dell'interfaccia utente riutilizzabili con blazer](./components.md) .

I file *_Imports. Razor* non sono file componente Razor. Definiscono invece un set di direttive Razor da importare in altri file con *estensione Razor* all'interno della stessa cartella e nelle relative sottocartelle. Ad esempio, un file *_Imports. Razor* è un modo convenzionale per aggiungere `using` direttive per gli spazi dei nomi di uso comune:

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

## <a name="pages"></a>.NET

Dove si trovano le pagine nelle app Blazer? Blazer non definisce un'estensione di file separata per le pagine indirizzabili, ad esempio i file *aspx* nelle app Web Form ASP.NET. Le pagine vengono invece definite assegnando Route ai componenti. Una route viene in genere assegnata usando la `@page` direttiva Razor. Ad esempio, il `Counter` componente creato nel file *pages/Counter. Razor* definisce la route seguente:

```razor
@page "/counter"
```

Il routing in blazer è gestito sul lato client, non sul server. Quando l'utente si sposta nel browser, blazer intercetta la navigazione e quindi esegue il rendering del componente con la route corrispondente.

Le route dei componenti non sono attualmente dedotte dal percorso del file del componente, come avviene con le pagine *aspx* . Questa funzionalità può essere aggiunta in futuro. Ogni route deve essere specificata in modo esplicito nel componente. L'archiviazione di componenti instradabili in una cartella di *pagine* non ha un significato speciale ed è puramente una convenzione.

Verranno esaminati più dettagliatamente il routing in blazer nella sezione [pagine, routing e layout](./pages-routing-layouts.md) .

## <a name="layout"></a>Layout

Nelle app Web Form ASP.NET, il layout di pagina comune viene gestito usando le pagine master (*site. master*). Nelle app Blazer il layout di pagina viene gestito usando i componenti di layout (*Shared/MainLayout. Razor*). I componenti di layout verranno illustrati più dettagliatamente nella sezione [pagina, routing e layout](./pages-routing-layouts.md) .

## <a name="bootstrap-blazor"></a>Blazer bootstrap

Per il bootstrap di Blazer, l'app deve:

- Specificare la posizione nella pagina in cui deve essere eseguito il rendering del componente radice (*app. Razor*).
- Aggiungere lo script del Framework Blazer corrispondente.

Nell'app Server Blazer la pagina host del componente radice viene definita nel file *_Host. cshtml* . Questo file definisce una pagina Razor, non un componente. Razor Pages utilizzare sintassi Razor per definire una pagina indirizzabile dal server, molto simile a una pagina *aspx* . Il `Html.RenderComponentAsync<TComponent>(RenderMode)` metodo viene utilizzato per definire la posizione in cui deve essere eseguito il rendering di un componente a livello di radice. L' `RenderMode` opzione indica il modo in cui il componente deve essere sottoposto a rendering. Nella tabella seguente sono descritte le opzioni supportate `RenderMode` .

|Opzione                        |Descrizione       |
|------------------------------|------------------|
|`RenderMode.Server`           |Rendering interattivo dopo che è stata stabilita una connessione con il browser|
|`RenderMode.ServerPrerendered`|Primo prerendering e quindi rendering interattivo|
|`RenderMode.Static`           |Rendering come contenuto statico|

Il riferimento allo script *_framework/blazor.Server.js* stabilisce la connessione in tempo reale con il server e quindi gestisce tutte le interazioni utente e gli aggiornamenti dell'interfaccia utente.

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

Nell'app webassembly Blazer la pagina host è un semplice file HTML statico in *wwwroot/index.html*. L' `<app>` elemento viene utilizzato per indicare la posizione in cui deve essere eseguito il rendering del componente radice.

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

Il componente specifico di cui eseguire il rendering viene configurato nel `Startup.Configure` metodo dell'app con un selettore CSS corrispondente che indica dove deve essere eseguito il rendering del componente.

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

Quando viene compilato un progetto blazer, tutti i componenti Razor e i file di codice vengono compilati in un singolo assembly. A differenza dei progetti Web Form ASP.NET, Blazer non supporta la compilazione runtime della logica dell'interfaccia utente.

## <a name="run-the-app"></a>Eseguire l'app

Per eseguire l'app Server blazer, premere `F5` in Visual Studio. Le app Blazer non supportano la compilazione in fase di esecuzione. Per visualizzare i risultati delle modifiche apportate al markup del codice e del componente, ricompilare e riavviare l'app con il debugger collegato. Se si esegue senza il debugger collegato ( `Ctrl+F5` ), Visual Studio controlla le modifiche ai file e riavvia l'app quando vengono apportate modifiche. Si aggiorna manualmente il browser Man mano che vengono apportate modifiche.

Per eseguire l'app webassembly blazer, scegliere uno degli approcci seguenti:

- Eseguire direttamente il progetto client utilizzando il server di sviluppo.
- Eseguire il progetto server quando si ospita l'app con ASP.NET Core.

Le app webassembly Blazer non supportano il debug con Visual Studio. Per eseguire l'app, usare `Ctrl+F5` anziché `F5` . È invece possibile eseguire il debug di app webassembly di Blazer direttamente nel browser. Per informazioni dettagliate, vedere [Debug ASP.NET Core Blazer](/aspnet/core/blazor/debug) .

>[!div class="step-by-step"]
>[Precedente](hosting-models.md) 
> [Avanti](app-startup.md)
