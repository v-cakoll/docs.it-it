---
title: Configurazione dell'app
description: Informazioni su come configurare le Blazor app senza usare ConfigurationManager.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/01/2020
ms.openlocfilehash: a13f663c2c6908ba906e42cb939c3b8707b8cccd
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173315"
---
# <a name="app-configuration"></a><span data-ttu-id="3fdf2-103">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="3fdf2-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="3fdf2-104">Il modo principale per caricare la configurazione delle app in Web Form è costituito dalle voci del file *web.config* nel &mdash; Server o da un file di configurazione correlato a cui viene fatto riferimento da *web.config*. È possibile usare l' `ConfigurationManager` oggetto statico per interagire con le impostazioni dell'app, le stringhe di connessione del repository dei dati e altri provider di configurazione estesa aggiunti nell'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="3fdf2-105">È tipico vedere interazioni con la configurazione dell'app, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="3fdf2-106">Con ASP.NET Core e lato server Blazor , il file *web.config* può essere presente se l'app è ospitata in un server IIS di Windows.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="3fdf2-107">Tuttavia, non esiste alcuna `ConfigurationManager` interazione con questa configurazione ed è possibile ricevere una configurazione più strutturata dell'app da altre origini.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="3fdf2-108">Esaminiamo ora come viene raccolta la configurazione e come è ancora possibile accedere alle informazioni di configurazione da un file di *web.config* .</span><span class="sxs-lookup"><span data-stu-id="3fdf2-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="3fdf2-109">Origini della configurazione</span><span class="sxs-lookup"><span data-stu-id="3fdf2-109">Configuration sources</span></span>

<span data-ttu-id="3fdf2-110">ASP.NET Core riconosce il numero di origini di configurazione che è possibile usare per l'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="3fdf2-111">Il Framework tenta di offrire il meglio di queste funzionalità per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="3fdf2-112">La configurazione viene letta e aggregata da queste varie origini ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="3fdf2-113">I valori caricati in un secondo momento per la stessa chiave di configurazione hanno la precedenza sui valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="3fdf2-114">ASP.NET Core è stato progettato per essere compatibile con il cloud e semplificare la configurazione delle app per gli operatori e gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="3fdf2-115">ASP.NET Core è compatibile con l'ambiente e sa se è in esecuzione nell' `Production` `Development` ambiente o.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="3fdf2-116">L'indicatore di ambiente viene impostato nella `ASPNETCORE_ENVIRONMENT` variabile di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="3fdf2-117">Se non è configurato alcun valore, l'impostazione predefinita dell'app è in esecuzione nell' `Production` ambiente.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="3fdf2-118">L'app può attivare e aggiungere la configurazione da diverse origini in base al nome dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="3fdf2-119">Per impostazione predefinita, la configurazione viene caricata dalle risorse seguenti nell'ordine elencato:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="3fdf2-120">*appsettings.jsnel* file, se presente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="3fdf2-121">*appSettings. File {ENVIRONMENT_NAME}. JSON* , se presente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="3fdf2-122">File dei segreti utente sul disco, se presente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="3fdf2-123">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-123">Environment variables</span></span>
1. <span data-ttu-id="3fdf2-124">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="3fdf2-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="3fdf2-125">appsettings.jsal formato e all'accesso</span><span class="sxs-lookup"><span data-stu-id="3fdf2-125">appsettings.json format and access</span></span>

<span data-ttu-id="3fdf2-126">Il *appsettings.jssu* file può essere gerarchico con valori strutturati come il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="3fdf2-127">Quando viene presentato con il codice JSON precedente, il sistema di configurazione rende Flat i valori figlio e fa riferimento ai percorsi gerarchici completi.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="3fdf2-128">Il carattere due punti ( `:` ) separa ogni proprietà della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="3fdf2-129">Ad esempio, la chiave `section1:key0` di configurazione accede al `section1` valore del valore letterale dell'oggetto `key0` .</span><span class="sxs-lookup"><span data-stu-id="3fdf2-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="3fdf2-130">Segreti utente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-130">User secrets</span></span>

