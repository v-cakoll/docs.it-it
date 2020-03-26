---
title: Eseguire la migrazione da ASP.NET Web Form a Blazor
description: Informazioni su come eseguire la migrazione di un'app Web Form ASP.NET esistente a Blazor.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134082"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>Eseguire la migrazione da ASP.NET Web Form a Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La migrazione di una base di codice da Web Form ASP.NET a Blazor è un'attività che richiede molto tempo e richiede una pianificazione. Questo capitolo descrive il processo. Qualcosa che può facilitare la transizione consiste nell'assicurare che l'app aderisca a un'architettura *a più livelli,* in cui il modello di app (in questo caso, Web Form) è separato dalla logica di business. Questa separazione logica dei livelli rende chiaro cosa deve passare a .NET Core e Blazor.

Per questo esempio viene usata l'app eShop disponibile in [GitHub.For](https://github.com/dotnet-architecture/eShopOnBlazor) this example, the eShop app available on GitHub is used. eShop è un servizio di catalogo che fornisce funzionalità CRUD tramite l'immissione e la convalida del form.

Perché un'app funzionante deve essere migrata in Blazor? Molte volte, non ce n'è bisogno. ASP.NET Web Form continueranno a essere supportati per molti anni. Tuttavia, molte delle funzionalità fornite da Blazor sono supportate solo in un'app migrata. Tali caratteristiche includono:

- Miglioramenti delle prestazioni nel framework,`Span<T>`
- Possibilità di eseguire come WebAssembly
- Supporto multipiattaforma per Linux e macOS
- Distribuzione locale dell'app o distribuzione condivisa del framework senza influire sulle altre app

Se queste o altre nuove funzionalità sono sufficientemente interessanti, potrebbe esserci un valore nella migrazione dell'app. La migrazione può assumere forme diverse; può essere l'intera app o solo alcuni endpoint che richiedono le modifiche. La decisione di eseguire la migrazione si basa in ultima analisi sui problemi aziendali che devono essere risolti dallo sviluppatore.

## <a name="server-side-versus-client-side-hosting"></a>Hosting lato server e hosting lato client

Come descritto nel capitolo dei modelli di [hosting,](hosting-models.md) un'app Blazor può essere ospitata in due modi diversi: lato server e lato client. Il modello lato server utilizza ASP.NET connessioni Core SignalR per gestire gli aggiornamenti DOM durante l'esecuzione di qualsiasi codice effettivo sul server. Il modello lato client viene eseguito come WebAssembly all'interno di un browser e non richiede connessioni server. Ci sono una serie di differenze che possono influenzare che è meglio per un'applicazione specifica:

- L'esecuzione come WebAssembly è ancora in fase di sviluppo e potrebbe non supportare tutte le funzionalità (ad esempio il threading) al momento corrente
- La comunicazione chatty tra il client e il server può causare problemi di latenza in modalità lato server
- L'accesso ai database e ai servizi interni o protetti richiede un servizio separato con hosting lato client

Al momento della scrittura, il modello lato server è più simile a i Web Form. La maggior parte di questo capitolo si concentra sul modello di hosting lato server, in quanto è pronto per la produzione.

## <a name="create-a-new-project"></a>Creare un nuovo progetto

Questa fase iniziale di migrazione consiste nel creare un nuovo progetto. Questo tipo di progetto si basa sui progetti di stile SDK di .NET Core e semplifica gran parte del boilerplate utilizzato nei formati di progetto precedenti. Per ulteriori dettagli, vedere il capitolo sulla struttura del [progetto](project-structure.md).

Una volta creato il progetto, installare le librerie utilizzate nel progetto precedente. Nei progetti Web Form precedenti, è possibile che sia stato utilizzato il file *packages.config* per elencare i pacchetti NuGet necessari. Nel nuovo progetto in stile SDK, *packages.config* è stato sostituito con `<PackageReference>` elementi nel file di progetto. Un vantaggio di questo approccio è che tutte le dipendenze vengono installate in modo transitivo. Elencare solo le dipendenze di primo livello che ti interessano.

