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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="49681-103">Struttura del progetto per le app Blazor</span><span class="sxs-lookup"><span data-stu-id="49681-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="49681-104">Nonostante le differenze significative della struttura del progetto, ASP.NET Web Form e Blazor condividono molti concetti simili.</span><span class="sxs-lookup"><span data-stu-id="49681-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="49681-105">Qui, esamineremo la struttura di un progetto Blazor e confrontarlo con un progetto Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="49681-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="49681-106">Per creare la tua prima app Blazor, segui le istruzioni nella procedura introduttiva di [Blazor.](/aspnet/core/blazor/get-started)</span><span class="sxs-lookup"><span data-stu-id="49681-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="49681-107">È possibile seguire le istruzioni per creare un'app Blazor Server o un'app Blazor WebAssembly ospitata in ASP.NET Core.You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49681-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="49681-108">Ad eccezione della logica specifica del modello di hosting, la maggior parte del codice in entrambi i progetti è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="49681-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="49681-109">File di progetto</span><span class="sxs-lookup"><span data-stu-id="49681-109">Project file</span></span>

<span data-ttu-id="49681-110">Le app per server Blazor sono progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49681-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="49681-111">Il file di progetto per l'app Blazor Server è semplice come si può ottenere:</span><span class="sxs-lookup"><span data-stu-id="49681-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="49681-112">Il file di progetto per un'app Blazor WebAssembly sembra leggermente più complesso (i numeri di versione esatti possono variare):</span><span class="sxs-lookup"><span data-stu-id="49681-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="49681-113">I progetti WebAssembly Blazor sono destinati a .NET Standard anziché a .NET Core perché vengono eseguiti nel browser in un runtime .NET basato su WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="49681-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="49681-114">Non è possibile installare .NET in un browser Web come si può su un server o un computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="49681-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="49681-115">Di conseguenza, il progetto fa riferimento al framework Blazor utilizzando singoli riferimenti al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49681-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="49681-116">In confronto, un progetto Web Form ASP.NET predefinito include quasi 300 righe di codice XML nel relativo file *con estensione csproj,* la maggior parte dei quali elenca in modo esplicito i vari file di codice e di contenuto nel progetto.</span><span class="sxs-lookup"><span data-stu-id="49681-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="49681-117">Molte delle semplificazioni nei progetti basati su .NET Core e .NET Standard provengono dalle destinazioni `Microsoft.NET.Sdk.Web` e dalle proprietà predefinite importate facendo riferimento all'SDK, spesso definito semplicemente Web SDK.</span><span class="sxs-lookup"><span data-stu-id="49681-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="49681-118">Web SDK include caratteri jolly e altre funzionalità che semplificano l'inclusione di file di codice e di contenuto nel progetto.</span><span class="sxs-lookup"><span data-stu-id="49681-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="49681-119">Non è necessario elencare i file in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="49681-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="49681-120">Quando è destinato a .NET Core, Web SDK aggiunge anche riferimenti a framework sia per .NET Core che per ASP.NET framework condivisi.</span><span class="sxs-lookup"><span data-stu-id="49681-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="49681-121">I framework sono visibili dal nodo **Framework dipendenze** > **Frameworks** nella finestra **Esplora soluzioni.**</span><span class="sxs-lookup"><span data-stu-id="49681-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="49681-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49681-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="49681-123">Sebbene siano supportati, i singoli riferimenti agli assembly sono meno comuni nei progetti .NET Core.Although they're supported, individual assembly references are less common in .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="49681-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="49681-124">La maggior parte delle dipendenze di progetto vengono gestite come riferimenti al pacchetto NuGet.Most project dependencies are handled as NuGet package references.</span><span class="sxs-lookup"><span data-stu-id="49681-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="49681-125">È sufficiente fare riferimento alle dipendenze dei pacchetti di primo livello nei progetti .NET Core.You only need to reference top-level package dependencies in .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="49681-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="49681-126">Le dipendenze transitive vengono incluse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="49681-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="49681-127">Anziché utilizzare il file *packages.config* comunemente disponibile nei progetti Web Form di ASP.NET `<PackageReference>` fare riferimento ai pacchetti, i riferimenti ai pacchetti vengono aggiunti al file di progetto utilizzando l'elemento .</span><span class="sxs-lookup"><span data-stu-id="49681-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="49681-128">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="49681-128">Entry point</span></span>

