---
title: Introduzione all'archiviazione code di Azure con F#
description: Le code di Azure forniscono una messaggistica asincrona affidabile tra i componenti dell'applicazione. La messaggistica cloud consente di ridimensionare i componenti dell'applicazione in modo indipendente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 841068ac91aecc53811359e27d984907569a2c6d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935499"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introduzione all'archiviazione code di Azure con F\#

L'archivio code di Azure fornisce la messaggistica cloud tra i componenti dell'applicazione. Durante la progettazione di applicazioni scalabili, i componenti dell'applicazione vengono spesso separati, per poter essere scalati in modo indipendente. L'archivio code fornisce la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, che possono essere eseguiti nel cloud, in un desktop, in un server locale o in un dispositivo mobile. Archiviazione code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro dei processi.

### <a name="about-this-tutorial"></a>Informazioni su questa esercitazione

Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure. Le attività descritte includono creazione ed eliminazione di code e aggiunta, lettura ed eliminazione dei messaggi in coda.

Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Sarà necessaria anche la chiave di accesso alle archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `queues.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto di `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`.

### <a name="add-namespace-declarations"></a>Aggiungere dichiarazioni di spazi dei nomi

Aggiungere le istruzioni `open` seguenti all'inizio del file `queues.fsx`:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Ottenere una stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, come segue:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Questa operazione non è tuttavia **consigliata** per i progetti reali. La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione. È consigliabile proteggere sempre la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

L'uso di Gestione configurazione di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo di `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Creare il client del servizio di accodamento

La classe `CloudQueueClient` consente di recuperare le code archiviate nell'archivio code. Ecco come creare il client del servizio:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archivio code.

## <a name="create-a-queue"></a>Crea una coda

Questo esempio illustra come creare una coda se non esiste già:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Inserire un messaggio in una coda

Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`. Chiamare quindi il metodo `AddMessage`. È possibile creare un `CloudQueueMessage` da una stringa (in formato UTF-8) o da una matrice di `byte`, come indicato di seguito:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Visualizzare il messaggio successivo

È possibile visualizzare il messaggio nella parte anteriore di una coda senza rimuoverlo dalla coda, chiamando il metodo `PeekMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Ottenere il messaggio successivo per l'elaborazione

È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il metodo `GetMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

In un secondo momento si indicherà la corretta elaborazione del messaggio utilizzando `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Cambiare il contenuto di un messaggio in coda

È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda. Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornarne lo stato. Il codice seguente consente di aggiornare il messaggio in coda con nuovo contenuto e di impostarne il timeout di visibilità per prolungarlo di altri 60 secondi. In questo modo lo stato del lavoro associato al messaggio viene salvato e il client ha a disposizione un altro minuto per continuare l'elaborazione del messaggio. È possibile usare questa tecnica per tenere traccia di flussi di lavoro composti da più passaggi nei messaggi in coda, senza la necessità di ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di errori hardware o software. In genere si mantiene anche un numero di tentativi e se il messaggio viene ritentato più di un determinato numero di volte, è necessario eliminarlo. In questo modo è possibile evitare che un messaggio attivi un errore dell'applicazione ogni volta che viene elaborato.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Rimuovere il messaggio successivo dalla coda

Il codice consente di rimuovere un messaggio da una coda in due passaggi. Quando si chiama `GetMessage`, si ottiene il messaggio successivo in una coda. Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro elemento di codice che legge i messaggi di questa coda. Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi. Per completare la rimozione del messaggio dalla coda, è necessario chiamare anche `DeleteMessage`. Questo processo in due passaggi di rimozione di un messaggio assicura che, qualora l'elaborazione di un messaggio non riesca a causa di errori hardware o software, un'altra istanza del codice sia in grado di ottenere lo stesso messaggio e di riprovare. Il codice chiama `DeleteMessage` subito dopo l'elaborazione del messaggio.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Usare i flussi di lavoro asincroni con API di archiviazione code comuni

Questo esempio illustra come usare un flusso di lavoro asincrono con API di archiviazione di accodamento comuni.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opzioni aggiuntive per rimuovere i messaggi dalla coda

È possibile personalizzare il recupero di messaggi da una coda in due modi.
Innanzitutto, è possibile recuperare un batch di messaggi (massimo 32). In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o più breve assegnando al codice più o meno tempo per l'elaborazione completa di ogni messaggio. Nell'esempio di codice seguente viene usato `GetMessages` per ottenere 20 messaggi in una sola chiamata e quindi elaborare ogni messaggio. Per ogni messaggio, inoltre, il timeout di invisibilità viene impostato su cinque minuti. Si noti che i 5 minuti iniziano per tutti i messaggi contemporaneamente, quindi dopo che sono trascorsi 5 minuti dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventeranno nuovamente visibili.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Recuperare la lunghezza della coda

È possibile ottenere una stima sul numero di messaggi presenti in una coda. Il metodo `FetchAttributes` chiede al Servizio di accodamento di recuperare gli attributi della coda, incluso il numero di messaggi. La proprietà `ApproximateMessageCount` restituisce l'ultimo valore recuperato dal metodo `FetchAttributes`, senza chiamare il Servizio di accodamento.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminare una coda

Per eliminare una coda e tutti i messaggi che contiene, chiamare il metodo `Delete` sull'oggetto Queue.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Passaggi successivi

A questo punto, dopo aver appreso le nozioni di base dell'archiviazione di accodamento, visitare i collegamenti seguenti per altre informazioni sulle attività di archiviazione più complesse.

- [API di Archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del team di Archiviazione di Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Informazioni di riferimento sulle API REST dei servizi di Archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
