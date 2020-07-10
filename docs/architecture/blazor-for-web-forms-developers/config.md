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
# <a name="app-configuration"></a>Configurazione dell'app

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il modo principale per caricare la configurazione delle app in Web Form è costituito dalle voci del file *web.config* nel &mdash; Server o da un file di configurazione correlato a cui viene fatto riferimento da *web.config*. È possibile usare l' `ConfigurationManager` oggetto statico per interagire con le impostazioni dell'app, le stringhe di connessione del repository dei dati e altri provider di configurazione estesa aggiunti nell'app. È tipico vedere interazioni con la configurazione dell'app, come illustrato nel codice seguente:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

Con ASP.NET Core e lato server Blazor , il file *web.config* può essere presente se l'app è ospitata in un server IIS di Windows. Tuttavia, non esiste alcuna `ConfigurationManager` interazione con questa configurazione ed è possibile ricevere una configurazione più strutturata dell'app da altre origini. Esaminiamo ora come viene raccolta la configurazione e come è ancora possibile accedere alle informazioni di configurazione da un file di *web.config* .

## <a name="configuration-sources"></a>Origini della configurazione

ASP.NET Core riconosce il numero di origini di configurazione che è possibile usare per l'app. Il Framework tenta di offrire il meglio di queste funzionalità per impostazione predefinita. La configurazione viene letta e aggregata da queste varie origini ASP.NET Core. I valori caricati in un secondo momento per la stessa chiave di configurazione hanno la precedenza sui valori precedenti.

ASP.NET Core è stato progettato per essere compatibile con il cloud e semplificare la configurazione delle app per gli operatori e gli sviluppatori. ASP.NET Core è compatibile con l'ambiente e sa se è in esecuzione nell' `Production` `Development` ambiente o. L'indicatore di ambiente viene impostato nella `ASPNETCORE_ENVIRONMENT` variabile di ambiente di sistema. Se non è configurato alcun valore, l'impostazione predefinita dell'app è in esecuzione nell' `Production` ambiente.

L'app può attivare e aggiungere la configurazione da diverse origini in base al nome dell'ambiente. Per impostazione predefinita, la configurazione viene caricata dalle risorse seguenti nell'ordine elencato:

1. *appsettings.jsnel* file, se presente
1. *appSettings. File {ENVIRONMENT_NAME}. JSON* , se presente
1. File dei segreti utente sul disco, se presente
1. Variabili di ambiente
1. Argomenti della riga di comando

## <a name="appsettingsjson-format-and-access"></a>appsettings.jsal formato e all'accesso

Il *appsettings.jssu* file può essere gerarchico con valori strutturati come il codice JSON seguente:

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

Quando viene presentato con il codice JSON precedente, il sistema di configurazione rende Flat i valori figlio e fa riferimento ai percorsi gerarchici completi. Il carattere due punti ( `:` ) separa ogni proprietà della gerarchia. Ad esempio, la chiave `section1:key0` di configurazione accede al `section1` valore del valore letterale dell'oggetto `key0` .

## <a name="user-secrets"></a>Segreti utente

I segreti utente sono:

* Valori di configurazione archiviati in un file JSON nella workstation dello sviluppatore, al di fuori della cartella di sviluppo dell'app.
* Viene caricato solo quando è in esecuzione nell' `Development` ambiente.
* Associato a un'app specifica.
* Gestito con il comando interfaccia della riga di comando di .NET Core `user-secrets` .

Configurare l'app per l'archiviazione dei segreti eseguendo il `user-secrets` comando:

```dotnetcli
dotnet user-secrets init
```

Il comando precedente aggiunge un `UserSecretsId` elemento al file di progetto. L'elemento contiene un GUID, che viene usato per associare i segreti all'app. È quindi possibile definire un segreto con il `set` comando. Ad esempio:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Il comando precedente rende `Parent:ApiKey` disponibile la chiave di configurazione nella workstation di uno sviluppatore con il valore `12345` .

