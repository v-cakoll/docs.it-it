---
title: Eseguire la migrazione da Web Form ASP.NET aBlazor
description: Informazioni su come eseguire la migrazione di un'app Web Form ASP.NET esistente a Blazor .
author: twsouthwick
ms.author: tasou
no-loc:
- Blazor
- WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 464d2f535acd3b9774fe240b4feeda1875f98022
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173146"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>Eseguire la migrazione da Web Form ASP.NET aBlazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La migrazione di una codebase da ASP.NET Web Forms a Blazor è un'attività dispendiosa in termini di tempo che richiede la pianificazione. Questo capitolo descrive il processo. Un elemento che può semplificare la transizione consiste nel garantire che l'app rispetti un'architettura a più *livelli* , in cui il modello di app (in questo caso, Web Form) è separato dalla logica di business. Questa separazione logica dei livelli rende chiaro cosa deve passare a .NET Core e Blazor .

Per questo esempio viene usata l'app eShop disponibile su [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) . eShop è un servizio di catalogo che fornisce funzionalità CRUD tramite l'immissione e la convalida del modulo.

Perché è necessario eseguire la migrazione di un'app funzionante a Blazor ? Spesso non è necessario. I Web Form ASP.NET continueranno a essere supportati per molti anni. Tuttavia, molte delle funzionalità fornite da Blazor sono supportate solo in un'app migrata. Tali funzionalità includono:

- Miglioramenti delle prestazioni nel Framework, ad esempio`Span<T>`
- Possibilità di esecuzione comeWebAssembly
- Supporto multipiattaforma per Linux e macOS
- Distribuzione app-Local o Framework condiviso senza conseguenze per altre app

Se queste o altre nuove funzionalità sono sufficientemente interessanti, potrebbe essere necessario eseguire la migrazione dell'app. La migrazione può assumere forme diverse; può essere l'intera app o solo determinati endpoint che richiedono le modifiche. La decisione di eseguire la migrazione è in definitiva basata sui problemi aziendali che devono essere risolti dallo sviluppatore.

## <a name="server-side-versus-client-side-hosting"></a>Hosting lato server e lato client

Come descritto nel capitolo [modelli di hosting](hosting-models.md) , un' Blazor app può essere ospitata in due modi diversi: lato server e lato client. Il modello sul lato server usa ASP.NET Core le connessioni SignalR per gestire gli aggiornamenti DOM durante l'esecuzione di qualsiasi codice effettivo sul server. Il modello sul lato client viene eseguito come WebAssembly all'interno di un browser e non richiede alcuna connessione al server. Esistono diverse differenze che possono influire sul meglio per un'app specifica:

- L'esecuzione di come WebAssembly è ancora in fase di sviluppo e potrebbe non supportare tutte le funzionalità, ad esempio il threading, all'ora corrente
- La comunicazione loquace tra il client e il server può causare problemi di latenza in modalità lato server
- L'accesso ai database e ai servizi interni o protetti richiede un servizio separato con hosting lato client

Al momento della stesura di questo articolo, il modello sul lato server è più simile a Web Forms. La maggior parte di questo capitolo è incentrata sul modello di hosting lato server, in quanto è pronto per l'ambiente di produzione.

## <a name="create-a-new-project"></a>Creare un nuovo progetto

Questo passaggio iniziale della migrazione prevede la creazione di un nuovo progetto. Questo tipo di progetto è basato sui progetti di stile SDK di .NET Core e semplifica la maggior parte degli standard usati nei formati di progetto precedenti. Per altri dettagli, vedere il capitolo sulla [struttura del progetto](project-structure.md).

Una volta creato il progetto, installare le librerie utilizzate nel progetto precedente. Nei progetti Web Form precedenti è possibile che sia stato usato il file di *packages.config* per elencare i pacchetti NuGet necessari. Nel nuovo progetto di tipo SDK *packages.config* è stato sostituito con `<PackageReference>` gli elementi nel file di progetto. Un vantaggio di questo approccio è che tutte le dipendenze vengono installate in modo transitivo. È possibile elencare solo le dipendenze di primo livello a cui si è interessati.

