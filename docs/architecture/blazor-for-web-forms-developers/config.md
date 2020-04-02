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
# <a name="app-configuration"></a>Configurazione dell'app

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il modo principale per caricare la configurazione dell'app nei&mdash;Web Form consiste nel utilizzare le voci nel file *web.config* nel server o in un file di configurazione correlato a cui fa riferimento *web.config*. Puoi usare l'oggetto statico `ConfigurationManager` per interagire con le impostazioni dell'app, le stringhe di connessione al repository dati e altri provider di configurazione estesa aggiunti all'app. È tipico visualizzare le interazioni con la configurazione dell'app come illustrato nel codice seguente:It's typical to see interactions with app configuration as seen in the following code:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

Con ASP.NET Core e sul lato server Blazor, il file *web.config* può essere presente se l'app è ospitata in un server Windows IIS. Tuttavia, non `ConfigurationManager` esiste alcuna interazione con questa configurazione ed è possibile ricevere una configurazione dell'app più strutturata da altre origini. Diamo un'occhiata a come viene raccolta la configurazione e come è ancora possibile accedere alle informazioni di configurazione da un file *web.config.*

## <a name="configuration-sources"></a>Origini della configurazione

ASP.NET Core riconosce che esistono molte origini di configurazione che potresti voler usare per la tua app. Il framework tenta di offrire il meglio di queste funzionalità per impostazione predefinita. La configurazione viene letta e aggregata da queste varie origini da ASP.NET Core.Configuration is read and aggregated from these various sources by ASP.NET Core. I valori caricati successivamente per la stessa chiave di configurazione hanno la precedenza sui valori precedenti.

ASP.NET Core è stato progettato per essere in grado di riconoscere il cloud e per semplificare la configurazione delle app sia per gli operatori che per gli sviluppatori. ASP.NET Core è in grado di riconoscere l'ambiente e sa se è in esecuzione nel proprio `Production` ambiente o. `Development` L'indicatore di ambiente `ASPNETCORE_ENVIRONMENT` è impostato nella variabile di ambiente di sistema. Se non è configurato alcun valore, per `Production` impostazione predefinita l'app viene eseguita nell'ambiente.

L'app può attivare e aggiungere la configurazione da diverse origini in base al nome dell'ambiente. Per impostazione predefinita, la configurazione viene caricata dalle risorse seguenti nell'ordine elencato:By default, configuration is loaded from the following resources in the order listed:

1. *file appsettings.json,* se presente
1. *impostazioni dell'app. file ENVIRONMENT_NAME.json,* se presente
1. File dei segreti utente sul disco, se presente
1. Variabili di ambiente
1. Argomenti della riga di comando

## <a name="appsettingsjson-format-and-access"></a>appsettings.json formato e accesso

Il file *appsettings.json* può essere gerarchico con valori strutturati come il seguente JSON:

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

Quando viene presentato con il codice JSON precedente, il sistema di configurazione appiattisce i valori figlio e fa riferimento ai relativi percorsi gerarchici completi. Un carattere due punti (`:`) separa ogni proprietà nella gerarchia. Ad esempio, la `section1:key0` chiave di `section1` configurazione accede `key0` al valore del valore letterale dell'oggetto.

## <a name="user-secrets"></a>Segreti utente

I segreti utente sono:

* Valori di configurazione archiviati in un file JSON nella workstation dello sviluppatore, all'esterno della cartella di sviluppo dell'app.
* Caricato solo durante `Development` l'esecuzione nell'ambiente.
* Associato a un'app specifica.
* Gestito con il comando dell'interfaccia della riga di comando `user-secrets` di .NET Core.

Configurare l'app per l'archiviazione dei segreti eseguendo il comando:Configure your app for secrets storage by executing the `user-secrets` command:

```dotnetcli
dotnet user-secrets init
```

Il comando precedente `UserSecretsId` aggiunge un elemento al file di progetto. L'elemento contiene un GUID, che viene usato per associare segreti all'app. È quindi possibile definire `set` un segreto con il comando. Ad esempio:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Il comando precedente `Parent:ApiKey` rende disponibile la chiave di configurazione `12345`sulla workstation di uno sviluppatore con il valore .

Per altre informazioni sulla creazione, l'archiviazione e la gestione dei segreti utente, vedere [l'archiviazione sicura dei segreti dell'app in fase](/aspnet/core/security/app-secrets) di sviluppo in ASP.NET documento core.

## <a name="environment-variables"></a>Variabili di ambiente

