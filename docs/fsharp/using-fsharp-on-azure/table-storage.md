---
title: 'Introduzione all''archiviazione tabelle di Azure con F #'
description: Archiviare dati strutturati nel cloud tramite l'archiviazione tabelle di Azure, un archivio dati NoSQL.
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: e003f537c6f0f85b3b0ba932655ae2a54c980bc5
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2018
---
# <a name="get-started-with-azure-table-storage-using-f"></a>Introduzione all'archiviazione tabelle di Azure con F # #

Archiviazione tabelle di Azure è un servizio che archivia dati NoSQL strutturati nel cloud. Archiviazione tabelle è un archivio o l'attributo chiave con una progettazione schemaless. Poiché l'archiviazione tabelle è schemaless, è facile adattare i dati come le esigenze di evolve l'applicazione. Accesso ai dati è veloce e conveniente per tutti i tipi di applicazioni. Archiviazione tabelle è in genere notevolmente inferiore costo SQL tradizionale per i volumi di dati simili.

È possibile utilizzare l'archiviazione tabelle per archiviare i set di dati flessibile, ad esempio i dati utente per applicazioni web, rubriche, informazioni sul dispositivo e qualsiasi altro tipo di metadati che richiede il servizio. È possibile archiviare qualsiasi numero di entità in una tabella e un account di archiviazione può contenere qualsiasi numero di tabelle, fino al limite di capacità dell'account di archiviazione.

### <a name="about-this-tutorial"></a>Su questa esercitazione

In questa esercitazione viene illustrato come scrivere codice F # per eseguire alcune attività comuni utilizzando l'archiviazione tabelle di Azure, inclusa la creazione e l'eliminazione di una tabella e inserimento, aggiornamento, eliminazione e query sui dati di tabella.