Molte delle dipendenze che usi sono disponibili per .NET Core, tra cui Entity Framework 6 e log4net. Se non è disponibile alcuna versione di .NET Core o .NET Standard, è spesso possibile usare la versione .NET Framework. Il chilometraggio potrebbe variare. Qualsiasi API usata che non è disponibile in .NET Core causa un errore di Runtime. Visual Studio invia notifiche a questi pacchetti. Viene visualizzata un'icona gialla sul nodo **riferimenti** del progetto in **Esplora soluzioni**.

Nel Blazor progetto eShop basato su, è possibile visualizzare i pacchetti installati. In precedenza, il file *packages.config* elencava tutti i pacchetti usati nel progetto, ottenendo un file di lunghezza quasi 50 righe. Un frammento di *packages.config* è:

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

L' `<packages>` elemento include tutte le dipendenze necessarie. È difficile identificare quali di questi pacchetti sono inclusi perché sono necessari. Alcuni `<package>` elementi sono elencati semplicemente per soddisfare le esigenze delle dipendenze necessarie.

Il Blazor progetto elenca le dipendenze necessarie all'interno `<ItemGroup>` di un elemento nel file di progetto:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Un pacchetto NuGet che semplifica la vita degli sviluppatori di Web Form è [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md). Sebbene .NET Core sia multipiattaforma, alcune funzionalità sono disponibili solo in Windows. Le funzionalità specifiche di Windows vengono rese disponibili tramite l'installazione di Compatibility Pack. Esempi di queste funzionalità includono il registro di sistema, WMI e i servizi directory. Il pacchetto aggiunge circa 20.000 API e attiva molti servizi con cui potrebbe essere già noto. Il progetto eShop non richiede il pacchetto di compatibilità. Tuttavia, se i progetti utilizzano funzionalità specifiche di Windows, il pacchetto semplifica le attività di migrazione.

## <a name="enable-startup-process"></a>Abilita processo di avvio

Il processo di avvio per Blazor è stato modificato da Web Form e segue una configurazione simile per altri servizi ASP.NET Core. Quando vengono ospitati sul lato server, Blazor i componenti vengono eseguiti come parte di una normale app ASP.NET Core. Quando sono ospitati nel browser con WebAssembly , i Blazor componenti utilizzano un modello di hosting simile. La differenza è che i componenti vengono eseguiti come servizio separato da uno qualsiasi dei processi back-end. In entrambi i casi, l'avvio è simile.

Il file *Global.asax.cs* è la pagina di avvio predefinita per i progetti Web Form. Nel progetto eShop questo file configura il contenitore di inversione del controllo (IoC) e gestisce i vari eventi del ciclo di vita dell'app o della richiesta. Alcuni di questi eventi vengono gestiti con middleware, ad esempio `Application_BeginRequest` . Per altri eventi è necessario eseguire l'override di servizi specifici tramite l'inserimento DI dipendenze.

A titolo di esempio, il file *Global.asax.cs* per eShop contiene il codice seguente:

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

Il file precedente diventa la `Startup` classe sul lato server Blazor :

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

Una modifica significativa che è possibile notare da Web Form è l'importanza di DI. DI è stato un principio guida nel ASP.NET Core progettazione. Supporta la personalizzazione di quasi tutti gli aspetti del framework ASP.NET Core. Esiste anche un provider di servizi predefinito che può essere usato per molti scenari. Se è necessaria una maggiore personalizzazione, può essere supportata dai numerosi progetti della community. Ad esempio, è possibile portare avanti l'investimento della libreria DI terze parti.

