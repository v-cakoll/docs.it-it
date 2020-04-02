---
title: Configurazione dell'app
description: Informazioni su come configurare le app Blazor senza usare ConfigurationManager.Learn how to configure Blazor apps without using ConfigurationManager.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588240"
---
# <a name="app-configuration"></a><span data-ttu-id="a7534-103">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="a7534-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a7534-104">Il modo principale per caricare la configurazione dell'app nei&mdash;Web Form consiste nel utilizzare le voci nel file *web.config* nel server o in un file di configurazione correlato a cui fa riferimento *web.config*. Puoi usare l'oggetto statico `ConfigurationManager` per interagire con le impostazioni dell'app, le stringhe di connessione al repository dati e altri provider di configurazione estesa aggiunti all'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="a7534-105">È tipico visualizzare le interazioni con la configurazione dell'app come illustrato nel codice seguente:It's typical to see interactions with app configuration as seen in the following code:</span><span class="sxs-lookup"><span data-stu-id="a7534-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="a7534-106">Con ASP.NET Core e sul lato server Blazor, il file *web.config* può essere presente se l'app è ospitata in un server Windows IIS.</span><span class="sxs-lookup"><span data-stu-id="a7534-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="a7534-107">Tuttavia, non `ConfigurationManager` esiste alcuna interazione con questa configurazione ed è possibile ricevere una configurazione dell'app più strutturata da altre origini.</span><span class="sxs-lookup"><span data-stu-id="a7534-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="a7534-108">Diamo un'occhiata a come viene raccolta la configurazione e come è ancora possibile accedere alle informazioni di configurazione da un file *web.config.*</span><span class="sxs-lookup"><span data-stu-id="a7534-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="a7534-109">Origini della configurazione</span><span class="sxs-lookup"><span data-stu-id="a7534-109">Configuration sources</span></span>

<span data-ttu-id="a7534-110">ASP.NET Core riconosce che esistono molte origini di configurazione che potresti voler usare per la tua app.</span><span class="sxs-lookup"><span data-stu-id="a7534-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="a7534-111">Il framework tenta di offrire il meglio di queste funzionalità per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a7534-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="a7534-112">La configurazione viene letta e aggregata da queste varie origini da ASP.NET Core.Configuration is read and aggregated from these various sources by ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7534-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="a7534-113">I valori caricati successivamente per la stessa chiave di configurazione hanno la precedenza sui valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="a7534-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="a7534-114">ASP.NET Core è stato progettato per essere in grado di riconoscere il cloud e per semplificare la configurazione delle app sia per gli operatori che per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="a7534-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="a7534-115">ASP.NET Core è in grado di riconoscere l'ambiente e sa se è in esecuzione nel proprio `Production` ambiente o. `Development`</span><span class="sxs-lookup"><span data-stu-id="a7534-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="a7534-116">L'indicatore di ambiente `ASPNETCORE_ENVIRONMENT` è impostato nella variabile di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="a7534-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="a7534-117">Se non è configurato alcun valore, per `Production` impostazione predefinita l'app viene eseguita nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a7534-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="a7534-118">L'app può attivare e aggiungere la configurazione da diverse origini in base al nome dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a7534-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="a7534-119">Per impostazione predefinita, la configurazione viene caricata dalle risorse seguenti nell'ordine elencato:By default, configuration is loaded from the following resources in the order listed:</span><span class="sxs-lookup"><span data-stu-id="a7534-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="a7534-120">*file appsettings.json,* se presente</span><span class="sxs-lookup"><span data-stu-id="a7534-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="a7534-121">*impostazioni dell'app. file ENVIRONMENT_NAME.json,* se presente</span><span class="sxs-lookup"><span data-stu-id="a7534-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="a7534-122">File dei segreti utente sul disco, se presente</span><span class="sxs-lookup"><span data-stu-id="a7534-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="a7534-123">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="a7534-123">Environment variables</span></span>
1. <span data-ttu-id="a7534-124">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="a7534-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="a7534-125">appsettings.json formato e accesso</span><span class="sxs-lookup"><span data-stu-id="a7534-125">appsettings.json format and access</span></span>

<span data-ttu-id="a7534-126">Il file *appsettings.json* può essere gerarchico con valori strutturati come il seguente JSON:</span><span class="sxs-lookup"><span data-stu-id="a7534-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

