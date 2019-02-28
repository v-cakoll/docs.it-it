---
title: Iniziare a usare archiviazione di Accodamento di AzureF#
description: Le code di Azure offrono messaggistica asincrona affidabile tra i componenti dell'applicazione. Messaggistica cloud consente di ridimensionare in modo indipendente i componenti dell'applicazione.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974276"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introduzione all'archiviazione code di Azure con F\#

Archiviazione code di Azure fornisce messaggistica cloud tra i componenti dell'applicazione. Durante la progettazione di applicazioni scalabili, i componenti dell'applicazione vengono spesso separati, in modo che sia possibile ridimensionarli in modo indipendente. L'archivio Code fornisce la messaggistica asincrona per la comunicazione tra componenti dell'applicazione, che possono essere eseguiti nel cloud, sul desktop, in un server in locale o in un dispositivo mobile. Archiviazione code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro processi.

### <a name="about-this-tutorial"></a>Informazioni su questa esercitazione

Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure. Argomenti trattati includono la creazione e l'eliminazione di code e aggiunta, la lettura e l'eliminazione dei messaggi di coda.

Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
È necessario anche la chiave di accesso di archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un F# creare uno Script e avviare F# interattivo

Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script. Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `queues.fsx`, nella F# ambiente di sviluppo.

Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il codice seguente `open` istruzioni all'inizio del `queues.fsx` file:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Si tratta tuttavia **sconsigliato** progetti per il real. La chiave dell'account è simile alla password radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave dell'account. Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Usando Gestione configurazione di Azure è facoltativa. È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Creare il client di servizio di Accodamento

Il `CloudQueueClient` classe consente di recuperare le code archiviate nell'archiviazione di Accodamento. Ecco un modo per creare il client del servizio:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione di Accodamento.

## <a name="create-a-queue"></a>Creare una coda

In questo esempio viene illustrato come creare una coda, se non esiste già:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Inserire un messaggio in una coda

Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`. Successivamente, chiamare il `AddMessage` (metodo). Oggetto `CloudQueueMessage` possono essere creati da una stringa (in formato UTF-8) o un `byte` matrice, simile al seguente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Visualizza il messaggio successivo

È possibile visualizzare il messaggio successivo di una coda senza rimuoverlo dalla coda chiamando il `PeekMessage` (metodo).

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Ottiene il messaggio successivo per l'elaborazione

È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione tramite la chiamata di `GetMessage` (metodo).

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

In un secondo momento indicano l'elaborazione corretta del messaggio utilizzando `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Modificare il contenuto di un messaggio in coda

È possibile modificare il contenuto di un messaggio recuperato inserito nella coda. Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornare lo stato dell'attività di lavoro. Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per prolungarlo di altri 60 secondi. Questo consente di salvare lo stato del lavoro associata al messaggio e consente al client un altro minuto per continuare a utilizzare il messaggio. È possibile usare questa tecnica per tenere traccia dei flussi di lavoro costituito da più passaggi nei messaggi in coda, senza la necessità di ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di errori hardware o software. In genere, è consigliabile mantenere anche un numero di tentativi e verrà effettuati più di un numero di volte in cui il messaggio, è necessario eliminarlo. Ciò consente di proteggere un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Rimuovere il messaggio successivo dalla coda

Il codice inseriscono nella coda un messaggio da una coda in due passaggi. Quando si chiama `GetMessage`, viene visualizzato il messaggio successivo in una coda. Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice che legge messaggi dalla stessa coda. Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi. Per completare la rimozione del messaggio dalla coda, è necessario chiamare anche `DeleteMessage`. Questo processo in due passaggi di rimozione di un messaggio assicura che se il codice non riesce a elaborare un messaggio a causa di errori hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare. Il codice chiama `DeleteMessage` immediatamente dopo il messaggio è stato elaborato.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Usare flussi di lavoro asincroni con API comuni di archiviazione coda

In questo esempio mostra come usare un flusso di lavoro di async con API comuni di archiviazione coda.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opzioni aggiuntive per i messaggi dalla coda deprovisioning

Esistono due modi per personalizzare il recupero di messaggi da una coda.
In primo luogo, è possibile recuperare un batch di messaggi (massimo 32). In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o breve, consentendo al codice più o meno tempo per elaborare completamente ogni messaggio. Il codice seguente viene illustrato come utilizzare `GetMessages` per ottenere i 20 messaggi in una chiamata e quindi elabori ogni messaggio. Imposta inoltre il timeout di invisibilità viene impostato su cinque minuti per ogni messaggio. Si noti che i cinque minuti iniziano per tutti i messaggi contemporaneamente, pertanto, dopo 5 minuti trascorsi dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventano nuovamente visibili.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Ottenere la lunghezza della coda

È possibile ottenere una stima del numero di messaggi in una coda. Il `FetchAttributes` metodo richiede il servizio di Accodamento di recuperare gli attributi della coda, incluso il numero di messaggi. Il `ApproximateMessageCount` proprietà restituisce l'ultimo valore recuperato dal `FetchAttributes` metodo, senza chiamare il servizio di Accodamento.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminare una coda

Per eliminare una coda e tutti i messaggi in esso contenuti, chiamare il `Delete` metodo sull'oggetto coda.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Passaggi successivi

A questo punto, dopo aver appreso le nozioni di base dell'archiviazione di accodamento, visitare i collegamenti seguenti per altre informazioni sulle attività di archiviazione più complesse.

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del Team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Riferimento all'API REST dei servizi di archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