Molte delle dipendenze in uso sono disponibili per .NET Core, inclusi Entity Framework 6 e log4net. Se non è disponibile alcuna versione di .NET Core o .NET Standard, è spesso possibile usare la versione di .NET Framework. Il chilometraggio può variare. Qualsiasi API utilizzata non disponibile in .NET Core causa un errore di runtime. Visual Studio notifica tali pacchetti. Nel nodo **Riferimenti** del progetto in **Esplora soluzioni**viene visualizzata un'icona gialla.

Nel progetto eShop basato su Blazor, è possibile visualizzare i pacchetti installati. In precedenza, il file *packages.config* elencava tutti i pacchetti utilizzati nel progetto, generando un file lungo quasi 50 righe. Un frammento di *packages.config* è:

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

L'elemento `<packages>` include tutte le dipendenze necessarie. È difficile identificare quali di questi pacchetti sono inclusi perché sono necessari. Alcuni `<package>` elementi sono elencati semplicemente per soddisfare le esigenze delle dipendenze necessarie.

Il progetto Blazor elenca le dipendenze necessarie all'interno di un `<ItemGroup>` elemento nel file di progetto:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Un pacchetto NuGet che semplifica la vita degli sviluppatori Web Form è il pacchetto di [compatibilità di Windows.](../../core/porting/windows-compat-pack.md) Anche se .NET Core è multipiattaforma, alcune funzionalità sono disponibili solo in Windows. Le funzionalità specifiche di Windows vengono rese disponibili installando il pacchetto di compatibilità. Esempi di tali funzionalità includono il Registro di sistema, WMI e servizi directory. Il pacchetto aggiunge circa 20.000 API e attiva molti servizi con cui è già familiare. Il progetto eShop non richiede il pacchetto di compatibilità; ma se i progetti utilizzano funzionalità specifiche di Windows, il pacchetto semplifica le attività di migrazione.

## <a name="enable-startup-process"></a>Abilita processo di avvio

Il processo di avvio per Blazor è stato modificato rispetto a Web Form e segue una configurazione simile per altri servizi ASP.NET Core. Quando sono ospitati sul lato server, i componenti Blazor vengono eseguiti come parte di una normale app ASP.NET Core. Quando sono ospitati nel browser con WebAssembly, i componenti Blazor utilizzano un modello di hosting simile. La differenza è che i componenti vengono eseguiti come servizio separato da qualsiasi processo back-end. In entrambi i casi, l'avvio è simile.

Il *file Global.asax.cs* è la pagina di avvio predefinita per i progetti Web Form. Nel progetto eShop, questo file configura il contenitore Inversion of Control (IoC) e gestisce i vari eventi del ciclo di vita dell'app o della richiesta. Alcuni di questi eventi vengono gestiti `Application_BeginRequest`con middleware (ad esempio ). Altri eventi richiedono l'override di servizi specifici tramite inserimento delle dipendenze (DI).

A titolo di esempio, il *file di Global.asax.cs* per eShop contiene il codice seguente:

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
    /// http://docs.autofac.org/en/latest/integration/webforms.html
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

Il file precedente `Startup` diventa la classe in Blazor lato server:

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

Un cambiamento significativo che si può notare da Web Form è la prominenza di DI. DI è stato un principio guida nella progettazione ASP.NET Core. Supporta la personalizzazione di quasi tutti gli aspetti del framework ASP.NET Core. C'è anche un provider di servizi incorporato che può essere utilizzato per molti scenari. Se è necessaria una maggiore personalizzazione, può essere supportata dai numerosi progetti della community. Ad esempio, è possibile portare avanti l'investimento della libreria DI di terze parti.

Nell'app eShop originale, c'è una configurazione per la gestione delle sessioni. Poiché Blazor lato server utilizza ASP.NET Core SignalR per la comunicazione, lo stato della sessione non è supportato in quanto le connessioni possono verificarsi indipendentemente da un contesto HTTP. Un'app che usa lo stato sessione richiede una riprogettazione prima dell'esecuzione come app Blazor.