<span data-ttu-id="a7534-127">Quando viene presentato con il codice JSON precedente, il sistema di configurazione appiattisce i valori figlio e fa riferimento ai relativi percorsi gerarchici completi.</span><span class="sxs-lookup"><span data-stu-id="a7534-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="a7534-128">Un carattere due punti (`:`) separa ogni proprietà nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="a7534-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="a7534-129">Ad esempio, la `section1:key0` chiave di `section1` configurazione accede `key0` al valore del valore letterale dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a7534-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="a7534-130">Segreti utente</span><span class="sxs-lookup"><span data-stu-id="a7534-130">User secrets</span></span>

<span data-ttu-id="a7534-131">I segreti utente sono:</span><span class="sxs-lookup"><span data-stu-id="a7534-131">User secrets are:</span></span>

* <span data-ttu-id="a7534-132">Valori di configurazione archiviati in un file JSON nella workstation dello sviluppatore, all'esterno della cartella di sviluppo dell'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="a7534-133">Caricato solo durante `Development` l'esecuzione nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a7534-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="a7534-134">Associato a un'app specifica.</span><span class="sxs-lookup"><span data-stu-id="a7534-134">Associated with a specific app.</span></span>
* <span data-ttu-id="a7534-135">Gestito con il comando dell'interfaccia della riga di comando `user-secrets` di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7534-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="a7534-136">Configurare l'app per l'archiviazione dei segreti eseguendo il comando:Configure your app for secrets storage by executing the `user-secrets` command:</span><span class="sxs-lookup"><span data-stu-id="a7534-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="a7534-137">Il comando precedente `UserSecretsId` aggiunge un elemento al file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a7534-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="a7534-138">L'elemento contiene un GUID, che viene usato per associare segreti all'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="a7534-139">È quindi possibile definire `set` un segreto con il comando.</span><span class="sxs-lookup"><span data-stu-id="a7534-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="a7534-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a7534-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="a7534-141">Il comando precedente `Parent:ApiKey` rende disponibile la chiave di configurazione `12345`sulla workstation di uno sviluppatore con il valore .</span><span class="sxs-lookup"><span data-stu-id="a7534-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="a7534-142">Per altre informazioni sulla creazione, l'archiviazione e la gestione dei segreti utente, vedere [l'archiviazione sicura dei segreti dell'app in fase](/aspnet/core/security/app-secrets) di sviluppo in ASP.NET documento core.</span><span class="sxs-lookup"><span data-stu-id="a7534-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="a7534-143">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="a7534-143">Environment variables</span></span>

<span data-ttu-id="a7534-144">Il set successivo di valori caricati nella configurazione dell'app sono le variabili di ambiente del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7534-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="a7534-145">Tutte le impostazioni delle variabili di ambiente del sistema sono ora accessibili all'utente tramite l'API di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7534-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="a7534-146">I valori gerarchici vengono appiattiti e separati da due punti quando vengono letti all'interno dell'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="a7534-147">Tuttavia, alcuni sistemi operativi non consentono i nomi delle variabili di ambiente dei due punti.</span><span class="sxs-lookup"><span data-stu-id="a7534-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="a7534-148">ASP.NET Core risolve questa limitazione convertendo i`__`valori con caratteri di sottolineatura doppi ( ) in due punti quando vi si accede.</span><span class="sxs-lookup"><span data-stu-id="a7534-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="a7534-149">Il `Parent:ApiKey` valore della sezione dei segreti utente precedente `Parent__ApiKey`può essere sostituito con la variabile di ambiente .</span><span class="sxs-lookup"><span data-stu-id="a7534-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="a7534-150">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="a7534-150">Command-line arguments</span></span>

<span data-ttu-id="a7534-151">La configurazione può essere fornita anche come argomenti della riga di comando all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="a7534-152">Utilizzare la notazione`--`double-dash (`/`) o barra rovesciata ( ) per indicare il nome del valore di configurazione da impostare e il valore da configurare.</span><span class="sxs-lookup"><span data-stu-id="a7534-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="a7534-153">La sintassi è simile ai seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="a7534-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="a7534-154">La restituzione di web.config</span><span class="sxs-lookup"><span data-stu-id="a7534-154">The return of web.config</span></span>

<span data-ttu-id="a7534-155">Se l'app è stata distribuita in Windows in IIS, il file *web.config* configura comunque IIS per gestire l'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="a7534-156">Per impostazione predefinita, IIS aggiunge un riferimento al ASP.NET Core Module (ANCM).</span><span class="sxs-lookup"><span data-stu-id="a7534-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="a7534-157">ANCM è un modulo IIS nativo che ospita l'app al posto del server Web Kestrel.</span><span class="sxs-lookup"><span data-stu-id="a7534-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="a7534-158">Questa sezione *web.config* è simile al markup XML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7534-158">This *web.config* section resembles the following XML markup:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

