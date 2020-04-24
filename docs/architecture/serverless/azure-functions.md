---
title: Funzioni di Azure-app senza server
description: Funzioni di Azure offre funzionalità senza server tra più linguaggi (C#, JavaScript, Java) e piattaforme per fornire codice di scalabilità immediata basato sugli eventi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 2dee60e3635be94a55ee26a7f04942bc59cb8dec
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135724"
---
# <a name="azure-functions"></a>Funzioni di Azure

Funzioni di Azure offre un'esperienza di calcolo senza server. Una funzione viene richiamata da un *trigger* , ad esempio l'accesso a un endpoint HTTP o un timer, ed esegue un blocco di codice o logica di business. Le funzioni supportano inoltre *associazioni* specializzate che si connettono a risorse come l'archiviazione e le code.

![Logo di funzioni di Azure](./media/azure-functions-logo.png)

La versione corrente del runtime 3,0 supporta le applicazioni .NET Core 3,1 multipiattaforma. Sono supportate altre lingue oltre a C#, ad esempio JavaScript, F # e Java. Le funzioni create nel portale forniscono una sintassi di scripting avanzata. Le funzioni create come progetti autonomi possono essere distribuite con funzionalità e supporto completo per la piattaforma.

Per altre informazioni, vedere la [documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions).

## <a name="programming-language-support"></a>Supporto del linguaggio di programmazione

Le lingue seguenti sono tutte supportate in disponibilità generale (GA).

|Linguaggio      |Runtime supportati|
|--------------|------------------|
|**C#**        |.NET Core 3,1     |
|**JavaScript**|Nodo 10 & 12      |
|**F#**        |.NET Core 3,1     |
|**Java**      |Java 8            |
|**Python**    |Python 3,6, 3,7, & 3,8|
|**TypeScript**|Nodo 10 & 12 (tramite JavaScript)|
|**PowerShell**|PowerShell Core 6|

Per altre informazioni, vedere [Linguaggi supportati](https://docs.microsoft.com/azure/azure-functions/supported-languages).

## <a name="app-service-plans"></a>Piani di servizio app

Le funzioni sono supportate da un *piano di servizio app*. Il piano definisce le risorse usate dall'app per le funzioni. È possibile assegnare piani a un'area, determinare le dimensioni e il numero di macchine virtuali che verranno usate e scegliere un piano tariffario. Per un vero approccio senza server, le app per le funzioni possono usare il piano a **consumo** . Il piano a consumo eseguirà il ridimensionamento automatico del back-end in base al carico.

Un'altra opzione di hosting per le app per le funzioni è il [piano Premium](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan). Questo piano fornisce un'istanza "always on" per evitare l'avvio a freddo, supporta funzionalità avanzate, come la connettività VNet, e viene eseguito su hardware Premium.

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

In questo esempio, la funzione viene attivata da una modifica all'archiviazione BLOB nel `images` contenitore. Le informazioni per il file vengono passate, quindi il trigger funge anche da Binding. Esiste un'altra associazione per inserire le informazioni in una `images`coda denominata.

Di seguito è riportato lo script C# per la funzione:

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

L'esempio è una funzione semplice che accetta il nome del file che è stato modificato o caricato nell'archivio BLOB e lo inserisce in una coda per l'elaborazione successiva.

Per un elenco completo dei trigger e delle associazioni, vedere [concetti relativi a trigger e associazioni di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

>[!div class="step-by-step"]
>[Precedente](azure-serverless-platform.md)
>[successivo](application-insights.md)
