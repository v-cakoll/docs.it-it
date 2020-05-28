---
title: Eseguire la migrazione da Web Form ASP.NET a blazer
description: Informazioni su come eseguire la migrazione di un'app Web Form ASP.NET esistente a blazer.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: b614572bd04d9ec694b0feb95173373591d5e117
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144409"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="f05cf-103">Eseguire la migrazione da Web Form ASP.NET a blazer</span><span class="sxs-lookup"><span data-stu-id="f05cf-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="f05cf-104">La migrazione di una codebase da ASP.NET Web Forms a blazer è un'attività dispendiosa in termini di tempo che richiede la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="f05cf-105">Questo capitolo descrive il processo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-105">This chapter outlines the process.</span></span> <span data-ttu-id="f05cf-106">Un elemento che può semplificare la transizione consiste nel garantire che l'app rispetti un'architettura a più *livelli* , in cui il modello di app (in questo caso, Web Form) è separato dalla logica di business.</span><span class="sxs-lookup"><span data-stu-id="f05cf-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="f05cf-107">Questa separazione logica dei livelli rende chiaro cosa deve passare a .NET Core e blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="f05cf-108">Per questo esempio viene usata l'app eShop disponibile su [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) .</span><span class="sxs-lookup"><span data-stu-id="f05cf-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="f05cf-109">eShop è un servizio di catalogo che fornisce funzionalità CRUD tramite l'immissione e la convalida del modulo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="f05cf-110">Perché è necessario eseguire la migrazione di un'app funzionante a blazer?</span><span class="sxs-lookup"><span data-stu-id="f05cf-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="f05cf-111">Spesso non è necessario.</span><span class="sxs-lookup"><span data-stu-id="f05cf-111">Many times, there's no need.</span></span> <span data-ttu-id="f05cf-112">I Web Form ASP.NET continueranno a essere supportati per molti anni.</span><span class="sxs-lookup"><span data-stu-id="f05cf-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="f05cf-113">Tuttavia, molte delle funzionalità fornite da blazer sono supportate solo in un'app migrata.</span><span class="sxs-lookup"><span data-stu-id="f05cf-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="f05cf-114">Tali funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="f05cf-114">Such features include:</span></span>

- <span data-ttu-id="f05cf-115">Miglioramenti delle prestazioni nel Framework, ad esempio`Span<T>`</span><span class="sxs-lookup"><span data-stu-id="f05cf-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="f05cf-116">Possibilità di eseguire come webassembly</span><span class="sxs-lookup"><span data-stu-id="f05cf-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="f05cf-117">Supporto multipiattaforma per Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="f05cf-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="f05cf-118">Distribuzione app-Local o Framework condiviso senza conseguenze per altre app</span><span class="sxs-lookup"><span data-stu-id="f05cf-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="f05cf-119">Se queste o altre nuove funzionalità sono sufficientemente interessanti, potrebbe essere necessario eseguire la migrazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="f05cf-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="f05cf-120">La migrazione può assumere forme diverse; può essere l'intera app o solo determinati endpoint che richiedono le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f05cf-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="f05cf-121">La decisione di eseguire la migrazione è in definitiva basata sui problemi aziendali che devono essere risolti dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="f05cf-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="f05cf-122">Hosting lato server e lato client</span><span class="sxs-lookup"><span data-stu-id="f05cf-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="f05cf-123">Come descritto nel capitolo [hosting Models](hosting-models.md) , un'app Blaze può essere ospitata in due modi diversi: lato server e lato client.</span><span class="sxs-lookup"><span data-stu-id="f05cf-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="f05cf-124">Il modello sul lato server usa ASP.NET Core le connessioni SignalR per gestire gli aggiornamenti DOM durante l'esecuzione di qualsiasi codice effettivo sul server.</span><span class="sxs-lookup"><span data-stu-id="f05cf-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="f05cf-125">Il modello sul lato client viene eseguito come webassembly all'interno di un browser e non richiede alcuna connessione al server.</span><span class="sxs-lookup"><span data-stu-id="f05cf-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="f05cf-126">Esistono diverse differenze che possono influire sul meglio per un'app specifica:</span><span class="sxs-lookup"><span data-stu-id="f05cf-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="f05cf-127">L'esecuzione come webassembly è ancora in fase di sviluppo e potrebbe non supportare tutte le funzionalità, ad esempio il threading, all'ora corrente</span><span class="sxs-lookup"><span data-stu-id="f05cf-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="f05cf-128">La comunicazione loquace tra il client e il server può causare problemi di latenza in modalità lato server</span><span class="sxs-lookup"><span data-stu-id="f05cf-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="f05cf-129">L'accesso ai database e ai servizi interni o protetti richiede un servizio separato con hosting lato client</span><span class="sxs-lookup"><span data-stu-id="f05cf-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="f05cf-130">Al momento della stesura di questo articolo, il modello sul lato server è più simile a Web Forms.</span><span class="sxs-lookup"><span data-stu-id="f05cf-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="f05cf-131">La maggior parte di questo capitolo è incentrata sul modello di hosting lato server, in quanto è pronto per l'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="f05cf-132">Creare un nuovo progetto</span><span class="sxs-lookup"><span data-stu-id="f05cf-132">Create a new project</span></span>