Per una panoramica concettuale dell'archiviazione tabelle, vedere [la Guida di .NET per l'archiviazione tabelle](/azure/storage/storage-dotnet-how-to-use-tables)

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Per questo account, è necessario anche la chiave di accesso di archiviazione.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un Script F # e avvio di F # Interactive

Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #. Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `tables.fsx`, nell'ambiente di sviluppo F #.

Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`direttiva. Eseguire nuovamente per 'Microsoft.WindowsAzure.ConfigurationManager' per ottenere lo spazio dei nomi Microsoft.Azure.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il seguente `open` istruzioni all'inizio di `tables.fsx` file:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Si tratta tuttavia **non è consigliabile** di progetti. La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave di account di archiviazione. Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Utilizzando Gestione configurazione di Azure è facoltativa. È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, utilizzare:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Creare il client del servizio tabelle

La `CloudTableClient` classe consente di recuperare tabelle ed entità archiviate nell'archiviazione tabelle. Ecco un modo per creare il client del servizio:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati in archiviazione tabelle.

## <a name="create-a-table"></a>Creare una tabella

In questo esempio viene illustrato come creare una tabella se non esiste già:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a>Aggiungere un'entità a una tabella

Un'entità deve disporre di un tipo che eredita da `TableEntity`. È possibile estendere `TableEntity` nel modo desiderato, ma il tipo di *deve* dispone di un costruttore senza parametri. Solo le proprietà che hanno entrambi `get` e `set` verranno archiviati nella tabella di Azure.

Chiave di riga e di partizione dell'entità è necessario identificare in modo univoco l'entità nella tabella. Le entità con la stessa chiave di partizione è possibile eseguire query più velocemente rispetto a quelle con le chiavi di partizione diverso, ma con le chiavi di partizione diverse consente una maggiore scalabilità di operazioni parallele.

Di seguito è riportato un esempio di un `Customer` che utilizza il `lastName` come chiave di partizione e `firstName` come chiave di riga.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Ora verrà aggiunto il nostro `Customer` alla tabella. A tale scopo, si crea un `TableOperation` che verrà eseguita sulla tabella. In questo caso, si crea un `Insert` operazione.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a>Inserire un batch di entità

È possibile inserire un batch di entità in una tabella utilizzando una sola operazione di scrittura. Operazioni batch consentono di combinare operazioni in una singola esecuzione, ma presentano alcune restrizioni:

- È possibile eseguire aggiornamenti, Elimina e lo inserisce nella stessa operazione batch.
- Un'operazione batch può includere fino a 100 entità.
- Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.
- Sebbene sia possibile eseguire una query in un'operazione batch, deve essere l'unica operazione nel batch.

Ecco alcuni codice che combina due istruzioni INSERT in un'operazione batch:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a>Recuperare tutte le entità in una partizione

Per una query sulla tabella per tutte le entità in una partizione, utilizzare un `TableQuery` oggetto. In questo caso, è applicare un filtro per le entità in cui "Buster" è la chiave di partizione.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a>Recuperare un intervallo di entità in una partizione

Se non si desidera eseguire una query di tutte le entità in una partizione, è possibile specificare un intervallo combinando il filtro di chiave di partizione con un filtro di riga di chiave. In questo caso, utilizzare due filtri per ottenere tutte le entità nella partizione "Buster" in cui la chiave di riga (nome) inizia con una lettera precedente a "M" nell'alfabeto.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a>Recuperare una singola entità

È possibile scrivere una query per recuperare un'entità singola e specifica. In questo caso, si utilizza un `TableOperation` per specificare il cliente "Larry Buster". Invece di una raccolta, verrà restituito un `Customer`. Specifica la chiave di partizione sia la chiave di riga in una query è il modo più rapido per recuperare una singola entità dal servizio tabelle.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a>Sostituire un'entità

Per aggiornare un'entità, recuperarlo dal servizio tabelle, modificare l'oggetto entità e quindi salvare le modifiche al servizio tabella utilizzando un `Replace` operazione. In questo modo l'entità da sostituire completamente nel server, a meno che l'entità nel server è stato modificato dopo che è stata recuperata, nel qual caso l'operazione avrà esito negativo. Questo errore consiste nell'impedire all'applicazione inavvertitamente sovrascrivendo le modifiche apportate da altre origini.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a>Inserire o sostituire un'entità

In alcuni casi, è possibile capire se l'entità esiste nella tabella o non. E in tal caso, i valori correnti archiviati in essa contenuti non sono più necessari. È possibile utilizzare `InsertOrReplace` per creare l'entità o sostituirlo se esiste, indipendentemente dal suo stato.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a>Query a un subset di proprietà dell'entità

Una query di tabella è possibile recuperare solo alcune proprietà di un'entità anziché tutti gli elementi. Questa tecnica, denominata proiezione, è possibile migliorare le prestazioni delle query, in particolare per le entità di grandi dimensioni. In questo caso, si restituiscono gli indirizzi e-mail solo `DynamicTableEntity` e `EntityResolver`. Si noti che proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo quando si utilizza un account del servizio di tabella.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a>Recuperare le entità in pagine in modo asincrono

Se si legge un numero elevato di entità e si desidera elaborarle quando vengono recuperate anziché attenderne tutte restituito, è possibile utilizzare una query segmentata. In questo caso, per restituire risultati nelle pagine utilizzando un flusso di lavoro asincroni in modo che non l'esecuzione viene bloccata durante l'attesa per un ampio set di risultati da restituire.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

È ora eseguire il calcolo in modo sincrono:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a>Eliminare un'entità

Dopo avere recuperato, è possibile eliminare un'entità. Come con l'aggiornamento di un'entità, l'operazione non riuscirà se l'entità è stata modificata dopo che è stato recuperato.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a>Eliminare una tabella

È possibile eliminare una tabella da un account di archiviazione. Una tabella in cui è stata eliminata non sarà disponibile per essere ricreati per un periodo di tempo in seguito all'eliminazione.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a>Passaggi successivi

Ora che si è appreso le nozioni di base dell'archiviazione tabelle, vedere i collegamenti seguenti per informazioni sulle attività più complesse di archiviazione:

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [Blog del Team di archiviazione di Azure](http://blogs.msdn.com/b/windowsazurestorage/)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Introduzione all'archiviazione tabelle di Azure in .NET](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