<span data-ttu-id="49681-129">Il punto di ingresso dell'app Blazor Server è definito nel file *di Program.cs,* come si vedrebbe in un'app console.</span><span class="sxs-lookup"><span data-stu-id="49681-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="49681-130">Quando l'app viene eseguita, crea ed esegue un'istanza dell'host Web usando valori predefiniti specifici per le app Web.</span><span class="sxs-lookup"><span data-stu-id="49681-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="49681-131">L'host Web gestisce il ciclo di vita dell'app Blazor Server e configura i servizi a livello di host.</span><span class="sxs-lookup"><span data-stu-id="49681-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="49681-132">Esempi di tali servizi sono la configurazione, la registrazione, l'inserimento delle dipendenze e il server HTTP.</span><span class="sxs-lookup"><span data-stu-id="49681-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="49681-133">Questo codice è per lo più boilerplate e viene spesso lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="49681-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="49681-134">Le app Blazor WebAssembly definiscono anche un punto di ingresso in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="49681-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="49681-135">Il codice ha un aspetto leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="49681-135">The code looks slightly different.</span></span> <span data-ttu-id="49681-136">Il codice è simile in quanto sta configurando l'host dell'app per fornire gli stessi servizi a livello di host all'app.</span><span class="sxs-lookup"><span data-stu-id="49681-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="49681-137">L'host dell'app WebAssembly, tuttavia, non configura un server HTTP perché viene eseguito direttamente nel browser.</span><span class="sxs-lookup"><span data-stu-id="49681-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="49681-138">Le app Blazor hanno una `Startup` classe anziché un file *Global.asax* per definire la logica di avvio per l'app.</span><span class="sxs-lookup"><span data-stu-id="49681-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="49681-139">La `Startup` classe viene utilizzata per configurare l'app e tutti i servizi specifici dell'app.</span><span class="sxs-lookup"><span data-stu-id="49681-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="49681-140">Nell'app Blazor Server, la `Startup` classe viene utilizzata per configurare l'endpoint per la connessione in tempo reale utilizzata da Blazor tra i browser client e il server.</span><span class="sxs-lookup"><span data-stu-id="49681-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="49681-141">Nell'app Blazor WebAssembly, la `Startup` classe definisce i componenti radice per l'app e la posizione in cui deve essere eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="49681-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="49681-142">Esamineremo più a fondo `Startup` la classe nella sezione [Avvio](./app-startup.md) app.</span><span class="sxs-lookup"><span data-stu-id="49681-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="49681-143">File statici</span><span class="sxs-lookup"><span data-stu-id="49681-143">Static files</span></span>

<span data-ttu-id="49681-144">A differenza di ASP.NET progetti Web Form, non tutti i file in un progetto Blazor possono essere richiesti come file statici.</span><span class="sxs-lookup"><span data-stu-id="49681-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="49681-145">Solo i file nella cartella *wwwroot* sono indirizzabili sul Web.</span><span class="sxs-lookup"><span data-stu-id="49681-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="49681-146">Questa cartella si riferisce alla "radice web" dell'app.</span><span class="sxs-lookup"><span data-stu-id="49681-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="49681-147">Qualsiasi elemento al di fuori della radice web dell'app *non è* indirizzabile al Web.</span><span class="sxs-lookup"><span data-stu-id="49681-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="49681-148">Questa configurazione fornisce un ulteriore livello di sicurezza che impedisce l'esposizione accidentale di file di progetto sul Web.</span><span class="sxs-lookup"><span data-stu-id="49681-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="49681-149">Configurazione</span><span class="sxs-lookup"><span data-stu-id="49681-149">Configuration</span></span>

