---
title: Iniziare a usare archiviazione tabelle di AzureF#
description: Store dati strutturati nel cloud con archiviazione tabelle di Azure o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 2b74a33023065ea809c2d7eb6202b1a254018422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966008"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Introduzione all'archiviazione tabelle di Azure e l'API Table di Azure Cosmos DB con F\#

Archiviazione tabelle di Azure è un servizio che archivia dati NoSQL strutturati nel cloud. Archiviazione tabelle è un archivio di chiavi/attributi con una struttura senza schema. Poiché l'archiviazione tabelle è senza schema, è facile adattare i dati come le esigenze priva di. Accesso ai dati è rapido ed economico per tutti i tipi di applicazioni. Archiviazione tabelle è in genere costo notevolmente inferiore rispetto alle soluzioni SQL tradizionali per volumi simili di dati.

È possibile usare l'archiviazione tabelle per archiviare set di dati flessibili, ad esempio i dati utente per le applicazioni web, rubriche, informazioni sul dispositivo e qualsiasi altro tipo di metadati richiesti dal servizio. È possibile archiviare qualsiasi numero di entità in una tabella e un account di archiviazione può contenere un numero qualsiasi di tabelle, fino al limite di capacità dell'account di archiviazione.

Azure Cosmos DB offre l'API di tabella per le applicazioni scritte per l'archiviazione tabelle di Azure e che richiedono funzionalità premium, ad esempio:

- Distribuzione globale chiavi in mano.
- Velocità effettiva dedicata in tutto il mondo.
- Latenze di millisecondi in pochissimi millisecondi al 99 ° percentile.
- Disponibilità elevata garantita.
- Indicizzazione secondaria automatica.

Le applicazioni scritte per l'archiviazione tabelle di Azure possono eseguire la migrazione ad Azure Cosmos DB usando l'API di tabella senza modifiche al codice e sfruttare i vantaggi delle funzionalità premium. L'API tabelle include SDK client per .NET, Java, Python e Node. js.

Per altre informazioni, vedere [Introduzione all'API tabelle di Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Informazioni su questa esercitazione

Questa esercitazione illustra come scrivere F# codice per eseguire alcune attività comuni usando l'API Azure Cosmos DB nella tabella, incluse la creazione e l'eliminazione di una tabella e inserimento, l'aggiornamento, eliminazione e query sui dati di tabella o archiviazione tabelle di Azure.

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account) oppure [account Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).


## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un F# creare uno Script e avviare F# interattivo

Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script. Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `tables.fsx`, nella F# ambiente di sviluppo.

Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva. Eseguire quindi un nuovo `Microsoft.WindowsAzure.ConfigurationManager` per ottenere lo spazio dei nomi Microsoft.Azure.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il codice seguente `open` istruzioni all'inizio del `tables.fsx` file:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Ottenere la stringa di connessione di archiviazione di Azure

Se ci si connette al servizio di archiviazione tabelle di Azure, la stringa di connessione è necessario per questa esercitazione. È possibile copiare la stringa di connessione dal portale di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

### <a name="get-your-azure-cosmos-db-connection-string"></a>Ottenere la stringa di connessione di Azure Cosmos DB

Se ci si connette ad Azure Cosmos DB, la stringa di connessione è necessario per questa esercitazione. È possibile copiare la stringa di connessione dal portale di Azure. Nel portale di Azure nell'account Cosmos DB, passare a **le impostazioni** > **stringa di connessione**, fare clic sui **copia** per copiare la connessione primaria Stringa. 