<span data-ttu-id="3fdf2-131">I segreti utente sono:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-131">User secrets are:</span></span>

* <span data-ttu-id="3fdf2-132">Valori di configurazione archiviati in un file JSON nella workstation dello sviluppatore, al di fuori della cartella di sviluppo dell'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="3fdf2-133">Viene caricato solo quando è in esecuzione nell' `Development` ambiente.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="3fdf2-134">Associato a un'app specifica.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-134">Associated with a specific app.</span></span>
* <span data-ttu-id="3fdf2-135">Gestito con il comando interfaccia della riga di comando di .NET Core `user-secrets` .</span><span class="sxs-lookup"><span data-stu-id="3fdf2-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="3fdf2-136">Configurare l'app per l'archiviazione dei segreti eseguendo il `user-secrets` comando:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="3fdf2-137">Il comando precedente aggiunge un `UserSecretsId` elemento al file di progetto.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="3fdf2-138">L'elemento contiene un GUID, che viene usato per associare i segreti all'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="3fdf2-139">È quindi possibile definire un segreto con il `set` comando.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="3fdf2-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="3fdf2-141">Il comando precedente rende `Parent:ApiKey` disponibile la chiave di configurazione nella workstation di uno sviluppatore con il valore `12345` .</span><span class="sxs-lookup"><span data-stu-id="3fdf2-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="3fdf2-142">Per ulteriori informazioni sulla creazione, l'archiviazione e la gestione dei segreti utente, vedere la pagina relativa all' [archiviazione sicura di segreti dell'app in fase di sviluppo in ASP.NET Core](/aspnet/core/security/app-secrets) documento.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="3fdf2-143">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="3fdf2-143">Environment variables</span></span>

<span data-ttu-id="3fdf2-144">Il set successivo di valori caricati nella configurazione dell'app è costituito dalle variabili di ambiente del sistema.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="3fdf2-145">Tutte le impostazioni delle variabili di ambiente del sistema sono ora accessibili tramite l'API di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="3fdf2-146">I valori gerarchici sono bidimensionali e separati da due punti quando vengono letti all'interno dell'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="3fdf2-147">Alcuni sistemi operativi, tuttavia, non consentono i nomi delle variabili di ambiente con due punti.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="3fdf2-148">ASP.NET Core risolve questa limitazione convertendo i valori che hanno due caratteri di sottolineatura ( `__` ) in un segno di due punti quando ne viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="3fdf2-149">Il `Parent:ApiKey` valore della sezione segreti utente precedente può essere sostituito con la variabile di ambiente `Parent__ApiKey` .</span><span class="sxs-lookup"><span data-stu-id="3fdf2-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="3fdf2-150">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="3fdf2-150">Command-line arguments</span></span>

<span data-ttu-id="3fdf2-151">La configurazione può essere fornita anche come argomenti della riga di comando all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="3fdf2-152">Usare la notazione doppio trattino ( `--` ) o barra ( `/` ) per indicare il nome del valore di configurazione da impostare e il valore da configurare.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="3fdf2-153">La sintassi è simile ai comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="3fdf2-154">Restituito di web.config</span><span class="sxs-lookup"><span data-stu-id="3fdf2-154">The return of web.config</span></span>

