---
title: Introduzione all'archiviazione tabelle di Azure con F#
description: Archivia i dati strutturati nel cloud usando l'archiviazione tabelle di Azure o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 6833e2264f7543f50b94892b6980140e4bf1cdd1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424603"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Introduzione all'archiviazione tabelle di Azure e Azure Cosmos DB API Tabella con F\#

Archiviazione tabelle di Azure è un servizio che archivia dati NoSQL strutturati nel cloud. L'archiviazione tabelle è un archivio di chiavi/attributi con una progettazione senza schema. Poiché l'archiviazione tabelle è con schema, è facile adattare i dati in base all'evoluzione delle esigenze dell'applicazione. L'accesso ai dati è veloce ed economicamente conveniente per tutti i tipi di applicazioni. Il costo dell'archiviazione tabelle è in genere significativamente inferiore rispetto a SQL tradizionale per volumi di dati simili.

È possibile usare l'archiviazione tabelle per archiviare set di dati flessibili, ad esempio dati utente per le applicazioni Web, rubriche, informazioni sui dispositivi e altri tipi di metadati richiesti dal servizio. È possibile archiviare un numero qualsiasi di entità in una tabella e un account di archiviazione può contenere un numero qualsiasi di tabelle, fino al limite di capacità dell'account di archiviazione.

Azure Cosmos DB fornisce le API Tabella per le applicazioni scritte per l'archiviazione tabelle di Azure e che richiedono funzionalità Premium, ad esempio:

- Distribuzione globale chiavi in mano.
- Velocità effettiva dedicata in tutto il mondo.
- Latenze di millisecondi a una sola cifra al 99 ° percentile.
- Disponibilità elevata garantita.
- Indicizzazione secondaria automatica.

Le applicazioni scritte per l'archiviazione tabelle di Azure possono eseguire la migrazione a Azure Cosmos DB usando il API Tabella senza modifiche al codice e sfruttare le funzionalità Premium. Il API Tabella include SDK client disponibili per .NET, Java, Python e node. js.