Per ulteriori informazioni sulla creazione, l'archiviazione e la gestione dei segreti utente, vedere la pagina relativa all' [archiviazione sicura di segreti dell'app in fase di sviluppo in ASP.NET Core](/aspnet/core/security/app-secrets) documento.

## <a name="environment-variables"></a>Variabili di ambiente

Il set successivo di valori caricati nella configurazione dell'app è costituito dalle variabili di ambiente del sistema. Tutte le impostazioni delle variabili di ambiente del sistema sono ora accessibili tramite l'API di configurazione. I valori gerarchici sono bidimensionali e separati da due punti quando vengono letti all'interno dell'app. Alcuni sistemi operativi, tuttavia, non consentono i nomi delle variabili di ambiente con due punti. ASP.NET Core risolve questa limitazione convertendo i valori che hanno due caratteri di sottolineatura ( `__` ) in un segno di due punti quando ne viene eseguito l'accesso. Il `Parent:ApiKey` valore della sezione segreti utente precedente può essere sostituito con la variabile di ambiente `Parent__ApiKey` .

## <a name="command-line-arguments"></a>Argomenti della riga di comando

La configurazione può essere fornita anche come argomenti della riga di comando all'avvio dell'app. Usare la notazione doppio trattino ( `--` ) o barra ( `/` ) per indicare il nome del valore di configurazione da impostare e il valore da configurare. La sintassi è simile ai comandi seguenti:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Restituito di web.config

Se l'app è stata distribuita in Windows in IIS, il file di *web.config* Configura comunque IIS per gestire l'app. Per impostazione predefinita, in IIS viene aggiunto un riferimento al modulo ASP.NET Core (modulo ASP.NET Core). MODULO ASP.NET Core è un modulo IIS nativo che ospita l'app al posto del server Web gheppio. Questa *web.config* sezione è simile al markup XML seguente:

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

La configurazione specifica dell'app può essere definita annidando un `environmentVariables` elemento nell' `aspNetCore` elemento. I valori definiti in questa sezione vengono presentati all'app ASP.NET Core come variabili di ambiente. Le variabili di ambiente vengono caricate in modo appropriato durante il segmento di avvio dell'app.

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

## <a name="read-configuration-in-the-app"></a>Leggere la configurazione nell'app

ASP.NET Core fornisce la configurazione dell'app tramite l' <xref:Microsoft.Extensions.Configuration.IConfiguration> interfaccia. Questa interfaccia di configurazione deve essere richiesta dai Blazor componenti, dalle Blazor pagine e da qualsiasi altra classe gestita da ASP.NET Core che richiede l'accesso alla configurazione. Il Framework di ASP.NET Core compilerà automaticamente questa interfaccia con la configurazione risolta configurata in precedenza. In una Blazor pagina o in un markup Razor di un componente, è possibile inserire l' `IConfiguration` oggetto con una `@inject` direttiva nella parte superiore del file *Razor* come segue:

```razor
@inject IConfiguration Configuration
```

Questa istruzione precedente rende l' `IConfiguration` oggetto disponibile come `Configuration` variabile in tutto il resto del modello Razor.

È possibile leggere le singole impostazioni di configurazione specificando la gerarchia delle impostazioni di configurazione cercata come parametro dell'indicizzatore:

```csharp
var mySetting = Configuration["section1:key0"];
```

È possibile recuperare intere sezioni di configurazione usando il <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> metodo per recuperare una raccolta di chiavi in una posizione specifica con una sintassi simile a `GetSection("section1")` per recuperare la configurazione per sezione1 dall'esempio precedente.

## <a name="strongly-typed-configuration"></a>Configurazione fortemente tipizzata

Con Web Form, è possibile creare un tipo di configurazione fortemente tipizzato che eredita dal <xref:System.Configuration.ConfigurationSection> tipo e dai tipi associati. Un oggetto `ConfigurationSection` consentiva di configurare alcune regole business ed elaborarle per tali valori di configurazione.

In ASP.NET Core, è possibile specificare una gerarchia di classi che riceverà i valori di configurazione. Queste classi:

* Non è necessario ereditare da una classe padre.
* Deve includere `public` proprietà che corrispondono alle proprietà e ai riferimenti ai tipi per la struttura di configurazione che si desidera acquisire.

Per il *appsettings.jsprecedente in* esempio, è possibile definire le classi seguenti per acquisire i valori:

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

Questa gerarchia di classi può essere popolata aggiungendo la riga seguente al `Startup.ConfigureServices` Metodo:

```csharp
services.Configure<MyConfig>(Configuration);
```

Nel resto dell'app è possibile aggiungere un parametro di input alle classi o una `@inject` direttiva nei modelli Razor di tipo `IOptions<MyConfig>` per ricevere le impostazioni di configurazione fortemente tipizzate. La `IOptions<MyConfig>.Value` Proprietà produrrà il `MyConfig` valore popolato dalle impostazioni di configurazione.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Altre informazioni sulla funzionalità opzioni sono disponibili nel [modello di opzioni in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) documento.

>[!div class="step-by-step"]
>[Precedente](middleware.md) 
> [Avanti](security-authentication-authorization.md)