Per l'esercitazione, immettere la stringa di connessione nello script, come nell'esempio seguente:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Si tratta tuttavia **sconsigliato** progetti per il real. La chiave dell'account è simile alla password radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave dell'account. Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Usando Gestione configurazione di Azure è facoltativa. È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Restituisce un `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Creare il client del servizio tabelle

Il `CloudTableClient` classe consente di recuperare le tabelle e le entità nell'archiviazione tabelle. Ecco un modo per creare il client del servizio:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione tabelle.

### <a name="create-a-table"></a>Creare una tabella

In questo esempio viene illustrato come creare una tabella se non esiste già:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Aggiungere un'entità a una tabella

È necessario che un tipo che eredita da un'entità `TableEntity`. È possibile estendere `TableEntity` nel modo desiderato, ma il tipo *necessario* dispone di un costruttore senza parametri. Solo le proprietà che hanno entrambe `get` e `set` vengono archiviati nella tabella di Azure.

Partizione di un'entità e la chiave di riga identificare in modo univoco l'entità nella tabella. Le entità con la stessa chiave di partizione è possibile eseguire query più velocemente rispetto a quelle con chiavi di partizione diverse, tuttavia usando chiavi di partizione diverse assicura maggiore scalabilità delle operazioni parallele.

Di seguito è riportato un esempio di un `Customer` che usa la `lastName` come chiave di partizione e il `firstName` come chiave di riga.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

A questo punto aggiungere `Customer` alla tabella. A tale scopo, creare un `TableOperation` che viene eseguita sulla tabella. In questo caso, si crea un `Insert` operazione.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Inserire un batch di entità

È possibile inserire un batch di entità in una tabella utilizzando una sola operazione di scrittura. Operazioni batch consentono di combinare le operazioni in un'unica esecuzione, ma presentano alcune restrizioni:

- È possibile eseguire gli aggiornamenti, eliminazione e inserimento nella stessa operazione batch.
- Un'operazione batch può includere fino a 100 entità.
- Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.
- Sebbene sia possibile eseguire una query in un'operazione batch, deve essere l'unica operazione nel batch.

Ecco un codice che combina due istruzioni INSERT in un'operazione batch:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Recuperare tutte le entità in una partizione

Per eseguire query su una tabella per tutte le entità in una partizione, usare un `TableQuery` oggetto. In questo caso, Filtra per le entità in cui la chiave di partizione "Smith".

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Recuperare un intervallo di entità in una partizione

Se non si desidera eseguire una query di tutte le entità in una partizione, è possibile specificare un intervallo combinando il filtro della chiave di partizione con un filtro della chiave di riga. In questo caso, si usano due filtri per ottenere tutte le entità nella partizione "Smith" in cui la chiave di riga (nome) inizia con una lettera precedente a "M" nell'alfabeto.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Recuperare una singola entità

È possibile scrivere una query per recuperare una singola entità specifica. In questo caso, si utilizza un `TableOperation` per specificare il cliente "Ben Smith". Invece di una raccolta, si ottiene un `Customer`. Specifica la chiave di partizione sia la chiave di riga in una query è il modo più rapido per recuperare una singola entità dal servizio tabelle.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Ora possibile stampare i risultati:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a>Sostituire un'entità

Per aggiornare un'entità, recuperarla dal servizio tabelle, modificare l'oggetto entità e quindi salvare le modifiche nuovamente al servizio tabella tramite un `Replace` operazione. In questo modo l'entità viene completamente sostituita nel server, a meno che l'entità nel server è stato modificato dopo essere stata recuperata, nel qual caso l'operazione ha esito negativo. Questo errore è impedire all'applicazione di sovrascrivere inavvertitamente le modifiche apportate da altre origini.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Inserire o sostituire un'entità

In alcuni casi, è possibile capire se esiste un'entità nella tabella. E in caso affermativo, i valori correnti in essa archiviati non sono più necessari. È possibile usare `InsertOrReplace` per creare l'entità o sostituirlo se esiste, indipendentemente dallo stato.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Eseguire query su un subset delle proprietà dell'entità

Una query di tabella può recuperare solo alcune proprietà da un'entità invece di tutti gli elementi. Questa tecnica, denominata proiezione, è possibile migliorare le prestazioni delle query, in particolare per entità di grandi dimensioni. In questo caso, si restituiscono indirizzi di posta elettronica solo usando `DynamicTableEntity` e `EntityResolver`. Si noti che proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo quando si usa un account sul servizio tabelle.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Recuperare entità nelle pagine in modo asincrono

Se si esegue la lettura di un numero elevato di entità e si desidera elaborarle quando vengono recuperate anziché attendere vengano tutte restituite, è possibile usare una query segmentata. In questo caso, per restituire i risultati nelle pagine utilizzando un flusso di lavoro asincroni in modo che l'esecuzione non venga bloccata durante l'attesa per un ampio set di risultati da restituire.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

È ora necessario eseguire il calcolo in modo sincrono:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Eliminare un'entità

È possibile eliminare un'entità dopo averla recuperata. Come con l'aggiornamento di un'entità, l'operazione non riesce se l'entità è stato modificato dopo che è stato recuperato.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Eliminare una tabella

È possibile eliminare una tabella da un account di archiviazione. Una tabella in cui è stata eliminata non sarà disponibile per essere creata nuovamente per un periodo di tempo dopo l'eliminazione.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Passaggi successivi

A questo punto, dopo aver appreso le nozioni di base dell'archiviazione tabelle, visitare i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse e l'API Table di Azure Cosmos DB.

- [Introduzione ad Azure Cosmos DB API di tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Storage Client Library per .NET](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [Provider di tipi di archiviazione di Azure](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Blog del Team di archiviazione di Azure](https://blogs.msdn.com/b/windowsazurestorage/)
- [Configurazione delle stringhe di connessione](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [Introduzione all'archiviazione tabelle di Azure in .NET](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