Per ulteriori informazioni, vedere [Introduzione a Azure Cosmos DB API tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Informazioni su questa esercitazione

Questa esercitazione illustra come scrivere F# codice per eseguire alcune attività comuni usando l'archiviazione tabelle di Azure o il Azure Cosmos DB API tabella, tra cui la creazione e l'eliminazione di una tabella e l'inserimento, l'aggiornamento, l'eliminazione e l'esecuzione di query sui dati della tabella.

## <a name="prerequisites"></a>Prerequisites

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure o un](/azure/storage/storage-create-storage-account) [account Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `tables.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`. Ripetere l'operazione per `Microsoft.WindowsAzure.ConfigurationManager` per ottenere lo spazio dei nomi Microsoft. Azure.

### <a name="add-namespace-declarations"></a>Aggiungi dichiarazioni dello spazio dei nomi

Aggiungere le seguenti istruzioni `open` all'inizio del file `tables.fsx`:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Ottenere la stringa di connessione di archiviazione di Azure

Se ci si connette al servizio tabelle di archiviazione di Azure, per questa esercitazione è necessaria la stringa di connessione. È possibile copiare la stringa di connessione dal portale di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

### <a name="get-your-azure-cosmos-db-connection-string"></a>Ottenere la stringa di connessione Azure Cosmos DB

Se ci si connette a Azure Cosmos DB, per questa esercitazione è necessaria la stringa di connessione. È possibile copiare la stringa di connessione dal portale di Azure. Nel portale di Azure, nell'account Cosmos DB, passare a **impostazioni** >  stringa di**connessione**e fare clic sul pulsante **copia** per copiare la stringa di connessione primaria.

Per l'esercitazione, immettere la stringa di connessione nello script, come nell'esempio seguente:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Questa operazione non è tuttavia **consigliata** per i progetti reali. La chiave dell'account di archiviazione è simile alla password radice dell'account di archiviazione. Prestare sempre attenzione a proteggere la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

L'uso di Configuration Manager di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Viene restituito un `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Creare il client del servizio tabelle

La classe `CloudTableClient` consente di recuperare tabelle ed entità nell'archivio tabelle. Ecco un modo per creare il client del servizio:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

A questo punto si è pronti per scrivere codice che legge e scrive i dati nell'archivio tabelle.

### <a name="create-a-table"></a>Creare una tabella

Questo esempio illustra come creare una tabella se non esiste già:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Aggiungere un'entità a una tabella

Un'entità deve avere un tipo che eredita da `TableEntity`. Puoi estendere `TableEntity` nel modo che preferisci, ma il tipo *deve* avere un costruttore senza parametri. Nella tabella di Azure vengono archiviate solo le proprietà con `get` e `set`.

La chiave di partizione e di riga di un'entità identifica in modo univoco l'entità nella tabella. È possibile eseguire query più velocemente sulle entità con la stessa chiave di partizione rispetto a quelle con chiavi di partizione diverse, ma l'uso di chiavi di partizione diverse consente una maggiore scalabilità delle operazioni parallele.

Di seguito è riportato un esempio di `Customer` che usa il `lastName` come chiave di partizione e il `firstName` come chiave di riga.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Aggiungere ora `Customer` alla tabella. A tale scopo, creare un `TableOperation` che viene eseguito nella tabella. In questo caso, si crea un'operazione `Insert`.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Inserire un batch di entità

È possibile inserire un batch di entità in una tabella utilizzando una singola operazione di scrittura. Le operazioni batch consentono di combinare le operazioni in una singola esecuzione, ma presentano alcune restrizioni:

- È possibile eseguire aggiornamenti, eliminazioni e inserimenti nella stessa operazione batch.
- Un'operazione batch può includere fino a 100 entità.
- Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.
- Sebbene sia possibile eseguire una query in un'operazione batch, è necessario che sia l'unica operazione nel batch.

Ecco il codice che combina due inserimenti in un'operazione batch:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Recuperare tutte le entità in una partizione

Per eseguire una query su una tabella per tutte le entità in una partizione, usare un oggetto `TableQuery`. Qui viene filtrato per le entità in cui "Smith" è la chiave di partizione.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Recuperare un intervallo di entità in una partizione

Se non si desidera eseguire una query su tutte le entità di una partizione, è possibile specificare un intervallo combinando il filtro della chiave di partizione con un filtro della chiave di riga. In questo caso, si usano due filtri per recuperare tutte le entità nella partizione "Smith", dove la chiave di riga (nome) inizia con una lettera precedente a "M" nell'alfabeto.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Recuperare una singola entità

È possibile scrivere una query per recuperare una singola entità specifica. Qui viene usato un `TableOperation` per specificare il cliente "Ben Smith". Anziché una raccolta, viene restituito un `Customer`. La definizione della chiave di partizione e della chiave di riga in una query rappresenta il modo più rapido per recuperare una singola entità dal servizio tabelle.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

È ora possibile stampare i risultati:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>Sostituire un'entità

Per aggiornare un'entità, recuperarla dal servizio tabelle, modificare l'oggetto entità, quindi salvare di nuovo le modifiche nel servizio tabelle utilizzando un'operazione `Replace`. In questo modo l'entità viene completamente sostituita nel server, a meno che l'entità nel server non sia cambiata dopo che è stata recuperata, nel qual caso l'operazione non riesce. Questo errore impedisce all'applicazione di sovrascrivere inavvertitamente le modifiche da altre origini.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Inserire o sostituire un'entità

In alcuni casi non è possibile sapere se un'entità è presente nella tabella. In caso contrario, i valori correnti archiviati non sono più necessari. È possibile utilizzare `InsertOrReplace` per creare l'entità o sostituirla se esistente, indipendentemente dal relativo stato.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Eseguire una query su un subset di proprietà dell'entità

Una query di tabella può recuperare solo alcune proprietà da un'entità anziché tutte. Questa tecnica, denominata proiezione, può migliorare le prestazioni delle query, in particolare per entità di grandi dimensioni. In questo caso, vengono restituiti solo gli indirizzi di posta elettronica utilizzando `DynamicTableEntity` e `EntityResolver`. Si noti che la proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo quando si usa un account nel servizio tabelle.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Recuperare entità in pagine in modo asincrono

Se si sta leggendo un numero elevato di entità e si vuole elaborarle quando vengono recuperate, anziché attendere che vengano restituite tutte, è possibile usare una query segmentata. In questo caso, si restituiscono i risultati nelle pagine usando un flusso di lavoro asincrono, in modo che l'esecuzione non venga bloccata durante l'attesa della restituzione di un set di risultati di grandi dimensioni.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

È ora possibile eseguire questo calcolo in modo sincrono:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Eliminare un'entità

È possibile eliminare un'entità dopo averla recuperata. Come per l'aggiornamento di un'entità, questa operazione ha esito negativo se l'entità è cambiata dopo che è stata recuperata.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Eliminare una tabella

È possibile eliminare una tabella da un account di archiviazione. Una tabella eliminata non sarà disponibile per essere ricreata per un certo periodo di tempo dopo l'eliminazione.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Passaggi successivi

Ora che sono state apprese le nozioni di base dell'archiviazione tabelle, seguire i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse e la Azure Cosmos DB API Tabella.

- [Introduzione a Azure Cosmos DB API Tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Informazioni di riferimento sulla libreria client di archiviazione per .NET](https://docs.microsoft.com/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Blog del team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurazione delle stringhe di connessione](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
