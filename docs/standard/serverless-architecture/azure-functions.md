---
title: Funzioni di Azure - App senza server
description: Funzioni di Azure offrono funzionalità senza server in più lingue (c#, JavaScript, Java) e le piattaforme per fornire immediata guidato dagli eventi scalabilità codice.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: f08ba20b485197acd3bb5cdfe5699cd6be991d7c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369951"
---
# <a name="azure-functions"></a>Funzioni di Azure

Funzioni di Azure offre un'esperienza di calcolo senza server. Una funzione viene richiamata da un *trigger* (ad esempio l'accesso a un endpoint HTTP o un timer) ed esegue un blocco di codice o logica di business. Funzioni anche supporto specializzato *associazioni* che si connettono a risorse quali archiviazione e code.

![Logo di funzioni di Azure](./media/azure-functions-logo.png)

Sono disponibili due versioni di framework funzioni di Azure. La versione legacy supporta la versione completa di .NET Framework e il nuovo runtime supporta le applicazioni .NET Core multipiattaforma. Sono supportate le lingue aggiuntive oltre a c#, ad esempio JavaScript, F # e Java. Creati nel portale di funzioni forniscono una sintassi di scripting avanzata. Funzioni create come progetti autonomi possono essere distribuite con le funzionalità e supporto della piattaforma completa.

Per altre informazioni, vedere [documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions).

## <a name="functions-v1-vs-v2"></a>Funzioni v1 e v2

Sono disponibili due versioni del runtime di funzioni di Azure: 1.x e 2.x. Versione 1.x è disponibile a livello generale (GA). Supporta lo sviluppo .NET dal portale o le macchine Windows e Usa .NET Framework. 1.x supporta c#, JavaScript e F #, con il supporto sperimentale per Python, PHP, TypeScript, Batch, Bash e PowerShell.

Versione 2.x è disponibile in anteprima. Si usa .NET Core che supporta lo sviluppo multipiattaforma in Windows, macOS e Linux macchine. Aggiunge un eccellente supporto per Java 2.x, ma non ancora direttamente supporta uno dei linguaggi sperimentali. Versione 2.x Usa un nuovo modello di estendibilità di associazione che abilitano estensioni di terze parti per la piattaforma, controllo delle versioni indipendente delle associazioni, e una più semplice l'ambiente di esecuzione.

