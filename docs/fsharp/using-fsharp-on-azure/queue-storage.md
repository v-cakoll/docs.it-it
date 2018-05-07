---
title: "Introduzione all'archiviazione di Accodamento di Azure con F #"
description: Le code di Azure offrono una messaggistica affidabile e asincrono tra i componenti dell'applicazione. Cloud della messaggistica consentono di aumentare in modo indipendente i componenti dell'applicazione.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 14bbc657f965fc262d2a83b1fdf982fe5e75d55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introduzione all'archiviazione di Accodamento di Azure con F # #

Archiviazione delle code di Azure fornisce cloud scambio di messaggi tra i componenti dell'applicazione. Nella progettazione di applicazioni per la scala, i componenti delle applicazioni sono spesso separati, in modo che sia possibile adattarli in modo indipendente. L'archiviazione delle code recapita la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, se sono in esecuzione nel cloud, sul desktop, su un server locale o in un dispositivo mobile. L'archiviazione delle code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro di processo.

### <a name="about-this-tutorial"></a>Su questa esercitazione

In questa esercitazione viene illustrato come scrivere codice F # per alcune attività comuni tramite l'archiviazione delle code di Azure. Argomenti trattati includono la creazione e l'eliminazione di code e aggiunta, lettura e l'eliminazione di messaggi in coda.

Per una panoramica concettuale di archiviazione delle code, vedere [la Guida di .NET per l'archiviazione delle code](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Per questo account, è necessario anche la chiave di accesso di archiviazione.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un Script F # e avvio di F # Interactive

Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #. Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `queues.fsx`, nell'ambiente di sviluppo F #.

Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il seguente `open` istruzioni all'inizio di `queues.fsx` file:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Si tratta tuttavia **non è consigliabile** di progetti. La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave di account di archiviazione. Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Utilizzando Gestione configurazione di Azure è facoltativa. È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, utilizzare:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Creare il client del servizio coda

La `CloudQueueClient` classe consente di recuperare le code archiviate in archiviazione di Accodamento. Ecco un modo per creare il client del servizio:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati per l'archiviazione delle code.

## <a name="create-a-queue"></a>Creare una coda

In questo esempio viene illustrato come creare una coda, se non esiste già:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Inserire un messaggio in una coda

Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`. Chiamare quindi il `AddMessage` metodo. Oggetto `CloudQueueMessage` può essere creato da una stringa (in formato UTF-8) o un `byte` matrice, simile al seguente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Visualizza il messaggio successivo

È possibile anche visualizzare il messaggio all'inizio di una coda senza rimuoverlo dalla coda, chiamando la `PeekMessage` metodo.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Ottenere il messaggio successivo per l'elaborazione

È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il `GetMessage` metodo.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

In un secondo momento indicare l'elaborazione corretta del messaggio utilizzando `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Modificare il contenuto di un messaggio in coda

È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda. Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornare lo stato dell'attività di lavoro. Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per estendere un altro 60 secondi. Questo consente di salvare lo stato del lavoro associata al messaggio e fornisce al client un altro minuto per continuare a utilizzare il messaggio. È possibile utilizzare questa tecnica per tenere traccia dei flussi di lavoro costituito da più passaggi in messaggi in coda, senza dover ricominciare dall'inizio, se un passaggio di elaborazione non riesce a causa di un errore hardware o software. In genere, è consigliabile mantenere un numero di tentativi anche, e se il messaggio viene ritentato più di un numero di volte, è possibile eliminare. Ciò consente di proteggere un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Annullato l'accodamento del messaggio successivo

Il codice coda un messaggio da una coda in due passaggi. Quando si chiama `GetMessage`, viene visualizzato il messaggio successivo in una coda. Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice la lettura dei messaggi dalla coda. Per impostazione predefinita, il messaggio rimarrà invisibile per 30 secondi. Per completare la rimozione del messaggio dalla coda, è necessario chiamare `DeleteMessage`. Questo processo in due passaggi della rimozione di un messaggio garantisce che se il codice non riesce a elaborare un messaggio a causa di un errore hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare. Il codice chiama `DeleteMessage` subito dopo il messaggio è stato elaborato.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Utilizzare i flussi di lavoro asincrono all'archiviazione di Accodamento comuni API

In questo esempio viene illustrato come utilizzare un flusso di lavoro asincrono all'archiviazione di Accodamento comuni API.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opzioni aggiuntive per rimuovere Accodamento messaggi

Esistono due modi per personalizzare il recupero dei messaggi da una coda.
In primo luogo, è possibile ottenere un batch di messaggi (fino a 32). In secondo luogo, è possibile impostare un timeout di invisibilità superiori o inferiori, consentendo al codice più o meno tempo per elaborare completamente ogni messaggio. Nell'esempio di codice viene illustrato come utilizzare `GetMessages` per ottenere 20 messaggi in una chiamata e quindi elabora ogni messaggio. Inoltre, imposta il timeout di invisibilità cinque minuti per ogni messaggio. Si noti che viene avviato 5 minuti per tutti i messaggi nello stesso momento, dopo 5 minuti hanno passato dopo la chiamata a `GetMessages`, eventuali messaggi di cui non sono stati eliminati verrà visualizzati nuovamente.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Ottenere la lunghezza della coda

È possibile ottenere una stima del numero di messaggi in una coda. Il `FetchAttributes` metodo richiede il servizio di Accodamento di recuperare gli attributi di coda, incluso il conteggio dei messaggi. Il `ApproximateMessageCount` proprietà restituisce l'ultimo valore recuperato tramite il `FetchAttributes` metodo, senza chiamare il servizio di Accodamento.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminare una coda

Per eliminare una coda e tutti i messaggi in esso contenuti, chiamare il `Delete` metodo sull'oggetto di coda.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Passaggi successivi

Ora che si è appreso le nozioni fondamentali sull'archiviazione delle code, vedere i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse.

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del Team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Riferimento all'API REST di servizi di archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