<span data-ttu-id="49681-150">La configurazione in ASP.NET app Web Form viene in genere gestita utilizzando uno o più file *web.config.*</span><span class="sxs-lookup"><span data-stu-id="49681-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="49681-151">Le app Blazor in genere non dispongono di file *web.config.*</span><span class="sxs-lookup"><span data-stu-id="49681-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="49681-152">In caso affermativo, il file viene utilizzato solo per configurare le impostazioni specifiche di IIS quando è ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="49681-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="49681-153">Al contrario, le app Blazor Server usano le astrazioni di configurazione ASP.NET Core (le app Blazor WebAssembly non supportano attualmente le stesse astrazioni di configurazione, ma che potrebbero essere una funzionalità aggiunta in futuro).</span><span class="sxs-lookup"><span data-stu-id="49681-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="49681-154">Ad esempio, l'app predefinita Blazor Server memorizza alcune impostazioni in *appsettings.json*.</span><span class="sxs-lookup"><span data-stu-id="49681-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="49681-155">Ulteriori informazioni sulla configurazione verranno fornite in progetti ASP.NET Base nella sezione Configurazione.We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span><span class="sxs-lookup"><span data-stu-id="49681-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="49681-156">Componenti Razor</span><span class="sxs-lookup"><span data-stu-id="49681-156">Razor components</span></span>

<span data-ttu-id="49681-157">La maggior parte dei file nei progetti Blazor sono file *.razor.*</span><span class="sxs-lookup"><span data-stu-id="49681-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="49681-158">Razor è un linguaggio di modelli basato su HTML e C , che viene utilizzato per generare dinamicamente l'interfaccia utente Web.</span><span class="sxs-lookup"><span data-stu-id="49681-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="49681-159">I file *.razor* definiscono i componenti che costituiscono l'interfaccia utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="49681-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="49681-160">Per la maggior parte, i componenti sono identici per le applicazioni Blazor Server e Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="49681-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="49681-161">I componenti in Blazor sono analoghi ai controlli utente in ASP.NET Web Form.</span><span class="sxs-lookup"><span data-stu-id="49681-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="49681-162">Ogni file del componente Razor viene compilato in una classe .NET quando il progetto viene compilato.</span><span class="sxs-lookup"><span data-stu-id="49681-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="49681-163">La classe generata acquisisce lo stato del componente, la logica di rendering, i metodi del ciclo di vita, i gestori eventi e altre logiche.</span><span class="sxs-lookup"><span data-stu-id="49681-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="49681-164">Esamineremo i componenti di creazione nella sezione [Building reusable UI components with Blazor.](./components.md)</span><span class="sxs-lookup"><span data-stu-id="49681-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="49681-165">I file *_Imports.razor* non sono file di componenti Razor.</span><span class="sxs-lookup"><span data-stu-id="49681-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="49681-166">Al contrario, definiscono un set di direttive Razor da importare in altri file *.razor* all'interno della stessa cartella e nelle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="49681-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="49681-167">Ad esempio, un file *_Imports.razor* è `using` un modo convenzionale per aggiungere istruzioni per gli spazi dei nomi di uso comune:For example, a _Imports.razor file is a conventional way to add statements for commonly used namespaces:</span><span class="sxs-lookup"><span data-stu-id="49681-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="49681-168">Pagine</span><span class="sxs-lookup"><span data-stu-id="49681-168">Pages</span></span>