<span data-ttu-id="a7534-159">La configurazione specifica dell'app può `environmentVariables` essere `aspNetCore` definita annidando un elemento nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="a7534-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="a7534-160">I valori definiti in questa sezione vengono presentati all'app ASP.NET Core come variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="a7534-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="a7534-161">Le variabili di ambiente vengono caricate in modo appropriato durante tale segmento di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="a7534-161">The environment variables load appropriately during that segment of app startup.</span></span>

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="a7534-162">Leggere la configurazione nell'appRead configuration in the app</span><span class="sxs-lookup"><span data-stu-id="a7534-162">Read configuration in the app</span></span>

<span data-ttu-id="a7534-163">ASP.NET Core fornisce la <xref:Microsoft.Extensions.Configuration.IConfiguration> configurazione dell'app tramite l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a7534-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="a7534-164">Questa interfaccia di configurazione deve essere richiesta dai componenti Blazor, dalle pagine Blazor e da qualsiasi altra classe gestita da ASP.NET Core che deve accedere alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7534-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="a7534-165">Il framework ASP.NET Core popolerà automaticamente questa interfaccia con la configurazione risolta configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a7534-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="a7534-166">In una pagina Blazor o il markup Razor `IConfiguration` di un `@inject` componente, è possibile inserire l'oggetto con una direttiva nella parte superiore del file *.razor* come questo:</span><span class="sxs-lookup"><span data-stu-id="a7534-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="a7534-167">Questa istruzione precedente `IConfiguration` rende l'oggetto disponibile come `Configuration` variabile in tutto il resto del Razor modello.</span><span class="sxs-lookup"><span data-stu-id="a7534-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="a7534-168">È possibile leggere singole impostazioni di configurazione specificando la gerarchia delle impostazioni di configurazione ricercata come parametro dell'indicizzatore:Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span><span class="sxs-lookup"><span data-stu-id="a7534-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="a7534-169">È possibile recuperare intere <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> sezioni di configurazione utilizzando il metodo per recuperare `GetSection("section1")` una raccolta di chiavi in una posizione specifica con una sintassi simile a recuperare la configurazione per section1 dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="a7534-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="a7534-170">Configurazione fortemente tipata</span><span class="sxs-lookup"><span data-stu-id="a7534-170">Strongly typed configuration</span></span>

<span data-ttu-id="a7534-171">Con Web Form è stato possibile creare un tipo di <xref:System.Configuration.ConfigurationSection> configurazione fortemente tipizzato che eredita dal tipo e dai tipi associati.</span><span class="sxs-lookup"><span data-stu-id="a7534-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="a7534-172">Un `ConfigurationSection` ha consentito di configurare alcune regole di business e l'elaborazione per tali valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7534-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="a7534-173">In ASP.NET Core, è possibile specificare una gerarchia di classi che riceverà i valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7534-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="a7534-174">Queste classi:</span><span class="sxs-lookup"><span data-stu-id="a7534-174">These classes:</span></span>

* <span data-ttu-id="a7534-175">Non è necessario ereditare da una classe padre.</span><span class="sxs-lookup"><span data-stu-id="a7534-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="a7534-176">Deve `public` includere le proprietà che corrispondono alle proprietà e ai riferimenti al tipo per la struttura di configurazione che si desidera acquisire.</span><span class="sxs-lookup"><span data-stu-id="a7534-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="a7534-177">Per l'esempio appsettings.json precedente, è possibile definire le classi seguenti per acquisire i valori:For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span><span class="sxs-lookup"><span data-stu-id="a7534-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

<span data-ttu-id="a7534-178">Questa gerarchia di classi può essere `Startup.ConfigureServices` popolata aggiungendo la riga seguente al metodo:This class hierarchy can be populated by adding the following line to the method:</span><span class="sxs-lookup"><span data-stu-id="a7534-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="a7534-179">Nel resto dell'app, è possibile aggiungere un `@inject` parametro di input `IOptions<MyConfig>` alle classi o una direttiva nei modelli Razor di tipo per ricevere le impostazioni di configurazione fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="a7534-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="a7534-180">La `IOptions<MyConfig>.Value` proprietà produrrà il `MyConfig` valore popolato dalle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7534-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="a7534-181">Ulteriori informazioni sulla funzionalità Opzioni sono disponibili nel modello Opzioni del documento [Base ASP.NET.](/aspnet/core/fundamentals/configuration/options#options-interfaces)</span><span class="sxs-lookup"><span data-stu-id="a7534-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a7534-182">[Successivo](middleware.md)
>[precedente](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="a7534-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
