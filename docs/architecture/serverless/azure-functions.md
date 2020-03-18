---
title: Funzioni di Azure - App senza serverAzure Functions - Serverless apps
description: Le funzioni di Azure offrono funzionalità senza server in più linguaggi (C, JavaScript, Java) e piattaforme per fornire codice con scalabilità istantanea basato su eventi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401613"
---
# <a name="azure-functions"></a>Funzioni di Azure

Le funzioni di Azure offrono un'esperienza di calcolo senza server. Una funzione viene richiamata da un *trigger* (ad esempio l'accesso a un endpoint HTTP o un timer) ed esegue un blocco di codice o logica di business. Le funzioni supportano anche *associazioni specializzate* che si connettono a risorse come archiviazione e code.

![Logo delle funzioni di AzureAzure functions logo](./media/azure-functions-logo.png)

Esistono due versioni del framework Funzioni di Azure.There are two versions of the Azure Functions framework. La versione legacy supporta la versione completa di .NET Framework e il nuovo runtime supporta le applicazioni .NET Core multipiattaforma. Sono supportati linguaggi aggiuntivi oltre a C, ad esempio JavaScript, F e Java. Le funzioni create nel portale forniscono una sintassi di script avanzata. Le funzioni create come progetti autonomi possono essere distribuite con funzionalità e supporto completo della piattaforma.

