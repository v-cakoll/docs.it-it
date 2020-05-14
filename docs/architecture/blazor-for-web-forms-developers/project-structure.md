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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="dc4c1-103">Struttura del progetto per le app Blazer</span><span class="sxs-lookup"><span data-stu-id="dc4c1-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="dc4c1-104">Nonostante le differenze significative della struttura di progetto, ASP.NET Web Forms e blazer condividono molti concetti simili.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="dc4c1-105">In questo articolo verrà esaminata la struttura di un progetto blazer e il confronto con un progetto Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="dc4c1-106">Per creare la prima app blazer, seguire le istruzioni riportate nella procedura introduttiva di [Blazer](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="dc4c1-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="dc4c1-107">È possibile seguire le istruzioni per la creazione di un'app del server blazer o di un'app webassembly Blazer ospitata in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="dc4c1-108">Fatta eccezione per la logica specifica del modello di hosting, la maggior parte del codice in entrambi i progetti è la stessa.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="dc4c1-109">File di progetto</span><span class="sxs-lookup"><span data-stu-id="dc4c1-109">Project file</span></span>

<span data-ttu-id="dc4c1-110">Le app del server blazer sono progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="dc4c1-111">Il file di progetto per l'app del server blazer è semplice quanto è possibile ottenere:</span><span class="sxs-lookup"><span data-stu-id="dc4c1-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="dc4c1-112">Il file di progetto per un'app webassembly blazer è leggermente più occupato (i numeri di versione esatti possono variare):</span><span class="sxs-lookup"><span data-stu-id="dc4c1-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="dc4c1-113">I progetti di webassembly Blazer hanno come destinazione .NET Standard anziché .NET Core perché vengono eseguiti nel browser in un Runtime .NET basato su webassembly.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="dc4c1-114">Non è possibile installare .NET in un Web browser, ad esempio in un server o in un computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="dc4c1-115">Di conseguenza, il progetto fa riferimento al Framework di Blaze usando singoli riferimenti ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="dc4c1-116">Per confronto, un progetto Web Form ASP.NET predefinito include quasi 300 righe di codice XML nel file con estensione *csproj* , la maggior parte dei quali elenca in modo esplicito i vari file di codice e di contenuto del progetto.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="dc4c1-117">Molte delle semplificazioni nei progetti basati su .NET Core e .NET Standard provengono dalle destinazioni predefinite e dalle proprietà importate facendo riferimento all' `Microsoft.NET.Sdk.Web` SDK, spesso noto semplicemente come Web SDK.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="dc4c1-118">Web SDK include caratteri jolly e altre convenienze che semplificano l'inclusione del codice e dei file di contenuto nel progetto.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="dc4c1-119">Non è necessario elencare i file in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="dc4c1-120">Quando la destinazione è .NET Core, Web SDK aggiunge anche riferimenti a Framework sia per .NET Core che ASP.NET Core Framework condivisi.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="dc4c1-121">I Framework sono visibili dal nodo Framework **dipendenze**  >  **Frameworks** nella finestra **Esplora soluzioni** .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="dc4c1-122">I Framework condivisi sono raccolte di assembly installati nel computer durante l'installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="dc4c1-123">Sebbene siano supportati, i singoli riferimenti ad assembly sono meno comuni nei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="dc4c1-124">La maggior parte delle dipendenze del progetto viene gestita come riferimenti ai pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="dc4c1-125">È sufficiente fare riferimento alle dipendenze del pacchetto di primo livello nei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="dc4c1-126">Le dipendenze transitive vengono incluse automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="dc4c1-127">Anziché usare il file *packages. config* comunemente presente nei progetti Web Form ASP.NET per fare riferimento ai pacchetti, i riferimenti al pacchetto vengono aggiunti al file di progetto usando l' `<PackageReference>` elemento.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="dc4c1-128">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="dc4c1-128">Entry point</span></span>