> **Si verifica un problema noto nella versione 1.x con [supporto di reindirizzamento dell'associazione](https://github.com/Azure/azure-functions-host/issues/992).** Il problema è specifico per lo sviluppo .NET. I progetti con dipendenze da librerie che hanno una versione diversa dalle librerie incluse in fase di esecuzione sono interessati. Il team di funzioni ha eseguito il commit sta facendo progressi concreto sul problema. Il team di risolvere i reindirizzamenti di associazione nella versione 2.x prima dell'aggiunta alla disponibilità generale. L'istruzione ufficiale del team con le correzioni consigliate e le soluzioni alternative è disponibile qui: [risoluzione dell'Assembly in funzioni di Azure](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

Per altre informazioni, vedere [confrontare 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).

## <a name="programming-language-support"></a>Supporto di linguaggi di programmazione

Sono supportate le lingue seguenti sia in generale (GA), la disponibilità in anteprima, o sperimentale.

|Linguaggio      |1.x         |versione 2.x      |
|--------------|------------|---------|
|**C#**        |DISPONIBILE A LIVELLO GENERALE          |Anteprima  |
|**JavaScript**|DISPONIBILE A LIVELLO GENERALE          |Anteprima  |
|**F#**        |DISPONIBILE A LIVELLO GENERALE          |         |
|**Java**      |            |Anteprima  |
|**Python**    |Sperimentale|         |
|**PHP**       |Sperimentale|         |
|**TypeScript**|Sperimentale|         |
|**Batch**     |Sperimentale|         |
|**Bash**      |Sperimentale|         |
|**PowerShell**|Sperimentale|         |

Per altre informazioni, vedere [lingue supportate](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Piani di servizio App

Le funzioni sono supportate da un *piano di servizio app*. Il piano definisce le risorse usate dall'app per le funzioni. È possibile assegnare i piani a un'area, determinare le dimensioni e numero di macchine virtuali che verranno usate e selezionare un piano tariffario. Per un approccio senza server true, è possibile usare l'App per le funzioni di **consumo** piano. Il piano a consumo verrà ridimensionato automaticamente in base al caricamento del back-end.

Per altre informazioni, vedere [piani di servizio App](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).

## <a name="create-your-first-function"></a>Creare la prima funzione

Esistono tre modi comuni per creare App per le funzioni.

* Funzioni di script nel portale.
* Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure (CLI).
* Creare funzioni in locale usando l'IDE preferito e pubblicarli in Azure.

Per altre informazioni sulla creazione di una funzione con script nel portale, vedere [creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).

Per la compilazione della riga di comando di Azure, vedere [creare la prima funzione usando il comando di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).

Per creare una funzione da Visual Studio, vedere [creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).

## <a name="understand-triggers-and-bindings"></a>Comprendere i trigger e associazioni

Le funzioni vengono richiamate da un *trigger* e può avere uno e uno solo. Oltre a richiamare la funzione, determinate trigger fungere anche da associazioni. È anche possibile definire più associazioni oltre il trigger. *Associazioni* forniscono una modalità dichiarativa per la connessione dati al codice. Essi possono essere passati in (input) o la ricezione dei dati (output). Trigger e associazioni apportare facile da usare con le funzioni. Associazioni di rimuovere l'overhead di creazione manuale di database o un file le connessioni di sistema. Tutte le informazioni necessarie per le associazioni sono contenute in una speciale *Functions* file per gli script o dichiarati con gli attributi nel codice.

Alcuni trigger comuni includono:

* Archivio BLOB: richiamare la funzione quando viene caricato o modificato in archiviazione di un file o cartella.
* HTTP: richiamare la funzione, ad esempio un'API REST.
* Coda: richiamare la funzione quando sono presenti gli elementi in una coda.
* Timer: richiamare la funzione cadenza regolare.

Esempi di associazioni:

* COSMOS DB: connettersi facilmente al database per caricare o salvare i file.
* Archiviazione tabelle: funzionano con archivio chiave/valore da app per le funzioni.
* Archiviazione di Accodamento: facilmente recuperare gli elementi da una coda o inserire nuovi elementi nella coda.

Nell'esempio seguente *Functions* file definisce un trigger e un'associazione:

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

In questo esempio, la funzione viene attivata da una modifica all'archiviazione blob nel `images` contenitore. Le informazioni per il file viene passate, in modo che il trigger funge anche da un'associazione. Esiste un'altra associazione per inserire le informazioni in una coda denominata `images`.

Ecco lo script c# per la funzione:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

L'esempio è una funzione semplice che accetta il nome del file che è stata modificata o caricati nell'archiviazione blob e li inserisce in una coda per l'elaborazione successiva.

Per un elenco completo di trigger e associazioni, vedere [funzioni di Azure concetti di trigger e associazioni](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

## <a name="proxies"></a>Proxy

I proxy forniscono funzionalità di reindirizzamento per l'applicazione. I proxy espongono un endpoint ed eseguire il mapping che l'endpoint a un'altra risorsa. Con i proxy, è possibile:

* Reindirizza una richiesta in ingresso a un altro endpoint.
* Modificare la richiesta in ingresso prima che vengano passati insieme.
* Modificare o fornire una risposta.

I proxy vengono usati per scenari, ad esempio:

* Semplificazione, riduzione o la modifica dell'URL.
* Fornire un prefisso API coerente a più servizi back-end.
* Il comportamento fittizio una risposta a un endpoint in fase di sviluppo.
* Fornire una risposta statica a un endpoint noto.
* Mentre il back-end è stato spostato o eseguire la migrazione, mantenendo coerenti con l'endpoint API.

I proxy vengono archiviati come le definizioni JSON. Ecco un esempio:

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

Il `Domain Redirect` proxy accetta una route abbreviata e ne esegue il mapping alla risorsa di funzione più lungo. La trasformazione è simile a:

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

Il `Root` proxy accetta qualsiasi elemento inviato all'URL radice (`https://--shorturl--/`) e lo reindirizza al sito della documentazione.

Nel video viene illustrato un esempio di utilizzo dei proxy [Azure: porta la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/events/Connect/2017/E102). In tempo reale, viene eseguita la migrazione di un'applicazione ASP.NET Core in esecuzione sul Server SQL locale al Cloud di Azure. Proxy vengono usati per effettuare il refactoring di un progetto API Web tradizionale per usare le funzioni.

Per altre informazioni sui proxy, vedere [lavorare con il proxy di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies).

>[!div class="step-by-step"]
[Precedente](azure-serverless-platform.md)
[Successivo](application-insights.md)