Per altre informazioni, vedere la [documentazione](https://docs.microsoft.com/azure/azure-functions)relativa alle funzioni di Azure.For more information, see Azure Functions documentation .

## <a name="functions-v1-vs-v2"></a>Funzioni v1 e v2

Esistono due versioni del runtime di Funzioni di Azure: 1.x e 2.x.There are two versions of the Azure Functions runtime: 1.x and 2.x. La versione 1.x è generalmente disponibile (GA). Supporta lo sviluppo .NET dal portale o dai computer Windows e utilizza .NET Framework. 1.x supporta il linguaggio C, JavaScript e F, con il supporto sperimentale per Python, PHP, TypeScript, Batch, Bash e PowerShell.

Anche la [versione 2.x è generalmente disponibile ora](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). Sfrutta .NET Core e supporta lo sviluppo multipiattaforma su computer Windows, macOS e Linux. 2.x aggiunge il supporto di prima classe per Java, ma non supporta ancora direttamente nessuno dei linguaggi sperimentali. La versione 2.x usa un nuovo modello di estendibilità dell'associazione che consente estensioni di terze parti alla piattaforma, il controllo delle versioni indipendente delle associazioni e un ambiente di esecuzione più semplificato.

> **Esiste un problema noto in 1.x con [supporto di reindirizzamento binding](https://github.com/Azure/azure-functions-host/issues/992).** Il problema è specifico per lo sviluppo .NET. I progetti con dipendenze da librerie che sono una versione diversa dalle librerie incluse nel runtime sono interessati. Il team delle funzioni si è impegnato a compiere progressi concreti sul problema. Il team si occuperà dei reindirizzamenti di binding in 2.x prima di passare alla disponibilità generale. La dichiarazione ufficiale del team con le correzioni e le soluzioni alternative suggerite è disponibile qui: [Risoluzione dell'assembly in Funzioni](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)di Azure .

Per ulteriori informazioni, vedere [Confrontare 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Supporto del linguaggio di programmazione

Le lingue seguenti sono supportate in generale availability (GA), preview o sperimentale.

|Linguaggio      |1.x         |2.x      |
|--------------|------------|---------|
|**C #**        |GA          |Anteprima  |
|**Javascript**|GA          |Anteprima  |
|**F #**        |GA          |         |
|**Java**      |            |Anteprima  |
|**Python**    |Sperimentale|         |
|**Php**       |Sperimentale|         |
|**TypeScript**|Sperimentale|         |
|**lotto**     |Sperimentale|         |
|**Bash**      |Sperimentale|         |
|**Powershell**|Sperimentale|         |

Per altre informazioni, vedere [Linguaggi supportati](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Piani di servizio app

Le funzioni sono supportate da un piano di *servizio app.* Il piano definisce le risorse usate dall'app funzioni. È possibile assegnare piani a un'area, determinare le dimensioni e il numero di macchine virtuali che verranno utilizzate e selezionare un piano tariffario. Per un vero approccio senza server, le app per le funzioni possono usare il piano di **consumo.** Il piano di consumo scalerà automaticamente il back-end in base al carico.

Per altre informazioni, vedere [Piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Creare la prima funzione

Esistono tre modi comuni per creare app per le funzioni.

- Funzioni di script nel portale.
- Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure.Create the necessary resources using the Azure CLI.
- Creare funzioni in locale usando l'IDE preferito e pubblicarle in Azure.Build functions locally using your favorite IDE and publish them to Azure.

Per altre informazioni sulla creazione di una funzione con script nel portale, vedere Creare la prima funzione nel portale di Azure.For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal.](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)

Per eseguire la compilazione dall'interfaccia della riga di comando di Azure, vedere [Creare la prima funzione usando l'interfaccia della riga di comando](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)di Azure.To build from the Azure CLI, see Create your first function using the Azure CLI.

Per creare una funzione da Visual Studio, vedere [Creare la prima funzione utilizzando Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Comprendere i trigger e le associazioni

Le funzioni vengono richiamate da un *trigger* e possono averne esattamente uno. Oltre a richiamare la funzione, alcuni trigger fungono anche da associazioni. È inoltre possibile definire più associazioni oltre al trigger. *Le associazioni* forniscono un modo dichiarativo per connettere i dati al codice. Possono essere passati (input) o ricevere dati (output). I trigger e le associazioni semplificano l'utilizzo delle funzioni. Le associazioni rimuovono l'overhead della creazione manuale di connessioni al database o al file system. Tutte le informazioni necessarie per le associazioni sono contenute in un file *functions.json* speciale per gli script o dichiarate con attributi nel codice.

Alcuni trigger comuni includono:Some common triggers include:

- Archiviazione BLOB: richiamare la funzione quando un file o una cartella viene caricata o modificata nell'archiviazione.
- HTTP: richiamare la funzione come un'API REST.
- Coda: richiama la funzione quando gli elementi sono presenti in una coda.
- Timer: richiamare la funzione a cadenza regolare.

Esempi di associazioni includono:Examples of bindings include:

- CosmosDB: connettiti facilmente al database per caricare o salvare i file.
- Archiviazione tabelle: usare l'archiviazione con chiave/valore dall'app per le funzioni.
- Archiviazione delle code: recupera facilmente gli elementi da una coda o inserisci nuovi elementi nella coda.

Il file *functions.json di* esempio seguente definisce un trigger e un'associazione:The following example functions.json file defines a trigger and a binding:

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

In questo esempio, la funzione viene attivata da `images` una modifica all'archiviazione BLOB nel contenitore. Le informazioni per il file vengono passate, pertanto il trigger funge anche da associazione. Esiste un'altra associazione per `images`inserire informazioni in una coda denominata .

Di seguito è riportato lo script di C ' per la funzione:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

L'esempio è una funzione semplice che accetta il nome del file modificato o caricato nell'archiviazione BLOB e lo inserisce in una coda per un'elaborazione successiva.

Per un elenco completo dei trigger e delle associazioni, vedere Concetti relativi [ai trigger e](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)alle associazioni di Funzioni di Azure.

## <a name="proxies"></a>Proxy

I proxy forniscono funzionalità di reindirizzamento per l'applicazione. I proxy espongono un endpoint ed eseguono il mapping di tale endpoint a un'altra risorsa. Con i proxy, è possibile:

- Reindirizzare una richiesta in ingresso a un altro endpoint.
- Modificare la richiesta in ingresso prima che venga passata.
- Modificare o fornire una risposta.

I proxy vengono utilizzati per scenari quali:Proxies are used for scenarios such as:

- Semplificazione, accorciamento o modifica dell'URL.
- Fornire un prefisso API coerente a più servizi back-end.
- Risposta a un endpoint in fase di sviluppo.
- Fornire una risposta statica a un endpoint noto.
- Mantenere coerente un endpoint API durante lo spostamento o la migrazione del back-end.

I proxy vengono archiviati come definizioni JSON. Esempio:

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

Il `Domain Redirect` proxy accetta una route abbreviata e ne esegue il mapping alla risorsa funzione più lunga. La trasformazione è simile alla:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Il `Root` proxy accetta qualsiasi elemento`https://--shorturl--/`inviato all'URL radice ( ) e lo reindirizza al sito della documentazione.

Un esempio di utilizzo dei proxy è illustrato nel video [Azure: Portare l'app nel cloud con Funzioni](https://channel9.msdn.com/events/Connect/2017/E102)di Azure senza server. In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud. I proxy vengono utilizzati per facilitare il refactoring di un progetto API Web tradizionale per l'utilizzo delle funzioni.

Per altre informazioni sui proxy, vedere Usare i proxy di Funzioni di Azure.For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Successivo](azure-serverless-platform.md)
>[precedente](application-insights.md)