<span data-ttu-id="3fdf2-155">Se l'app è stata distribuita in Windows in IIS, il file di *web.config* Configura comunque IIS per gestire l'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="3fdf2-156">Per impostazione predefinita, in IIS viene aggiunto un riferimento al modulo ASP.NET Core (modulo ASP.NET Core).</span><span class="sxs-lookup"><span data-stu-id="3fdf2-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="3fdf2-157">MODULO ASP.NET Core è un modulo IIS nativo che ospita l'app al posto del server Web gheppio.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="3fdf2-158">Questa *web.config* sezione è simile al markup XML seguente:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="3fdf2-159">La configurazione specifica dell'app può essere definita annidando un `environmentVariables` elemento nell' `aspNetCore` elemento.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="3fdf2-160">I valori definiti in questa sezione vengono presentati all'app ASP.NET Core come variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="3fdf2-161">Le variabili di ambiente vengono caricate in modo appropriato durante il segmento di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="3fdf2-162">Leggere la configurazione nell'app</span><span class="sxs-lookup"><span data-stu-id="3fdf2-162">Read configuration in the app</span></span>

<span data-ttu-id="3fdf2-163">ASP.NET Core fornisce la configurazione dell'app tramite l' <xref:Microsoft.Extensions.Configuration.IConfiguration> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="3fdf2-164">Questa interfaccia di configurazione deve essere richiesta dai Blazor componenti, dalle Blazor pagine e da qualsiasi altra classe gestita da ASP.NET Core che richiede l'accesso alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="3fdf2-165">Il Framework di ASP.NET Core compilerà automaticamente questa interfaccia con la configurazione risolta configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="3fdf2-166">In una Blazor pagina o in un markup Razor di un componente, è possibile inserire l' `IConfiguration` oggetto con una `@inject` direttiva nella parte superiore del file *Razor* come segue:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="3fdf2-167">Questa istruzione precedente rende l' `IConfiguration` oggetto disponibile come `Configuration` variabile in tutto il resto del modello Razor.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="3fdf2-168">È possibile leggere le singole impostazioni di configurazione specificando la gerarchia delle impostazioni di configurazione cercata come parametro dell'indicizzatore:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="3fdf2-169">È possibile recuperare intere sezioni di configurazione usando il <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> metodo per recuperare una raccolta di chiavi in una posizione specifica con una sintassi simile a `GetSection("section1")` per recuperare la configurazione per sezione1 dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="3fdf2-170">Configurazione fortemente tipizzata</span><span class="sxs-lookup"><span data-stu-id="3fdf2-170">Strongly typed configuration</span></span>

<span data-ttu-id="3fdf2-171">Con Web Form, è possibile creare un tipo di configurazione fortemente tipizzato che eredita dal <xref:System.Configuration.ConfigurationSection> tipo e dai tipi associati.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="3fdf2-172">Un oggetto `ConfigurationSection` consentiva di configurare alcune regole business ed elaborarle per tali valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="3fdf2-173">In ASP.NET Core, è possibile specificare una gerarchia di classi che riceverà i valori di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="3fdf2-174">Queste classi:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-174">These classes:</span></span>

* <span data-ttu-id="3fdf2-175">Non è necessario ereditare da una classe padre.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="3fdf2-176">Deve includere `public` proprietà che corrispondono alle proprietà e ai riferimenti ai tipi per la struttura di configurazione che si desidera acquisire.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="3fdf2-177">Per il *appsettings.jsprecedente in* esempio, è possibile definire le classi seguenti per acquisire i valori:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="3fdf2-178">Questa gerarchia di classi può essere popolata aggiungendo la riga seguente al `Startup.ConfigureServices` Metodo:</span><span class="sxs-lookup"><span data-stu-id="3fdf2-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="3fdf2-179">Nel resto dell'app è possibile aggiungere un parametro di input alle classi o una `@inject` direttiva nei modelli Razor di tipo `IOptions<MyConfig>` per ricevere le impostazioni di configurazione fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="3fdf2-180">La `IOptions<MyConfig>.Value` Proprietà produrrà il `MyConfig` valore popolato dalle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="3fdf2-181">Altre informazioni sulla funzionalità opzioni sono disponibili nel [modello di opzioni in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) documento.</span><span class="sxs-lookup"><span data-stu-id="3fdf2-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3fdf2-182">[Precedente](middleware.md) 
> [Avanti](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="3fdf2-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