<span data-ttu-id="dc4c1-129">Il punto di ingresso dell'app Server Blazer viene definito nel file *Program.cs* , come si può notare in un'app console.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="dc4c1-130">Quando l'app viene eseguita, crea ed esegue un'istanza dell'host web usando le impostazioni predefinite specifiche per le app Web.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="dc4c1-131">L'host Web gestisce il ciclo di vita dell'app Server Blaze e configura i servizi a livello di host.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="dc4c1-132">Esempi di tali servizi sono configurazione, registrazione, inserimento di dipendenze e il server HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="dc4c1-133">Questo codice è per lo più standard e viene spesso lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="dc4c1-134">Le app webassembly Blazer definiscono anche un punto di ingresso in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="dc4c1-135">Il codice ha un aspetto leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-135">The code looks slightly different.</span></span> <span data-ttu-id="dc4c1-136">Il codice è simile in quanto configura l'host dell'applicazione per fornire gli stessi servizi a livello di host all'app.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="dc4c1-137">Tuttavia, l'host dell'app webassembly non configura un server HTTP perché viene eseguito direttamente nel browser.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="dc4c1-138">Le app Blazer hanno una `Startup` classe anziché un file *Global. asax* per definire la logica di avvio per l'app.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="dc4c1-139">La `Startup` classe viene usata per configurare l'app e tutti i servizi specifici dell'app.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="dc4c1-140">Nell'app Server Blazer la `Startup` classe viene usata per configurare l'endpoint per la connessione in tempo reale usata da Blazer tra i browser client e il server.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="dc4c1-141">Nell'app webassembly Blazer la `Startup` classe definisce i componenti radice per l'app e la posizione in cui devono essere sottoposti a rendering.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="dc4c1-142">Verrà esaminata in maniera più approfondita la `Startup` classe nella sezione relativa all' [avvio dell'app](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="dc4c1-143">File statici</span><span class="sxs-lookup"><span data-stu-id="dc4c1-143">Static files</span></span>

<span data-ttu-id="dc4c1-144">A differenza dei progetti Web Form ASP.NET, non tutti i file in un progetto Blazer possono essere richiesti come file statici.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="dc4c1-145">Solo i file nella cartella *wwwroot* sono indirizzabili sul Web.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="dc4c1-146">Questa cartella viene definita "radice Web" dell'app.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="dc4c1-147">Qualsiasi elemento all'esterno della radice Web dell'app *non è* indirizzabile sul Web.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="dc4c1-148">Questa configurazione offre un livello di sicurezza aggiuntivo che impedisce l'esposizione accidentale dei file di progetto sul Web.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="dc4c1-149">Configurazione</span><span class="sxs-lookup"><span data-stu-id="dc4c1-149">Configuration</span></span>

<span data-ttu-id="dc4c1-150">La configurazione nelle app Web Form ASP.NET viene in genere gestita usando uno o più file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="dc4c1-151">Le app Blazer non dispongono in genere di file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="dc4c1-152">In caso affermativo, il file viene usato solo per configurare le impostazioni specifiche di IIS se ospitate in IIS.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="dc4c1-153">Al contrario, le app del server Blazer usano le astrazioni di configurazione ASP.NET Core (le app webassembly Blazer non supportano attualmente le stesse astrazioni di configurazione, ma potrebbe essere una funzionalità aggiunta in futuro).</span><span class="sxs-lookup"><span data-stu-id="dc4c1-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="dc4c1-154">Ad esempio, l'app Server Blazer predefinita archivia alcune impostazioni in *appSettings. JSON*.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="dc4c1-155">Nella sezione [configurazione](./config.md) verranno fornite ulteriori informazioni sulla configurazione nei progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="dc4c1-156">Componenti Razor</span><span class="sxs-lookup"><span data-stu-id="dc4c1-156">Razor components</span></span>

<span data-ttu-id="dc4c1-157">La maggior parte dei file nei progetti di blazer sono file con *estensione Razor* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="dc4c1-158">Razor è un linguaggio di modello basato su HTML e C# usato per generare dinamicamente l'interfaccia utente Web.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="dc4c1-159">I file con *estensione Razor* definiscono i componenti che costituiscono l'interfaccia utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="dc4c1-160">Nella maggior parte dei casi, i componenti sono identici per entrambe le app Blazer server e blazer webassembly.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="dc4c1-161">I componenti in blazer sono analoghi ai controlli utente nei Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="dc4c1-162">Ogni file del componente Razor viene compilato in una classe .NET quando viene compilato il progetto.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="dc4c1-163">La classe generata acquisisce lo stato del componente, la logica di rendering, i metodi del ciclo di vita, i gestori eventi e altre logiche.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="dc4c1-164">Verranno esaminati i componenti di creazione nella sezione [creazione di componenti dell'interfaccia utente riutilizzabili con blazer](./components.md) .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="dc4c1-165">I file *_Imports. Razor* non sono file componente Razor.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="dc4c1-166">Definiscono invece un set di direttive Razor da importare in altri file con *estensione Razor* all'interno della stessa cartella e nelle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="dc4c1-167">Ad esempio, un file *_Imports. Razor* è un modo convenzionale per aggiungere `using` direttive per gli spazi dei nomi di uso comune:</span><span class="sxs-lookup"><span data-stu-id="dc4c1-167">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="dc4c1-168">.NET</span><span class="sxs-lookup"><span data-stu-id="dc4c1-168">Pages</span></span>

<span data-ttu-id="dc4c1-169">Dove si trovano le pagine nelle app Blazer?</span><span class="sxs-lookup"><span data-stu-id="dc4c1-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="dc4c1-170">Blazer non definisce un'estensione di file separata per le pagine indirizzabili, ad esempio i file *aspx* nelle app Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="dc4c1-171">Le pagine vengono invece definite assegnando Route ai componenti.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="dc4c1-172">Una route viene in genere assegnata usando la `@page` direttiva Razor.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="dc4c1-173">Ad esempio, il `Counter` componente creato nel file *pages/Counter. Razor* definisce la route seguente:</span><span class="sxs-lookup"><span data-stu-id="dc4c1-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="dc4c1-174">Il routing in blazer è gestito sul lato client, non sul server.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="dc4c1-175">Quando l'utente si sposta nel browser, blazer intercetta la navigazione e quindi esegue il rendering del componente con la route corrispondente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="dc4c1-176">Le route dei componenti non sono attualmente dedotte dal percorso del file del componente, come avviene con le pagine *aspx* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="dc4c1-177">Questa funzionalità può essere aggiunta in futuro.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-177">This feature may be added in the future.</span></span> <span data-ttu-id="dc4c1-178">Ogni route deve essere specificata in modo esplicito nel componente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="dc4c1-179">L'archiviazione di componenti instradabili in una cartella di *pagine* non ha un significato speciale ed è puramente una convenzione.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="dc4c1-180">Verranno esaminati più dettagliatamente il routing in blazer nella sezione [pagine, routing e layout](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="dc4c1-181">Layout</span><span class="sxs-lookup"><span data-stu-id="dc4c1-181">Layout</span></span>

<span data-ttu-id="dc4c1-182">Nelle app Web Form ASP.NET, il layout di pagina comune viene gestito usando le pagine master (*site. master*).</span><span class="sxs-lookup"><span data-stu-id="dc4c1-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="dc4c1-183">Nelle app Blazer il layout di pagina viene gestito usando i componenti di layout (*Shared/MainLayout. Razor*).</span><span class="sxs-lookup"><span data-stu-id="dc4c1-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="dc4c1-184">I componenti di layout verranno illustrati più dettagliatamente nella sezione [pagina, routing e layout](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="dc4c1-185">Blazer bootstrap</span><span class="sxs-lookup"><span data-stu-id="dc4c1-185">Bootstrap Blazor</span></span>

<span data-ttu-id="dc4c1-186">Per il bootstrap di Blazer, l'app deve:</span><span class="sxs-lookup"><span data-stu-id="dc4c1-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="dc4c1-187">Specificare la posizione nella pagina in cui deve essere eseguito il rendering del componente radice (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="dc4c1-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="dc4c1-188">Aggiungere lo script del Framework Blazer corrispondente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="dc4c1-189">Nell'app Server Blazer la pagina host del componente radice viene definita nel file *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="dc4c1-190">Questo file definisce una pagina Razor, non un componente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="dc4c1-191">Razor Pages utilizzare sintassi Razor per definire una pagina indirizzabile dal server, molto simile a una pagina *aspx* .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="dc4c1-192">Il `Html.RenderComponentAsync<TComponent>(RenderMode)` metodo viene utilizzato per definire la posizione in cui deve essere eseguito il rendering di un componente a livello di radice.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="dc4c1-193">L' `RenderMode` opzione indica il modo in cui il componente deve essere sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="dc4c1-194">Nella tabella seguente sono descritte le opzioni supportate `RenderMode` .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="dc4c1-195">Opzione</span><span class="sxs-lookup"><span data-stu-id="dc4c1-195">Option</span></span>                        |<span data-ttu-id="dc4c1-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc4c1-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="dc4c1-197">Rendering interattivo dopo che è stata stabilita una connessione con il browser</span><span class="sxs-lookup"><span data-stu-id="dc4c1-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="dc4c1-198">Primo prerendering e quindi rendering interattivo</span><span class="sxs-lookup"><span data-stu-id="dc4c1-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="dc4c1-199">Rendering come contenuto statico</span><span class="sxs-lookup"><span data-stu-id="dc4c1-199">Rendered as static content</span></span>|

<span data-ttu-id="dc4c1-200">Il riferimento allo script *_framework/blazor.Server.js* stabilisce la connessione in tempo reale con il server e quindi gestisce tutte le interazioni utente e gli aggiornamenti dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="dc4c1-201">Nell'app webassembly Blazer la pagina host è un semplice file HTML statico in *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="dc4c1-202">L' `<app>` elemento viene utilizzato per indicare la posizione in cui deve essere eseguito il rendering del componente radice.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="dc4c1-203">Il componente specifico di cui eseguire il rendering viene configurato nel `Startup.Configure` metodo dell'app con un selettore CSS corrispondente che indica dove deve essere eseguito il rendering del componente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="dc4c1-204">Output della compilazione</span><span class="sxs-lookup"><span data-stu-id="dc4c1-204">Build output</span></span>

<span data-ttu-id="dc4c1-205">Quando viene compilato un progetto blazer, tutti i componenti Razor e i file di codice vengono compilati in un singolo assembly.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="dc4c1-206">A differenza dei progetti Web Form ASP.NET, Blazer non supporta la compilazione runtime della logica dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="dc4c1-207">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="dc4c1-207">Run the app</span></span>

<span data-ttu-id="dc4c1-208">Per eseguire l'app Server blazer, premere `F5` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="dc4c1-209">Le app Blazer non supportano la compilazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="dc4c1-210">Per visualizzare i risultati delle modifiche apportate al markup del codice e del componente, ricompilare e riavviare l'app con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="dc4c1-211">Se si esegue senza il debugger collegato ( `Ctrl+F5` ), Visual Studio controlla le modifiche ai file e riavvia l'app quando vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="dc4c1-212">Si aggiorna manualmente il browser Man mano che vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="dc4c1-213">Per eseguire l'app webassembly blazer, scegliere uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc4c1-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="dc4c1-214">Eseguire direttamente il progetto client utilizzando il server di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="dc4c1-215">Eseguire il progetto server quando si ospita l'app con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="dc4c1-216">Le app webassembly Blazer non supportano il debug con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="dc4c1-217">Per eseguire l'app, usare `Ctrl+F5` anziché `F5` .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="dc4c1-218">È invece possibile eseguire il debug di app webassembly di Blazer direttamente nel browser.</span><span class="sxs-lookup"><span data-stu-id="dc4c1-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="dc4c1-219">Per informazioni dettagliate, vedere [Debug ASP.NET Core Blazer](/aspnet/core/blazor/debug) .</span><span class="sxs-lookup"><span data-stu-id="dc4c1-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc4c1-220">[Precedente](hosting-models.md) 
> [Avanti](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="dc4c1-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