Nell'app eShop originale è presente una configurazione per la gestione delle sessioni. Poiché il lato server Blazor usa ASP.NET Core SignalR per la comunicazione, lo stato della sessione non è supportato perché le connessioni possono verificarsi indipendentemente da un contesto http. Un'app che usa lo stato della sessione richiede la riarchitettura prima di essere eseguita come Blazor app.

Per altre informazioni sull'avvio dell'app, vedere [avvio dell'app](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Eseguire la migrazione di moduli e gestori HTTP al middleware

I moduli e i gestori HTTP sono modelli comuni in Web Form per controllare la pipeline di richieste HTTP. Classi che implementano `IHttpModule` o `IHttpHandler` possono essere registrate ed elaborare richieste in ingresso. Web Form configura i moduli e i gestori nel file di *web.config* . Anche i Web Form sono molto basati sulla gestione degli eventi del ciclo di vita dell'app. ASP.NET Core usa invece il middleware. Il middleware è registrato nel `Configure` metodo della `Startup` classe. L'ordine di esecuzione del middleware è determinato dall'ordine di registrazione.

Nella sezione [Enable Startup Process](#enable-startup-process) è stato generato un evento Lifecycle da Web Form come `Application_BeginRequest` metodo. Questo evento non è disponibile in ASP.NET Core. Un modo per ottenere questo comportamento consiste nell'implementare il middleware come illustrato nell'esempio di file *Startup.cs* . Questo middleware esegue la stessa logica e quindi trasferisce il controllo al gestore successivo nella pipeline middleware.

Per altre informazioni sulla migrazione di moduli e gestori, vedere [eseguire la migrazione di moduli e gestori HTTP a ASP.NET Core middleware](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Esegui la migrazione dei file statici

Per gestire i file statici, ad esempio HTML, CSS, immagini e JavaScript, i file devono essere esposti dal middleware. La chiamata al `UseStaticFiles` metodo consente di mantenere i file statici dal percorso radice Web. La directory radice Web predefinita è *wwwroot*, ma può essere personalizzata. Come incluso nel `Configure` metodo della `Startup` classe eShop:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Il progetto eShop Abilita l'accesso ai file statici di base. Sono disponibili molte personalizzazioni per l'accesso ai file statici. Per informazioni sull'abilitazione dei file predefiniti o di un browser file, vedere [file statici in ASP.NET Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Eseguire la migrazione della creazione di bundle e della configurazione di minification

La creazione di bundle e minification sono tecniche di ottimizzazione delle prestazioni per ridurre il numero e le dimensioni delle richieste del server per recuperare determinati tipi di file. JavaScript e CSS spesso subiscono una forma di aggregazione o minification prima di essere inviati al client. In ASP.NET Web Forms queste ottimizzazioni vengono gestite in fase di esecuzione. Le convenzioni di ottimizzazione sono definite *app_start file/bundleconfig.cs* . In ASP.NET Core, viene adottato un approccio più dichiarativo. Un file elenca i file da minimizzati, insieme a impostazioni minification specifiche.

Per altre informazioni sulla creazione di bundle e minification, vedere [bundle e minimizzare asset statici in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Migrare pagine ASPX

Una pagina in un'app Web Form è un file con estensione *aspx* . Spesso è possibile eseguire il mapping di una pagina Web Form a un componente di Blazor . Un Blazor componente viene creato in un file con estensione *Razor* . Per il progetto eShop, cinque pagine vengono convertite in una pagina Razor.

Ad esempio, la visualizzazione dettagli comprende tre file nel progetto Web Form: *Details. aspx*, *Details.aspx.cs*e *Details.aspx.designer.cs*. Quando si Blazor esegue la conversione in, il code-behind e il markup vengono combinati in *Details. Razor*. La compilazione Razor (equivalente ai file con *estensione designer.cs* ) viene archiviata nella directory *obj* e, per impostazione predefinita, è visualizzabile in **Esplora soluzioni**. La pagina Web Form è costituita dal markup seguente:

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

Il code-behind del markup precedente include il codice seguente:

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

Quando viene convertito in Blazor , la pagina Web Form si traduce nel codice seguente:

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

Si noti che il codice e il markup si trovano nello stesso file. Tutti i servizi necessari vengono resi accessibili con l' `@inject` attributo. Per la `@page` direttiva, è possibile accedere a questa pagina nella `Catalog/Details/{id}` Route. Il valore del `{id}` segnaposto della route è stato vincolato a un numero intero. Come descritto nella sezione relativa al [routing](pages-routing-layouts.md) , a differenza dei Web Form, un componente Razor dichiara in modo esplicito la route e tutti i parametri inclusi. Molti controlli Web Form potrebbero non avere controparti esatte in Blazor . Spesso è presente un frammento HTML equivalente che servirà allo stesso scopo. Ad esempio, il `<asp:Label />` controllo può essere sostituito con un `<label>` elemento HTML.

### <a name="model-validation-in-blazor"></a>Convalida del modello inBlazor

Se il codice Web Form include la convalida, è possibile trasferire la maggior parte degli elementi disponibili con modifiche minime. Un vantaggio dell'esecuzione di in Blazor è che la stessa logica di convalida può essere eseguita senza la necessità di JavaScript personalizzato. Le annotazioni dei dati consentono di semplificare la convalida del modello.

La pagina *create. aspx* , ad esempio, contiene un form di immissione dati con convalida. Un frammento di esempio sarà simile al seguente:

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

In Blazor il markup equivalente viene fornito in un file *create. Razor* :

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

Il `EditForm` contesto include il supporto della convalida e può essere racchiuso tra input. Le annotazioni dei dati costituiscono un modo comune per aggiungere la convalida. Questo supporto della convalida può essere aggiunto tramite il `DataAnnotationsValidator` componente. Per ulteriori informazioni su questo meccanismo, vedere [ASP.NET Core Blazor Forms and Validation](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Eseguire la migrazione di controlli Web Form predefiniti

*Questo contenuto sarà presto disponibile.*

## <a name="migrate-configuration"></a>Eseguire la migrazione della configurazione

In un progetto Web Form i dati di configurazione vengono archiviati più di frequente nel file di *web.config* . È possibile accedere ai dati di configurazione con `ConfigurationManager` . I servizi erano spesso necessari per analizzare gli oggetti. Con .NET Framework 4.7.2, la composizione è stata aggiunta alla configurazione tramite `ConfigurationBuilders` . Questi generatori hanno consentito agli sviluppatori di aggiungere varie origini per la configurazione che è stata quindi composte in fase di esecuzione per recuperare i valori necessari.

In ASP.NET Core è stato introdotto un sistema di configurazione flessibile che consente di definire l'origine o le origini di configurazione usate dall'app e dalla distribuzione. L' `ConfigurationBuilder` infrastruttura che è possibile usare nell'app Web Form è stata modellata dopo i concetti usati nel sistema di configurazione ASP.NET Core.

Il frammento di codice seguente illustra come il progetto Web Forms eShop USA *web.config* per archiviare i valori di configurazione:

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

È frequente che i segreti, ad esempio le stringhe di connessione del database, vengano archiviati all'interno della *web.config*. I segreti sono inevitabilmente salvati in posizioni non sicure, ad esempio il controllo del codice sorgente. Con Blazor in ASP.NET Core, la configurazione precedente basata su XML viene sostituita con il codice JSON seguente:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON è il formato di configurazione predefinito. Tuttavia, ASP.NET Core supporta molti altri formati, incluso XML. Sono disponibili anche diversi formati supportati dalla community.

Il costruttore nella Blazor classe del progetto `Startup` accetta un' `IConfiguration` istanza tramite una tecnica di inserimento di un costruttore:

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

Per impostazione predefinita, le variabili di ambiente, i file JSON (*appsettings.jssu* e *appSettings. { Environment}. JSON*) e le opzioni della riga di comando vengono registrate come origini di configurazione valide nell'oggetto di configurazione. È possibile accedere alle origini di configurazione tramite `Configuration[key]` . Una tecnica più avanzata consiste nell'associare i dati di configurazione agli oggetti usando il modello di opzioni. Per ulteriori informazioni sulla configurazione e sul modello di opzioni, vedere la pagina relativa alla [configurazione nella ASP.NET Core](/aspnet/core/fundamentals/configuration/) e nel [modello di opzioni rispettivamente in ASP.NET Core](/aspnet/core/fundamentals/configuration/options).

## <a name="migrate-data-access"></a>Migrare l'accesso ai dati

L'accesso ai dati è un aspetto importante di qualsiasi app. Il progetto eShop archivia le informazioni del catalogo in un database e recupera i dati con Entity Framework (EF) 6. Poiché EF 6 è supportato in .NET Core 3,0, il progetto può continuare a usarlo.

Per l'eShop sono state necessarie le seguenti modifiche correlate a EF:

- In .NET Framework, l' `DbContext` oggetto accetta una stringa nel formato *nome = ConnectionString* e usa la stringa di connessione da `ConfigurationManager.AppSettings[ConnectionString]` per la connessione. In .NET Core questa operazione non è supportata. È necessario specificare la stringa di connessione.
- È stato eseguito l'accesso al database in modo sincrono. Sebbene questo funzioni, la scalabilità potrebbe soffrire. Questa logica deve essere spostata in un modello asincrono.

Sebbene non esista lo stesso supporto nativo per il binding del set di dati, Blazor offre flessibilità e potenza con il supporto C# in una pagina Razor. Ad esempio, è possibile eseguire calcoli e visualizzare il risultato. Per ulteriori informazioni sui modelli di dati in Blazor , vedere il capitolo relativo all' [accesso ai dati](data.md) .

## <a name="architectural-changes"></a>Modifiche dell'architettura

Infine, esistono alcune importanti differenze di architettura da considerare quando si esegue la migrazione a Blazor . Molte di queste modifiche sono applicabili a qualsiasi elemento basato su .NET Core o ASP.NET Core.

Poiché Blazor è basato su .NET Core, ci sono alcune considerazioni per garantire il supporto in .NET Core. Alcune delle principali modifiche includono la rimozione delle funzionalità seguenti:

- Più AppDomain
- Comunicazione remota
- Sicurezza dall'accesso di codice (CAS, Code Access Security)
- Trasparenza della sicurezza

Per altre informazioni sulle tecniche per identificare le modifiche necessarie per supportare l'esecuzione in .NET Core, vedere [trasferire il codice da .NET Framework a .NET Core](/dotnet/core/porting).

ASP.NET Core è una versione ripensata di ASP.NET e presenta alcune modifiche che potrebbero non sembrare evidenti. Di seguito sono riportate le modifiche principali:

- Nessun contesto di sincronizzazione, ovvero non sono presenti `HttpContext.Current` , `Thread.CurrentPrincipal` o altre funzioni di accesso statiche
- Nessuna copia shadow
- Nessuna coda di richieste

Molte operazioni nel ASP.NET Core sono asincrone, che consente di semplificare il caricamento delle attività associate a I/O. È importante non bloccarsi mai usando `Task.Wait()` o `Task.GetResult()` , che può esaurire rapidamente le risorse del pool di thread.

## <a name="migration-conclusion"></a>Conclusione della migrazione

A questo punto, sono stati visualizzati molti esempi di ciò che occorre per spostare un progetto Web Form in Blazor . Per un esempio completo, vedere il [progetto Blazor eShopOn](https://github.com/dotnet-architecture/eShopOnBlazor) .

>[!div class="step-by-step"]
>[Indietro](security-authentication-authorization.md)