Il set successivo di valori caricati nella configurazione dell'app sono le variabili di ambiente del sistema. Tutte le impostazioni delle variabili di ambiente del sistema sono ora accessibili all'utente tramite l'API di configurazione. I valori gerarchici vengono appiattiti e separati da due punti quando vengono letti all'interno dell'app. Tuttavia, alcuni sistemi operativi non consentono i nomi delle variabili di ambiente dei due punti. ASP.NET Core risolve questa limitazione convertendo i`__`valori con caratteri di sottolineatura doppi ( ) in due punti quando vi si accede. Il `Parent:ApiKey` valore della sezione dei segreti utente precedente `Parent__ApiKey`può essere sostituito con la variabile di ambiente .

## <a name="command-line-arguments"></a>Argomenti della riga di comando

La configurazione può essere fornita anche come argomenti della riga di comando all'avvio dell'app. Utilizzare la notazione`--`double-dash (`/`) o barra rovesciata ( ) per indicare il nome del valore di configurazione da impostare e il valore da configurare. La sintassi è simile ai seguenti comandi:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>La restituzione di web.config

Se l'app è stata distribuita in Windows in IIS, il file *web.config* configura comunque IIS per gestire l'app. Per impostazione predefinita, IIS aggiunge un riferimento al ASP.NET Core Module (ANCM). ANCM è un modulo IIS nativo che ospita l'app al posto del server Web Kestrel. Questa sezione *web.config* è simile al markup XML seguente:

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

La configurazione specifica dell'app può `environmentVariables` essere `aspNetCore` definita annidando un elemento nell'elemento. I valori definiti in questa sezione vengono presentati all'app ASP.NET Core come variabili di ambiente. Le variabili di ambiente vengono caricate in modo appropriato durante tale segmento di avvio dell'app.

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

## <a name="read-configuration-in-the-app"></a>Leggere la configurazione nell'appRead configuration in the app

ASP.NET Core fornisce la <xref:Microsoft.Extensions.Configuration.IConfiguration> configurazione dell'app tramite l'interfaccia. Questa interfaccia di configurazione deve essere richiesta dai componenti Blazor, dalle pagine Blazor e da qualsiasi altra classe gestita da ASP.NET Core che deve accedere alla configurazione. Il framework ASP.NET Core popolerà automaticamente questa interfaccia con la configurazione risolta configurata in precedenza. In una pagina Blazor o il markup Razor `IConfiguration` di un `@inject` componente, è possibile inserire l'oggetto con una direttiva nella parte superiore del file *.razor* come questo:

```razor
@inject IConfiguration Configuration
```

Questa istruzione precedente `IConfiguration` rende l'oggetto disponibile come `Configuration` variabile in tutto il resto del Razor modello.

È possibile leggere singole impostazioni di configurazione specificando la gerarchia delle impostazioni di configurazione ricercata come parametro dell'indicizzatore:Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:

```csharp
var mySetting = Configuration["section1:key0"];
```

È possibile recuperare intere <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> sezioni di configurazione utilizzando il metodo per recuperare `GetSection("section1")` una raccolta di chiavi in una posizione specifica con una sintassi simile a recuperare la configurazione per section1 dall'esempio precedente.

## <a name="strongly-typed-configuration"></a>Configurazione fortemente tipata

Con Web Form è stato possibile creare un tipo di <xref:System.Configuration.ConfigurationSection> configurazione fortemente tipizzato che eredita dal tipo e dai tipi associati. Un `ConfigurationSection` ha consentito di configurare alcune regole di business e l'elaborazione per tali valori di configurazione.

In ASP.NET Core, è possibile specificare una gerarchia di classi che riceverà i valori di configurazione. Queste classi:

* Non è necessario ereditare da una classe padre.
* Deve `public` includere le proprietà che corrispondono alle proprietà e ai riferimenti al tipo per la struttura di configurazione che si desidera acquisire.

Per l'esempio appsettings.json precedente, è possibile definire le classi seguenti per acquisire i valori:For the earlier *appsettings.json* sample, you could define the following classes to capture the values:

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

Questa gerarchia di classi può essere `Startup.ConfigureServices` popolata aggiungendo la riga seguente al metodo:This class hierarchy can be populated by adding the following line to the method:

```csharp
services.Configure<MyConfig>(Configuration);
```

Nel resto dell'app, è possibile aggiungere un `@inject` parametro di input `IOptions<MyConfig>` alle classi o una direttiva nei modelli Razor di tipo per ricevere le impostazioni di configurazione fortemente tipizzate. La `IOptions<MyConfig>.Value` proprietà produrrà il `MyConfig` valore popolato dalle impostazioni di configurazione.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Ulteriori informazioni sulla funzionalità Opzioni sono disponibili nel modello Opzioni del documento [Base ASP.NET.](/aspnet/core/fundamentals/configuration/options#options-interfaces)

>[!div class="step-by-step"]
>[Successivo](middleware.md)
>[precedente](security-authentication-authorization.md)
