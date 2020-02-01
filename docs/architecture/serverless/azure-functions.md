---
title: Funzioni di Azure-app senza server
description: Funzioni di Azure offre funzionalità senza server tra più linguaggiC#(, JavaScript, Java) e piattaforme per fornire codice di scalabilità immediata basato sugli eventi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920970"
---
# <a name="azure-functions"></a>Funzioni di Azure

Funzioni di Azure offre un'esperienza di calcolo senza server. Una funzione viene richiamata da un *trigger* , ad esempio l'accesso a un endpoint HTTP o un timer, ed esegue un blocco di codice o logica di business. Le funzioni supportano inoltre *associazioni* specializzate che si connettono a risorse come l'archiviazione e le code.

![Logo di funzioni di Azure](./media/azure-functions-logo.png)

Sono disponibili due versioni del Framework di funzioni di Azure. La versione legacy supporta il .NET Framework completo e il nuovo Runtime supporta le applicazioni .NET Core multipiattaforma. Sono supportate altre C# lingue oltre ad esempio F#JavaScript, e Java. Le funzioni create nel portale forniscono una sintassi di scripting avanzata. Le funzioni create come progetti autonomi possono essere distribuite con funzionalità e supporto completo per la piattaforma.

Per altre informazioni, vedere la [documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Funzioni V1 e V2

Sono disponibili due versioni del runtime di funzioni di Azure: 1. x e 2. x. La versione 1. x è disponibile a livello generale (GA). Supporta lo sviluppo .NET dal portale o dai computer Windows e usa il .NET Framework. 1. x supporta C#, JavaScript e F#, con supporto sperimentale per Python, php, typescript, batch, bash e PowerShell.

[La versione 2. x è ora disponibile](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)a livello generale. Si avvale di .NET Core e supporta lo sviluppo multipiattaforma sui computer Windows, macOS e Linux. 2. x aggiunge un supporto di prima classe per Java ma non supporta ancora direttamente nessuno dei linguaggi sperimentali. La versione 2. x usa un nuovo modello di estendibilità dell'associazione che consente estensioni di terze parti per la piattaforma, il controllo delle versioni indipendente delle associazioni e un ambiente di esecuzione più semplificato.

> **Si è verificato un problema noto in 1. x con supporto per il [Reindirizzamento dell'associazione](https://github.com/Azure/azure-functions-host/issues/992).** Il problema è specifico per lo sviluppo in .NET. Sono interessati i progetti con dipendenze dalle librerie che hanno una versione diversa rispetto alle librerie incluse nel Runtime. Il team di funzioni si è impegnato a compiere un progressi concreto sul problema. Il team affronterà i reindirizzamenti di binding in 2. x prima di passare alla disponibilità generale. L'istruzione ufficiale del team con correzioni e soluzioni alternative consigliate è disponibile qui: [risoluzione degli assembly in funzioni di Azure](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Per ulteriori informazioni, vedere [compare 1. x e 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Supporto del linguaggio di programmazione

Le lingue seguenti sono supportate in disponibilità generale (GA), anteprima o sperimentale.

|Lingua:      |1. x         |2.x      |
|--------------|------------|---------|
|**C#**        |Disponibilità a livello generale          |Preview  |
|**JavaScript**|Disponibilità a livello generale          |Preview  |
|**F#**        |Disponibilità a livello generale          |         |
|**Java**      |            |Preview  |
|**Python**    |Sperimentale|         |
|**PHP**       |Sperimentale|         |
|**TypeScript**|Sperimentale|         |
|**Batch**     |Sperimentale|         |
|**Bash**      |Sperimentale|         |
|**PowerShell**|Sperimentale|         |

Per ulteriori informazioni, vedere [linguaggi supportati](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Piani di servizio app

Le funzioni sono supportate da un *piano di servizio app*. Il piano definisce le risorse usate dall'app per le funzioni. È possibile assegnare piani a un'area, determinare le dimensioni e il numero di macchine virtuali che verranno usate e scegliere un piano tariffario. Per un vero approccio senza server, le app per le funzioni possono usare il piano a **consumo** . Il piano a consumo eseguirà il ridimensionamento automatico del back-end in base al carico.

Per altre informazioni, vedere [piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Creare la prima funzione

Esistono tre modi comuni per creare app per le funzioni.

- Funzioni di script nel portale.
- Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure.
- Consente di compilare localmente le funzioni usando l'IDE preferito e di pubblicarle in Azure.

Per altre informazioni sulla creazione di una funzione con script nel portale, vedere [creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Per compilare dall'interfaccia della riga di comando di Azure, vedere [creare la prima funzione usando l'interfaccia della](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)riga di comando di Azure.

Per creare una funzione da Visual Studio, vedere [creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Informazioni sui trigger e sulle associazioni

Le funzioni vengono richiamate da un *trigger* e possono avere esattamente una. Oltre a richiamare la funzione, alcuni trigger vengono utilizzati anche come associazioni. È anche possibile definire più associazioni oltre al trigger. Le *associazioni* forniscono una modalità dichiarativa per connettere i dati al codice. Possono essere passati (input) o ricevere dati (output). I trigger e le associazioni facilitano l'utilizzo delle funzioni. Le associazioni rimuovono l'overhead della creazione manuale di connessioni di database o file system. Tutte le informazioni necessarie per le associazioni sono contenute in un file *Functions. JSON* speciale per gli script o dichiarati con attributi nel codice.

Alcuni trigger comuni includono:

- Archiviazione BLOB: richiamare la funzione quando un file o una cartella viene caricata o modificata nello spazio di archiviazione.
- HTTP: richiama la funzione come un'API REST.
- Queue: richiama la funzione quando gli elementi sono presenti in una coda.
- Timer: richiamare la funzione a cadenza regolare.

Di seguito sono riportati alcuni esempi di binding:

- CosmosDB: consente di connettersi facilmente al database per caricare o salvare i file.
- Archiviazione tabelle: usare l'archiviazione di chiave/valore dall'app per le funzioni.
- Archiviazione code: è possibile recuperare facilmente elementi da una coda o inserire nuovi elementi nella coda.

Il file *Functions. JSON* di esempio seguente definisce un trigger e un'associazione:

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

In questo esempio, la funzione viene attivata da una modifica all'archiviazione BLOB nel contenitore `images`. Le informazioni per il file vengono passate, quindi il trigger funge anche da Binding. Esiste un'altra associazione per inserire le informazioni in una coda denominata `images`.

Di seguito è C# riportato lo script per la funzione:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

L'esempio è una funzione semplice che accetta il nome del file che è stato modificato o caricato nell'archivio BLOB e lo inserisce in una coda per l'elaborazione successiva.

Per un elenco completo dei trigger e delle associazioni, vedere [concetti relativi a trigger e associazioni di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Proxy

I proxy forniscono la funzionalità di reindirizzamento per l'applicazione. I proxy espongono un endpoint ed eseguire il mapping dell'endpoint a un'altra risorsa. Con i proxy è possibile:

- Reindirizzare una richiesta in ingresso a un altro endpoint.
- Modificare la richiesta in ingresso prima che venga passata.
- Modificare o fornire una risposta.

I proxy vengono usati per scenari come:

- Semplificazione, abbreviazione o modifica dell'URL.
- Fornire un prefisso API coerente a più servizi back-end.
- Simulazione di una risposta a un endpoint in fase di sviluppo.
- Fornire una risposta statica a un endpoint noto.
- Mantenere coerente un endpoint API mentre viene spostato o migrato il back-end.

I proxy vengono archiviati come definizioni JSON. Ecco un esempio:

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

Il proxy `Domain Redirect` accetta una route abbreviata e ne esegue il mapping alla risorsa della funzione più lunga. La trasformazione ha un aspetto simile al seguente:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Il proxy `Root` esegue qualsiasi operazione inviata all'URL radice (`https://--shorturl--/`) e la reindirizza al sito della documentazione.

Un esempio di uso di proxy è illustrato nel video [Azure: portare l'app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/events/Connect/2017/E102). In tempo reale, viene eseguita la migrazione di un'applicazione ASP.NET Core in esecuzione su SQL Server locale al cloud di Azure. I proxy vengono usati per eseguire il refactoring di un progetto API Web tradizionale per l'uso di funzioni.

Per altre informazioni sui proxy, vedere [usare proxy di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
>[Precedente](azure-serverless-platform.md)
>[Successivo](application-insights.md)