<span data-ttu-id="49681-169">Dove sono le pagine nelle applicazioni Blazor?</span><span class="sxs-lookup"><span data-stu-id="49681-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="49681-170">Blazor non definisce un'estensione di file separata per le pagine indirizzabili, ad esempio i file *aspx* in ASP.NET applicazioni Web Form.</span><span class="sxs-lookup"><span data-stu-id="49681-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="49681-171">Al contrario, le pagine vengono definite assegnando cicli di lavorazione ai componenti.</span><span class="sxs-lookup"><span data-stu-id="49681-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="49681-172">Una route viene in `@page` genere assegnata utilizzando la direttiva Razor.A route is typically assigned using the Razor directive.</span><span class="sxs-lookup"><span data-stu-id="49681-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="49681-173">Ad esempio, `Counter` il componente creato nel file *Pages/Counter.razor* definisce la seguente route:</span><span class="sxs-lookup"><span data-stu-id="49681-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="49681-174">Il routing in Blazor viene gestito sul lato client, non sul server.</span><span class="sxs-lookup"><span data-stu-id="49681-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="49681-175">Quando l'utente si sposta nel browser, Blazor intercetta la navigazione e quindi esegue il rendering del componente con la route corrispondente.</span><span class="sxs-lookup"><span data-stu-id="49681-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="49681-176">Le route dei componenti non vengono attualmente dedotte dal percorso del file del componente come sono con le pagine *aspx.*</span><span class="sxs-lookup"><span data-stu-id="49681-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="49681-177">Questa funzionalità potrebbe essere aggiunta in futuro.</span><span class="sxs-lookup"><span data-stu-id="49681-177">This feature may be added in the future.</span></span> <span data-ttu-id="49681-178">Ogni route deve essere specificata in modo esplicito nel componente.</span><span class="sxs-lookup"><span data-stu-id="49681-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="49681-179">L'archiviazione dei componenti instradabili in una cartella *Pages* non ha alcun significato speciale ed è puramente una convenzione.</span><span class="sxs-lookup"><span data-stu-id="49681-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="49681-180">Esamineremo più in dettaglio il routing in Blazor nella sezione [Pagine, routing e layout.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="49681-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="49681-181">Layout</span><span class="sxs-lookup"><span data-stu-id="49681-181">Layout</span></span>