<span data-ttu-id="f05cf-133">Questo passaggio iniziale della migrazione prevede la creazione di un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="f05cf-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="f05cf-134">Questo tipo di progetto è basato sui progetti di stile SDK di .NET Core e semplifica la maggior parte degli standard usati nei formati di progetto precedenti.</span><span class="sxs-lookup"><span data-stu-id="f05cf-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="f05cf-135">Per altri dettagli, vedere il capitolo sulla [struttura del progetto](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f05cf-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="f05cf-136">Una volta creato il progetto, installare le librerie utilizzate nel progetto precedente.</span><span class="sxs-lookup"><span data-stu-id="f05cf-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="f05cf-137">Nei progetti Web Form precedenti è possibile che sia stato usato il file *packages. config* per elencare i pacchetti NuGet necessari.</span><span class="sxs-lookup"><span data-stu-id="f05cf-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="f05cf-138">Nel nuovo progetto di tipo SDK, *packages. config* è stato sostituito da `<PackageReference>` elementi nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f05cf-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="f05cf-139">Un vantaggio di questo approccio è che tutte le dipendenze vengono installate in modo transitivo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="f05cf-140">È possibile elencare solo le dipendenze di primo livello a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="f05cf-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="f05cf-141">Molte delle dipendenze che usi sono disponibili per .NET Core, tra cui Entity Framework 6 e log4net.</span><span class="sxs-lookup"><span data-stu-id="f05cf-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="f05cf-142">Se non è disponibile alcuna versione di .NET Core o .NET Standard, è spesso possibile usare la versione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f05cf-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="f05cf-143">Il chilometraggio potrebbe variare.</span><span class="sxs-lookup"><span data-stu-id="f05cf-143">Your mileage may vary.</span></span> <span data-ttu-id="f05cf-144">Qualsiasi API usata che non è disponibile in .NET Core causa un errore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="f05cf-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="f05cf-145">Visual Studio invia notifiche a questi pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f05cf-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="f05cf-146">Viene visualizzata un'icona gialla sul nodo **riferimenti** del progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="f05cf-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="f05cf-147">Nel progetto eShop basato su blazer è possibile visualizzare i pacchetti installati.</span><span class="sxs-lookup"><span data-stu-id="f05cf-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="f05cf-148">In precedenza, il file *packages. config* elencava tutti i pacchetti usati nel progetto, ottenendo un file di lunghezza quasi 50 righe.</span><span class="sxs-lookup"><span data-stu-id="f05cf-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="f05cf-149">Un frammento di *packages. config* è:</span><span class="sxs-lookup"><span data-stu-id="f05cf-149">A snippet of *packages.config* is:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

<span data-ttu-id="f05cf-150">L' `<packages>` elemento include tutte le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f05cf-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="f05cf-151">È difficile identificare quali di questi pacchetti sono inclusi perché sono necessari.</span><span class="sxs-lookup"><span data-stu-id="f05cf-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="f05cf-152">Alcuni `<package>` elementi sono elencati semplicemente per soddisfare le esigenze delle dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f05cf-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="f05cf-153">Il progetto Blazer elenca le dipendenze richieste all'interno `<ItemGroup>` di un elemento nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="f05cf-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="f05cf-154">Un pacchetto NuGet che semplifica la vita degli sviluppatori di Web Form è [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f05cf-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="f05cf-155">Sebbene .NET Core sia multipiattaforma, alcune funzionalità sono disponibili solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="f05cf-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="f05cf-156">Le funzionalità specifiche di Windows vengono rese disponibili tramite l'installazione di Compatibility Pack.</span><span class="sxs-lookup"><span data-stu-id="f05cf-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="f05cf-157">Esempi di queste funzionalità includono il registro di sistema, WMI e i servizi directory.</span><span class="sxs-lookup"><span data-stu-id="f05cf-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="f05cf-158">Il pacchetto aggiunge circa 20.000 API e attiva molti servizi con cui potrebbe essere già noto.</span><span class="sxs-lookup"><span data-stu-id="f05cf-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="f05cf-159">Il progetto eShop non richiede il pacchetto di compatibilità. Tuttavia, se i progetti utilizzano funzionalità specifiche di Windows, il pacchetto semplifica le attività di migrazione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="f05cf-160">Abilita processo di avvio</span><span class="sxs-lookup"><span data-stu-id="f05cf-160">Enable startup process</span></span>

<span data-ttu-id="f05cf-161">Il processo di avvio per blazer è stato modificato da Web Form e segue una configurazione simile per altri servizi ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="f05cf-162">Quando vengono ospitati sul lato server, i componenti Blazer vengono eseguiti come parte di una normale app ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="f05cf-163">Quando sono ospitati nel browser con webassembly, i componenti di Blazer usano un modello di hosting simile.</span><span class="sxs-lookup"><span data-stu-id="f05cf-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="f05cf-164">La differenza è che i componenti vengono eseguiti come servizio separato da uno qualsiasi dei processi back-end.</span><span class="sxs-lookup"><span data-stu-id="f05cf-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="f05cf-165">In entrambi i casi, l'avvio è simile.</span><span class="sxs-lookup"><span data-stu-id="f05cf-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="f05cf-166">Il file *Global.asax.cs* è la pagina di avvio predefinita per i progetti Web Form.</span><span class="sxs-lookup"><span data-stu-id="f05cf-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="f05cf-167">Nel progetto eShop questo file configura il contenitore di inversione del controllo (IoC) e gestisce i vari eventi del ciclo di vita dell'app o della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f05cf-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="f05cf-168">Alcuni di questi eventi vengono gestiti con middleware, ad esempio `Application_BeginRequest` .</span><span class="sxs-lookup"><span data-stu-id="f05cf-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="f05cf-169">Per altri eventi è necessario eseguire l'override di servizi specifici tramite l'inserimento DI dipendenze.</span><span class="sxs-lookup"><span data-stu-id="f05cf-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="f05cf-170">A titolo di esempio, il file *Global.asax.cs* per eShop contiene il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// https://autofaccn.readthedocs.io/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

<span data-ttu-id="f05cf-171">Il file precedente diventa la `Startup` classe in blazer sul lato server:</span><span class="sxs-lookup"><span data-stu-id="f05cf-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

<span data-ttu-id="f05cf-172">Una modifica significativa che è possibile notare da Web Form è l'importanza di DI.</span><span class="sxs-lookup"><span data-stu-id="f05cf-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="f05cf-173">DI è stato un principio guida nel ASP.NET Core progettazione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="f05cf-174">Supporta la personalizzazione di quasi tutti gli aspetti del framework ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="f05cf-175">Esiste anche un provider di servizi predefinito che può essere usato per molti scenari.</span><span class="sxs-lookup"><span data-stu-id="f05cf-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="f05cf-176">Se è necessaria una maggiore personalizzazione, può essere supportata dai numerosi progetti della community.</span><span class="sxs-lookup"><span data-stu-id="f05cf-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="f05cf-177">Ad esempio, è possibile portare avanti l'investimento della libreria DI terze parti.</span><span class="sxs-lookup"><span data-stu-id="f05cf-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="f05cf-178">Nell'app eShop originale è presente una configurazione per la gestione delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="f05cf-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="f05cf-179">Poiché il blazer sul lato server usa ASP.NET Core SignalR per la comunicazione, lo stato della sessione non è supportato perché le connessioni possono verificarsi indipendentemente da un contesto HTTP.</span><span class="sxs-lookup"><span data-stu-id="f05cf-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="f05cf-180">Un'app che usa lo stato della sessione richiede la riarchitettura prima di essere eseguita come app blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="f05cf-181">Per altre informazioni sull'avvio dell'app, vedere [avvio dell'app](app-startup.md).</span><span class="sxs-lookup"><span data-stu-id="f05cf-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="f05cf-182">Eseguire la migrazione di moduli e gestori HTTP al middleware</span><span class="sxs-lookup"><span data-stu-id="f05cf-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="f05cf-183">I moduli e i gestori HTTP sono modelli comuni in Web Form per controllare la pipeline di richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="f05cf-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="f05cf-184">Classi che implementano `IHttpModule` o `IHttpHandler` possono essere registrate ed elaborare richieste in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f05cf-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="f05cf-185">Web Form configura i moduli e i gestori nel file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="f05cf-186">Anche i Web Form sono molto basati sulla gestione degli eventi del ciclo di vita dell'app.</span><span class="sxs-lookup"><span data-stu-id="f05cf-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="f05cf-187">ASP.NET Core usa invece il middleware.</span><span class="sxs-lookup"><span data-stu-id="f05cf-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="f05cf-188">Il middleware è registrato nel `Configure` metodo della `Startup` classe.</span><span class="sxs-lookup"><span data-stu-id="f05cf-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="f05cf-189">L'ordine di esecuzione del middleware è determinato dall'ordine di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="f05cf-190">Nella sezione [Enable Startup Process](#enable-startup-process) è stato generato un evento Lifecycle da Web Form come `Application_BeginRequest` metodo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="f05cf-191">Questo evento non è disponibile in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="f05cf-192">Un modo per ottenere questo comportamento consiste nell'implementare il middleware come illustrato nell'esempio di file *Startup.cs* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="f05cf-193">Questo middleware esegue la stessa logica e quindi trasferisce il controllo al gestore successivo nella pipeline middleware.</span><span class="sxs-lookup"><span data-stu-id="f05cf-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="f05cf-194">Per altre informazioni sulla migrazione di moduli e gestori, vedere [eseguire la migrazione di moduli e gestori HTTP a ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span><span class="sxs-lookup"><span data-stu-id="f05cf-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="f05cf-195">Esegui la migrazione dei file statici</span><span class="sxs-lookup"><span data-stu-id="f05cf-195">Migrate static files</span></span>

<span data-ttu-id="f05cf-196">Per gestire i file statici, ad esempio HTML, CSS, immagini e JavaScript, i file devono essere esposti dal middleware.</span><span class="sxs-lookup"><span data-stu-id="f05cf-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="f05cf-197">La chiamata al `UseStaticFiles` metodo consente di mantenere i file statici dal percorso radice Web.</span><span class="sxs-lookup"><span data-stu-id="f05cf-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="f05cf-198">La directory radice Web predefinita è *wwwroot*, ma può essere personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f05cf-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="f05cf-199">Come incluso nel `Configure` metodo della `Startup` classe eShop:</span><span class="sxs-lookup"><span data-stu-id="f05cf-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="f05cf-200">Il progetto eShop Abilita l'accesso ai file statici di base.</span><span class="sxs-lookup"><span data-stu-id="f05cf-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="f05cf-201">Sono disponibili molte personalizzazioni per l'accesso ai file statici.</span><span class="sxs-lookup"><span data-stu-id="f05cf-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="f05cf-202">Per informazioni sull'abilitazione dei file predefiniti o di un browser file, vedere [file statici in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span><span class="sxs-lookup"><span data-stu-id="f05cf-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="f05cf-203">Eseguire la migrazione della creazione di bundle e della configurazione di minification</span><span class="sxs-lookup"><span data-stu-id="f05cf-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="f05cf-204">La creazione di bundle e minification sono tecniche di ottimizzazione delle prestazioni per ridurre il numero e le dimensioni delle richieste del server per recuperare determinati tipi di file.</span><span class="sxs-lookup"><span data-stu-id="f05cf-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="f05cf-205">JavaScript e CSS spesso subiscono una forma di aggregazione o minification prima di essere inviati al client.</span><span class="sxs-lookup"><span data-stu-id="f05cf-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="f05cf-206">In ASP.NET Web Forms queste ottimizzazioni vengono gestite in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="f05cf-207">Le convenzioni di ottimizzazione sono definite *app_start file/bundleconfig.cs* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="f05cf-208">In ASP.NET Core, viene adottato un approccio più dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="f05cf-209">Un file elenca i file da minimizzati, insieme a impostazioni minification specifiche.</span><span class="sxs-lookup"><span data-stu-id="f05cf-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="f05cf-210">Per altre informazioni sulla creazione di bundle e minification, vedere [bundle e minimizzare asset statici in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="f05cf-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="f05cf-211">Migrare pagine ASPX</span><span class="sxs-lookup"><span data-stu-id="f05cf-211">Migrate ASPX pages</span></span>

<span data-ttu-id="f05cf-212">Una pagina in un'app Web Form è un file con estensione *aspx* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="f05cf-213">Una pagina Web Form spesso può essere mappata a un componente in blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="f05cf-214">Un componente Blazer viene creato in un file con estensione *Razor* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="f05cf-215">Per il progetto eShop, cinque pagine vengono convertite in una pagina Razor.</span><span class="sxs-lookup"><span data-stu-id="f05cf-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="f05cf-216">La visualizzazione dettagli, ad esempio, è costituita da tre file nel progetto Web Form, ovvero *Details. aspx*, *Details.aspx.cs*e *Details.aspx.designer.cs*.</span><span class="sxs-lookup"><span data-stu-id="f05cf-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="f05cf-217">Quando si esegue la conversione in blazer, il code-behind e il markup vengono combinati in *Details. Razor*.</span><span class="sxs-lookup"><span data-stu-id="f05cf-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="f05cf-218">La compilazione Razor (equivalente ai file con *estensione designer.cs* ) viene archiviata nella directory *obj* e, per impostazione predefinita, è visualizzabile in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="f05cf-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="f05cf-219">La pagina Web Form è costituita dal markup seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-219">The Web Forms page consists of the following markup:</span></span>

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

<span data-ttu-id="f05cf-220">Il code-behind del markup precedente include il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-220">The preceding markup's code-behind includes the following code:</span></span>

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

<span data-ttu-id="f05cf-221">Quando viene convertita in blazer, la pagina Web Form si traduce nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

<span data-ttu-id="f05cf-222">Si noti che il codice e il markup si trovano nello stesso file.</span><span class="sxs-lookup"><span data-stu-id="f05cf-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="f05cf-223">Tutti i servizi necessari vengono resi accessibili con l' `@inject` attributo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="f05cf-224">Per la `@page` direttiva, è possibile accedere a questa pagina nella `Catalog/Details/{id}` Route.</span><span class="sxs-lookup"><span data-stu-id="f05cf-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="f05cf-225">Il valore del `{id}` segnaposto della route è stato vincolato a un numero intero.</span><span class="sxs-lookup"><span data-stu-id="f05cf-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="f05cf-226">Come descritto nella sezione relativa al [routing](pages-routing-layouts.md) , a differenza dei Web Form, un componente Razor dichiara in modo esplicito la route e tutti i parametri inclusi.</span><span class="sxs-lookup"><span data-stu-id="f05cf-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="f05cf-227">Molti controlli Web Form potrebbero non avere controparti esatte in blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="f05cf-228">Spesso è presente un frammento HTML equivalente che servirà allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="f05cf-229">Ad esempio, il `<asp:Label />` controllo può essere sostituito con un `<label>` elemento HTML.</span><span class="sxs-lookup"><span data-stu-id="f05cf-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="f05cf-230">Convalida del modello in blazer</span><span class="sxs-lookup"><span data-stu-id="f05cf-230">Model validation in Blazor</span></span>

<span data-ttu-id="f05cf-231">Se il codice Web Form include la convalida, è possibile trasferire la maggior parte degli elementi disponibili con modifiche minime.</span><span class="sxs-lookup"><span data-stu-id="f05cf-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="f05cf-232">Un vantaggio per l'esecuzione in blazer è che la stessa logica di convalida può essere eseguita senza la necessità di JavaScript personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f05cf-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="f05cf-233">Le annotazioni dei dati consentono di semplificare la convalida del modello.</span><span class="sxs-lookup"><span data-stu-id="f05cf-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="f05cf-234">La pagina *create. aspx* , ad esempio, contiene un form di immissione dati con convalida.</span><span class="sxs-lookup"><span data-stu-id="f05cf-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="f05cf-235">Un frammento di esempio sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-235">An example snippet would look like this:</span></span>

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

<span data-ttu-id="f05cf-236">In blazer viene fornito il markup equivalente in un file *create. Razor* :</span><span class="sxs-lookup"><span data-stu-id="f05cf-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

<span data-ttu-id="f05cf-237">Il `EditForm` contesto include il supporto della convalida e può essere racchiuso tra input.</span><span class="sxs-lookup"><span data-stu-id="f05cf-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="f05cf-238">Le annotazioni dei dati costituiscono un modo comune per aggiungere la convalida.</span><span class="sxs-lookup"><span data-stu-id="f05cf-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="f05cf-239">Questo supporto della convalida può essere aggiunto tramite il `DataAnnotationsValidator` componente.</span><span class="sxs-lookup"><span data-stu-id="f05cf-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="f05cf-240">Per ulteriori informazioni su questo meccanismo, vedere la pagina relativa alla [convalida e ai moduli ASP.NET Core Blazer](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="f05cf-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="f05cf-241">Eseguire la migrazione di controlli Web Form predefiniti</span><span class="sxs-lookup"><span data-stu-id="f05cf-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="f05cf-242">*Questo contenuto sarà presto disponibile.*</span><span class="sxs-lookup"><span data-stu-id="f05cf-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="f05cf-243">Eseguire la migrazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="f05cf-243">Migrate configuration</span></span>

<span data-ttu-id="f05cf-244">In un progetto Web Form i dati di configurazione vengono archiviati più di frequente nel file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="f05cf-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="f05cf-245">È possibile accedere ai dati di configurazione con `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="f05cf-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="f05cf-246">I servizi erano spesso necessari per analizzare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f05cf-246">Services were often required to parse objects.</span></span> <span data-ttu-id="f05cf-247">Con .NET Framework 4.7.2, la composizione è stata aggiunta alla configurazione tramite `ConfigurationBuilders` .</span><span class="sxs-lookup"><span data-stu-id="f05cf-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="f05cf-248">Questi generatori hanno consentito agli sviluppatori di aggiungere varie origini per la configurazione che è stata quindi composte in fase di esecuzione per recuperare i valori necessari.</span><span class="sxs-lookup"><span data-stu-id="f05cf-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="f05cf-249">In ASP.NET Core è stato introdotto un sistema di configurazione flessibile che consente di definire l'origine o le origini di configurazione usate dall'app e dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="f05cf-250">L' `ConfigurationBuilder` infrastruttura che è possibile usare nell'app Web Form è stata modellata dopo i concetti usati nel sistema di configurazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="f05cf-251">Il frammento di codice seguente illustra come il progetto Web Forms eShop USA *Web. config* per archiviare i valori di configurazione:</span><span class="sxs-lookup"><span data-stu-id="f05cf-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

<span data-ttu-id="f05cf-252">È frequente che i segreti, ad esempio le stringhe di connessione del database, siano archiviati all'interno di *Web. config*. I segreti sono inevitabilmente salvati in posizioni non sicure, ad esempio il controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="f05cf-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="f05cf-253">Con blazer in ASP.NET Core, la configurazione precedente basata su XML viene sostituita con il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="f05cf-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="f05cf-254">JSON è il formato di configurazione predefinito. Tuttavia, ASP.NET Core supporta molti altri formati, incluso XML.</span><span class="sxs-lookup"><span data-stu-id="f05cf-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="f05cf-255">Sono disponibili anche diversi formati supportati dalla community.</span><span class="sxs-lookup"><span data-stu-id="f05cf-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="f05cf-256">Il costruttore nella classe del progetto Blazer `Startup` accetta un' `IConfiguration` istanza tramite una tecnica DI inserimento di un costruttore:</span><span class="sxs-lookup"><span data-stu-id="f05cf-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

<span data-ttu-id="f05cf-257">Per impostazione predefinita, le variabili di ambiente, i file JSON (*appSettings. JSON* e *appSettings. { Environment}. JSON*) e le opzioni della riga di comando vengono registrate come origini di configurazione valide nell'oggetto di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="f05cf-258">È possibile accedere alle origini di configurazione tramite `Configuration[key]` .</span><span class="sxs-lookup"><span data-stu-id="f05cf-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="f05cf-259">Una tecnica più avanzata consiste nell'associare i dati di configurazione agli oggetti usando il modello di opzioni.</span><span class="sxs-lookup"><span data-stu-id="f05cf-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="f05cf-260">Per ulteriori informazioni sulla configurazione e sul modello di opzioni, vedere la pagina relativa alla [configurazione nella ASP.NET Core](/aspnet/core/fundamentals/configuration/) e nel [modello di opzioni rispettivamente in ASP.NET Core](/aspnet/core/fundamentals/configuration/options).</span><span class="sxs-lookup"><span data-stu-id="f05cf-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="f05cf-261">Migrare l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="f05cf-261">Migrate data access</span></span>

<span data-ttu-id="f05cf-262">L'accesso ai dati è un aspetto importante di qualsiasi app.</span><span class="sxs-lookup"><span data-stu-id="f05cf-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="f05cf-263">Il progetto eShop archivia le informazioni del catalogo in un database e recupera i dati con Entity Framework (EF) 6.</span><span class="sxs-lookup"><span data-stu-id="f05cf-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="f05cf-264">Poiché EF 6 è supportato in .NET Core 3,0, il progetto può continuare a usarlo.</span><span class="sxs-lookup"><span data-stu-id="f05cf-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="f05cf-265">Per l'eShop sono state necessarie le seguenti modifiche correlate a EF:</span><span class="sxs-lookup"><span data-stu-id="f05cf-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="f05cf-266">In .NET Framework, l' `DbContext` oggetto accetta una stringa nel formato *nome = ConnectionString* e usa la stringa di connessione da `ConfigurationManager.AppSettings[ConnectionString]` per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="f05cf-267">In .NET Core questa operazione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f05cf-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="f05cf-268">È necessario specificare la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="f05cf-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="f05cf-269">È stato eseguito l'accesso al database in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="f05cf-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="f05cf-270">Sebbene questo funzioni, la scalabilità potrebbe soffrire.</span><span class="sxs-lookup"><span data-stu-id="f05cf-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="f05cf-271">Questa logica deve essere spostata in un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="f05cf-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="f05cf-272">Sebbene non esista lo stesso supporto nativo per il binding del set di dati, blazer garantisce flessibilità e potenza con il supporto C# in una pagina Razor.</span><span class="sxs-lookup"><span data-stu-id="f05cf-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="f05cf-273">Ad esempio, è possibile eseguire calcoli e visualizzare il risultato.</span><span class="sxs-lookup"><span data-stu-id="f05cf-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="f05cf-274">Per ulteriori informazioni sui modelli di dati in blazer, vedere il capitolo relativo all' [accesso ai dati](data.md) .</span><span class="sxs-lookup"><span data-stu-id="f05cf-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="f05cf-275">Modifiche dell'architettura</span><span class="sxs-lookup"><span data-stu-id="f05cf-275">Architectural changes</span></span>

<span data-ttu-id="f05cf-276">Infine, esistono alcune importanti differenze di architettura da considerare quando si esegue la migrazione a blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="f05cf-277">Molte di queste modifiche sono applicabili a qualsiasi elemento basato su .NET Core o ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="f05cf-278">Poiché Blazer si basa su .NET Core, ci sono alcune considerazioni per garantire il supporto in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f05cf-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="f05cf-279">Alcune delle principali modifiche includono la rimozione delle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="f05cf-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="f05cf-280">Più AppDomain</span><span class="sxs-lookup"><span data-stu-id="f05cf-280">Multiple AppDomains</span></span>
- <span data-ttu-id="f05cf-281">Comunicazione remota</span><span class="sxs-lookup"><span data-stu-id="f05cf-281">Remoting</span></span>
- <span data-ttu-id="f05cf-282">Sicurezza dall'accesso di codice (CAS, Code Access Security)</span><span class="sxs-lookup"><span data-stu-id="f05cf-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="f05cf-283">Trasparenza della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f05cf-283">Security Transparency</span></span>

<span data-ttu-id="f05cf-284">Per altre informazioni sulle tecniche per identificare le modifiche necessarie per supportare l'esecuzione in .NET Core, vedere [trasferire il codice da .NET Framework a .NET Core](/dotnet/core/porting).</span><span class="sxs-lookup"><span data-stu-id="f05cf-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="f05cf-285">ASP.NET Core è una versione ripensata di ASP.NET e presenta alcune modifiche che potrebbero non sembrare evidenti.</span><span class="sxs-lookup"><span data-stu-id="f05cf-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="f05cf-286">Di seguito sono riportate le modifiche principali:</span><span class="sxs-lookup"><span data-stu-id="f05cf-286">The main changes are:</span></span>

- <span data-ttu-id="f05cf-287">Nessun contesto di sincronizzazione, ovvero non sono presenti `HttpContext.Current` , `Thread.CurrentPrincipal` o altre funzioni di accesso statiche</span><span class="sxs-lookup"><span data-stu-id="f05cf-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="f05cf-288">Nessuna copia shadow</span><span class="sxs-lookup"><span data-stu-id="f05cf-288">No shadow copying</span></span>
- <span data-ttu-id="f05cf-289">Nessuna coda di richieste</span><span class="sxs-lookup"><span data-stu-id="f05cf-289">No request queue</span></span>

<span data-ttu-id="f05cf-290">Molte operazioni nel ASP.NET Core sono asincrone, che consente di semplificare il caricamento delle attività associate a I/O.</span><span class="sxs-lookup"><span data-stu-id="f05cf-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="f05cf-291">È importante non bloccarsi mai usando `Task.Wait()` o `Task.GetResult()` , che può esaurire rapidamente le risorse del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="f05cf-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="f05cf-292">Conclusione della migrazione</span><span class="sxs-lookup"><span data-stu-id="f05cf-292">Migration conclusion</span></span>

<span data-ttu-id="f05cf-293">A questo punto, sono stati visualizzati molti esempi di ciò che serve per spostare un progetto Web Form in blazer.</span><span class="sxs-lookup"><span data-stu-id="f05cf-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="f05cf-294">Per un esempio completo, vedere il progetto [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) .</span><span class="sxs-lookup"><span data-stu-id="f05cf-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="f05cf-295">Indietro</span><span class="sxs-lookup"><span data-stu-id="f05cf-295">Previous</span></span>](security-authentication-authorization.md)