Per ulteriori informazioni sull'avvio dell'app, vedere [Avvio dell'app](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Eseguire la migrazione di moduli e gestori HTTP in middlewareMigrate HTTP modules and handlers to middleware

I moduli e i gestori HTTP sono modelli comuni nei Web Form per controllare la pipeline delle richieste HTTP. Classi che `IHttpModule` `IHttpHandler` implementano o possono essere registrate ed elaborano le richieste in ingresso. Web Form configura moduli e gestori nel file *web.config.* Web Form è anche fortemente basato sulla gestione degli eventi del ciclo di vita dell'app. ASP.NET Core utilizza invece il middleware. Il middleware viene `Configure` registrato `Startup` nel metodo della classe. L'ordine di esecuzione del middleware è determinato dall'ordine di registrazione.

Nella sezione Abilita processo di [avvio,](#enable-startup-process) un evento `Application_BeginRequest` del ciclo di vita è stato generato da Web Form come metodo. Questo evento non è disponibile in ASP.NET Core. Un modo per ottenere questo comportamento consiste nell'implementare middleware come illustrato nell'esempio di file *Startup.cs.* Questo middleware esegue la stessa logica e quindi trasferisce il controllo al gestore successivo nella pipeline middleware.

Per ulteriori informazioni sulla migrazione di moduli e gestori, vedere Eseguire la migrazione di [gestori e moduli HTTP a ASP.NET middleware di base](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Eseguire la migrazione di file staticiMigrate static files

Per gestire file statici (ad esempio, HTML, CSS, immagini e JavaScript), i file devono essere esposti dal middleware. La `UseStaticFiles` chiamata al metodo consente la gestione di file statici dal percorso radice Web. La directory principale Web predefinita è *wwwroot*, ma può essere personalizzata. Come incluso `Configure` nel metodo della `Startup` classe di eShop:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Il progetto eShop consente l'accesso ai file statici di base. Sono disponibili molte personalizzazioni per l'accesso ai file statici. Per informazioni sull'abilitazione dei file predefiniti o di un browser di file, consultate [File statici in ASP.NET Core.](/aspnet/core/fundamentals/static-files)

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Eseguire la migrazione dell'aggregazione di runtime e dell'impostazione di minimizzazioneMigrate runtime bundling and minification setup

L'aggregazione e la minimizzazione sono tecniche di ottimizzazione delle prestazioni per ridurre il numero e le dimensioni delle richieste del server per recuperare determinati tipi di file. JavaScript e CSS spesso subiscono una qualche forma di raggruppamento o minimizzazione prima di essere inviati al client. In ASP.NET Web Form queste ottimizzazioni vengono gestite in fase di esecuzione. Le convenzioni di ottimizzazione sono definite in un file *App_Start/BundleConfig.cs.The* optimization conventions are defined an App_Start/BundleConfig.cs file. In ASP.NET Core, viene adottato un approccio più dichiarativo. Un file elenca i file da minificare, insieme a specifiche impostazioni di minimizzazione.

Per ulteriori informazioni sull'aggregazione e la minimizzazione, consultate [Raggruppare e minimificare le risorse statiche in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Eseguire la migrazione delle pagine ASPXMigrate ASPX pages

Una pagina in un'app Web Form è un file con estensione *aspx.* Una pagina Web Form può spesso essere mappata a un componente in Blazor. Un componente Blazor viene creato in un file con estensione *.razor.* Per il progetto eShop, cinque pagine vengono convertite in una pagina Razor.

Ad esempio, la visualizzazione dettagli è costituita da tre file nel progetto Web Form: *Details.aspx*, *Details.aspx.cs*e *Details.aspx.designer.cs*. Durante la conversione in Blazor, il code-behind e il markup vengono combinati in *Details.razor*. La compilazione Razor (equivalente a quella presente nei file *designer.cs)* viene archiviata nella directory *obj* e non è, per impostazione predefinita, visualizzabile in **Esplora soluzioni**. La pagina Web Form è costituita dal markup seguente:

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

Il code-behind del markup precedente include il codice seguente:The preceding markup's code-behind includes the following code:

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

Quando viene convertita in Blazor, la pagina Web Form viene convertita nel codice seguente:

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

Si noti che il codice e il markup si trovano nello stesso file. Tutti i servizi necessari `@inject` sono resi accessibili con l'attributo . In `@page` base alla direttiva, è `Catalog/Details/{id}` possibile accedere a questa pagina in corrispondenza della route. Il valore del segnaposto `{id}` della route è stato vincolato a un numero intero. Come descritto nella sezione relativa al [routing,](pages-routing-layouts.md) a differenza di Web Form, un componente Razor indica in modo esplicito la route e gli eventuali parametri inclusi. Molti controlli Web Form potrebbero non avere controparti esatte in Blazor. C'è spesso uno snippet HTML equivalente che servirà allo stesso scopo. Ad esempio, `<asp:Label />` il controllo può `<label>` essere sostituito con un elemento HTML.

### <a name="model-validation-in-blazor"></a>Convalida del modello in Blazor

Se il codice Web Form include la convalida, è possibile trasferire gran parte di ciò che si ha con modifiche poco o nessun. Un vantaggio dell'esecuzione in Blazor è che la stessa logica di convalida può essere eseguita senza la necessità di JavaScript personalizzato. Le annotazioni dei dati consentono una facile convalida del modello.

Ad esempio, la pagina *Create.aspx* dispone di un form di immissione dati con convalida. Un frammento di codice di esempio sarebbe simile al seguente:An example snippet would look like this:

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

In Blazor, il markup equivalente viene fornito in un file *Create.razor:In* Blazor, the equivalent markup is provided in a Create.razor file:

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

Il `EditForm` contesto include il supporto di convalida e può essere eseguito il wrapping dell'input. Le annotazioni dei dati sono un modo comune per aggiungere la convalida. Tale supporto di convalida `DataAnnotationsValidator` può essere aggiunto tramite il componente. Per ulteriori informazioni su questo meccanismo, vedere [ASP.NET core moduli e convalida](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Eseguire la migrazione dei controlli Web Form incorporati

*Questo contenuto è in arrivo.*

## <a name="migrate-configuration"></a>Eseguire la migrazione della configurazione

In un progetto Web Form i dati di configurazione vengono in genere archiviati nel file *web.config.* Si accede ai `ConfigurationManager`dati di configurazione con . I servizi erano spesso necessari per analizzare gli oggetti. Con .NET Framework 4.7.2, la composizione `ConfigurationBuilders`è stata aggiunta alla configurazione tramite . Questi generatori hanno consentito agli sviluppatori di aggiungere varie origini per la configurazione che è stata quindi composta in fase di esecuzione per recuperare i valori necessari.

ASP.NET Core ha introdotto un sistema di configurazione flessibile che consente di definire l'origine o le origini di configurazione usate dall'app e dalla distribuzione. L'infrastruttura `ConfigurationBuilder` che è possibile utilizzare nell'app Web Form è stata modellata in base ai concetti utilizzati nel sistema di configurazione ASP.NET Core.

Nel frammento di codice seguente viene illustrato come il progetto Web Form eShop utilizza *web.config* per archiviare i valori di configurazione:

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

È comune che i segreti, ad esempio le stringhe di connessione al database, vengano archiviati all'interno del *file web.config*. I segreti sono inevitabilmente persistenti in posizioni non sicure, ad esempio il controllo del codice sorgente. With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON è il formato di configurazione predefinito. tuttavia, ASP.NET Core supporta molti altri formati, tra cui XML. Esistono anche diversi formati supportati dalla community.

Il costruttore nella classe del `Startup` progetto Blazor accetta un'istanza tramite una tecnica DI nota come inserimento del costruttore:The constructor in the Blazor project's class accepts an `IConfiguration` instance through a DI technique known as constructor injection:

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

Per impostazione predefinita, le variabili di ambiente, i file JSON (*appsettings.json* e *appsettings. Environment,json*) e le opzioni della riga di comando vengono registrate come origini di configurazione valide nell'oggetto di configurazione. È possibile accedere alle `Configuration[key]`origini di configurazione tramite . Una tecnica più avanzata consiste nell'associare i dati di configurazione agli oggetti utilizzando il modello di opzioni. Per ulteriori informazioni sulla configurazione e sul modello di opzioni, vedere [Configurazione in ASP.NET base](/aspnet/core/fundamentals/configuration/) e modello Opzioni in ASP.NET [Core](/aspnet/core/fundamentals/configuration/options), rispettivamente.

## <a name="migrate-data-access"></a>Eseguire la migrazione dell'accesso ai datiMigrate data

L'accesso ai dati è un aspetto importante di qualsiasi app. Il progetto eShop archivia le informazioni del catalogo in un database e recupera i dati con Entity Framework (EF) 6. Poiché EF 6 è supportato in .NET Core 3.0, il progetto può continuare a usarlo.

Per eShop sono state necessarie le seguenti modifiche relative a EF:

- In .NET Framework `DbContext` l'oggetto accetta una stringa con il *formato name,ConnectionString* e utilizza la stringa di connessione da `ConfigurationManager.AppSettings[ConnectionString]` per connettersi. In .NET Core, questo non è supportato. È necessario specificare la stringa di connessione.
- L'accesso al database è stato eseguito in modo sincrono. Anche se questo funziona, la scalabilità può risentire. Questa logica deve essere spostata in un modello asincrono.

Anche se non esiste lo stesso supporto nativo per l'associazione di set di dati, Blazor offre flessibilità e potenza con il supporto c'è in una pagina Razor. Ad esempio, è possibile eseguire calcoli e visualizzare il risultato. Per ulteriori informazioni sui modelli di dati in Blazor, vedere il capitolo [Accesso ai dati.](data.md)

## <a name="architectural-changes"></a>Modifiche architettoniche

Infine, ci sono alcune importanti differenze architettoniche da considerare quando si esegue la migrazione a Blazor. Molte di queste modifiche sono applicabili a qualsiasi elemento basato su .NET Core o ASP.NET Core.

Poiché Blazor è basato su .NET Core, esistono considerazioni per garantire il supporto in .NET Core.Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core. Alcune delle principali modifiche includono la rimozione delle seguenti caratteristiche:

- Più Domini Applicazione
- Comunicazione remota
- Sicurezza dall'accesso di codice (CAS, Code Access Security)
- Trasparenza della sicurezza

Per ulteriori informazioni sulle tecniche per identificare le modifiche necessarie per supportare l'esecuzione in .NET Core, vedere [Eseguire il porting del codice da .NET Framework a .NET Core](/dotnet/core/porting).

ASP.NET Core è una versione rivisitata di ASP.NET e presenta alcune modifiche che potrebbero non sembrare inizialmente ovvie. I principali cambiamenti sono:

- Nessun contesto di sincronizzazione, `HttpContext.Current` `Thread.CurrentPrincipal`il che significa che non sono presenti funzioni di accesso , , o altre funzioni di accesso statiche
- Nessuna copia shadow
- Nessuna coda di richieste

Molte operazioni in ASP.NET Core sono asincrone, che consentono un'operazione di scaricamento più semplice delle attività associate a I/O.Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks. È importante non bloccare `Task.Wait()` mai `Task.GetResult()`utilizzando o , che può esaurire rapidamente le risorse del pool di thread.

## <a name="migration-conclusion"></a>Conclusione della migrazione

A questo punto, sono stati illustrati molti esempi di ciò che serve per spostare un progetto Web Form in Blazor. Per un esempio completo, vedere il progetto [eShopOnBlazor.For](https://github.com/dotnet-architecture/eShopOnBlazor) a full example, see the eShopOnBlazor project.

>[!div class="step-by-step"]
>[Indietro](security-authentication-authorization.md)