<span data-ttu-id="49681-182">Nelle app Web Form ASP.NET il layout di pagina comune viene gestito utilizzando le pagine master (*Site.Master*).</span><span class="sxs-lookup"><span data-stu-id="49681-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="49681-183">Nelle app Blazor il layout di pagina viene gestito utilizzando i componenti di layout (*Shared/MainLayout.razor*).</span><span class="sxs-lookup"><span data-stu-id="49681-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="49681-184">I componenti di layout verranno descritti in modo più dettagliato nella sezione [Pagina, instradamento e layout.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="49681-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="49681-185">Bootstrap Blazor</span><span class="sxs-lookup"><span data-stu-id="49681-185">Bootstrap Blazor</span></span>

<span data-ttu-id="49681-186">Per bootstrap Blazor, l'applicazione deve:</span><span class="sxs-lookup"><span data-stu-id="49681-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="49681-187">Specificare dove deve essere eseguito il rendering del componente radice (*App.Razor*).</span><span class="sxs-lookup"><span data-stu-id="49681-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="49681-188">Aggiungere lo script del framework Blazor corrispondente.</span><span class="sxs-lookup"><span data-stu-id="49681-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="49681-189">Nell'app Blazor Server, la pagina host del componente radice è definita nel file *_Host.cshtml.*</span><span class="sxs-lookup"><span data-stu-id="49681-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="49681-190">Questo file definisce una pagina Razor, non un componente.</span><span class="sxs-lookup"><span data-stu-id="49681-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="49681-191">Le pagine Razor utilizzano la sintassi Razor per definire una pagina indirizzabile al server, molto simile a una pagina *aspx.*</span><span class="sxs-lookup"><span data-stu-id="49681-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="49681-192">Il `Html.RenderComponentAsync<TComponent>(RenderMode)` metodo viene utilizzato per definire dove deve essere eseguito il rendering di un componente a livello di radice.</span><span class="sxs-lookup"><span data-stu-id="49681-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="49681-193">L'opzione `RenderMode` indica il modo in cui deve essere eseguito il rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="49681-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="49681-194">Nella tabella seguente vengono `RenderMode` descritte le opzioni supportate.</span><span class="sxs-lookup"><span data-stu-id="49681-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="49681-195">Opzione</span><span class="sxs-lookup"><span data-stu-id="49681-195">Option</span></span>                        |<span data-ttu-id="49681-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49681-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="49681-197">Rendering interattivo una volta stabilita una connessione con il browser</span><span class="sxs-lookup"><span data-stu-id="49681-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="49681-198">Prima il prerendering e quindi il rendering in modo interattivo</span><span class="sxs-lookup"><span data-stu-id="49681-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="49681-199">Rendering come contenuto statico</span><span class="sxs-lookup"><span data-stu-id="49681-199">Rendered as static content</span></span>|

<span data-ttu-id="49681-200">Il riferimento allo script *di _framework/blazor.server.js* stabilisce la connessione in tempo reale con il server e quindi gestisce tutte le interazioni utente e gli aggiornamenti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="49681-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="49681-201">Nell'app Blazor WebAssembly la pagina host è un semplice file HTML statico *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="49681-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="49681-202">L'elemento `<app>` viene utilizzato per indicare dove deve essere eseguito il rendering del componente radice.</span><span class="sxs-lookup"><span data-stu-id="49681-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="49681-203">Il componente specifico di cui eseguire `Startup.Configure` il rendering viene configurato nel metodo dell'app con un selettore CSS corrispondente che indica dove deve essere eseguito il rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="49681-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="49681-204">Output della compilazione</span><span class="sxs-lookup"><span data-stu-id="49681-204">Build output</span></span>

<span data-ttu-id="49681-205">Quando viene compilato un progetto Blazor, tutti i file di codice e di componente Razor vengono compilati in un unico assembly.</span><span class="sxs-lookup"><span data-stu-id="49681-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="49681-206">A differenza ASP.NET progetti Web Form, Blazor non supporta la compilazione in fase di esecuzione della logica dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="49681-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="49681-207">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="49681-207">Run the app</span></span>

<span data-ttu-id="49681-208">Per eseguire l'app Blazor Server, premere `F5` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49681-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="49681-209">Le app Blazor non supportano la compilazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="49681-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="49681-210">Per visualizzare i risultati delle modifiche al markup del codice e del componente, ricompilare e riavviare l'app con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="49681-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="49681-211">Se si esegue senza il`Ctrl+F5`debugger collegato ( ), Visual Studio controlla le modifiche ai file e riavvia l'app quando vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="49681-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="49681-212">Aggiornare manualmente il browser quando vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="49681-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="49681-213">Per eseguire l'app Blazor WebAssembly, scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="49681-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="49681-214">Eseguire il progetto client direttamente utilizzando il server di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="49681-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="49681-215">Eseguire il progetto server quando si ospita l'app con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49681-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="49681-216">Le app Blazor WebAssembly non supportano il debug con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49681-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="49681-217">Per eseguire l'app, utilizzare `Ctrl+F5` instead di `F5`.</span><span class="sxs-lookup"><span data-stu-id="49681-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="49681-218">È invece possibile eseguire il debug delle applicazioni WebAssembly Blazor direttamente nel browser.</span><span class="sxs-lookup"><span data-stu-id="49681-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="49681-219">Per informazioni dettagliate, vedere [Debug ASP.NET Core Blazor .See Debug ASP.NET Core Blazor.](/aspnet/core/blazor/debug)</span><span class="sxs-lookup"><span data-stu-id="49681-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="49681-220">[Successivo](hosting-models.md)
>[precedente](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="49681-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
