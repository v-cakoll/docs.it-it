---
title: Introduzione all'archiviazione code di Azure con F#
description: Le code di Azure forniscono messaggistica asincrona e affidabile tra i componenti dell'applicazione. La messaggistica cloud consente di ridimensionare i componenti dell'applicazione in modo indipendente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a09cbdd4b995e34177c110ce91b02162bb19dfa8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423850"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introduzione all'archiviazione code di Azure con F\#

Archiviazione code di Azure fornisce la messaggistica cloud tra i componenti dell'applicazione. Nella progettazione di applicazioni per la scalabilità, i componenti dell'applicazione vengono spesso separati, in modo che possano essere ridimensionati in modo indipendente. L'archiviazione di Accodamento offre la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, indipendentemente dal fatto che siano in esecuzione nel cloud, sul desktop, in un server locale o in un dispositivo mobile. L'archiviazione Code supporta anche la gestione di attività asincrone e la compilazione di flussi di lavoro di processo.

### <a name="about-this-tutorial"></a>Informazioni su questa esercitazione

Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure. Le attività descritte includono creazione ed eliminazione di code e aggiunta, lettura ed eliminazione dei messaggi in coda.

Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Prerequisites

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Sarà necessaria anche la chiave di accesso alle archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `queues.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`.

### <a name="add-namespace-declarations"></a>Aggiungi dichiarazioni dello spazio dei nomi

Aggiungere le seguenti istruzioni `open` all'inizio del file di `queues.fsx`:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, come segue:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Questa operazione non è tuttavia **consigliata** per i progetti reali. La chiave dell'account di archiviazione è simile alla password radice dell'account di archiviazione. Prestare sempre attenzione a proteggere la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

L'uso di Configuration Manager di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Creare il client di Servizio di accodamento

La classe `CloudQueueClient` consente di recuperare le code archiviate nell'archivio code. Ecco un modo per creare il client del servizio:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

A questo punto si è pronti per scrivere codice che legge e scrive i dati nell'archivio code.

## <a name="create-a-queue"></a>Creare una coda

Questo esempio illustra come creare una coda se non esiste già:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Inserire un messaggio in una coda

Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`. Chiamare quindi il metodo `AddMessage`. È possibile creare un `CloudQueueMessage` da una stringa (in formato UTF-8) o da una matrice di `byte`, come indicato di seguito:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Visualizza il messaggio successivo

È possibile visualizzare il messaggio nella parte anteriore di una coda senza rimuoverlo dalla coda, chiamando il metodo `PeekMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Ottenere il messaggio successivo per l'elaborazione

È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il metodo `GetMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

In un secondo momento si indicherà la corretta elaborazione del messaggio utilizzando `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Modificare il contenuto di un messaggio in coda

È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda. Se il messaggio rappresenta un'attività di lavoro, è possibile usare questa funzionalità per aggiornare lo stato dell'attività di lavoro. Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per estendere altri 60 secondi. In questo modo si salva lo stato del lavoro associato al messaggio e si concede al client un altro minuto per continuare a lavorare sul messaggio. È possibile utilizzare questa tecnica per tenere traccia dei flussi di lavoro in più passaggi nei messaggi in coda, senza dover ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di un errore hardware o software. In genere si mantiene anche un numero di tentativi e se il messaggio viene ritentato più di un determinato numero di volte, è necessario eliminarlo. In questo modo si protegge da un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Annulla la coda del messaggio successivo

Il codice rimuove un messaggio da una coda in due passaggi. Quando si chiama `GetMessage`, si ottiene il messaggio successivo in una coda. Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice che legge i messaggi da questa coda. Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi. Per completare la rimozione del messaggio dalla coda, è necessario chiamare anche `DeleteMessage`. Questo processo in due passaggi di rimozione di un messaggio assicura che se il codice non riesce a elaborare un messaggio a causa di un errore hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare. Il codice chiama `DeleteMessage` subito dopo l'elaborazione del messaggio.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Usare i flussi di lavoro asincroni con API di archiviazione code comuni

Questo esempio illustra come usare un flusso di lavoro asincrono con API di archiviazione di accodamento comuni.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opzioni aggiuntive per rimuovere i messaggi dalla coda di Accodamento

È possibile personalizzare il recupero dei messaggi da una coda in due modi.
Per prima cosa, è possibile ottenere un batch di messaggi (fino a 32). In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o più breve, consentendo al codice più o meno tempo di elaborare completamente ogni messaggio. Nell'esempio di codice seguente viene usato `GetMessages` per ottenere 20 messaggi in una sola chiamata e quindi elaborare ogni messaggio. Imposta anche il timeout di invisibilità su cinque minuti per ogni messaggio. Si noti che i 5 minuti iniziano per tutti i messaggi contemporaneamente, quindi dopo che sono trascorsi 5 minuti dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventeranno nuovamente visibili.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Ottenere la lunghezza della coda

È possibile ottenere una stima del numero di messaggi in una coda. Il metodo `FetchAttributes` chiede al Servizio di accodamento di recuperare gli attributi della coda, incluso il numero di messaggi. La proprietà `ApproximateMessageCount` restituisce l'ultimo valore recuperato dal metodo `FetchAttributes`, senza chiamare il Servizio di accodamento.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminare una coda

Per eliminare una coda e tutti i messaggi che contiene, chiamare il metodo `Delete` sull'oggetto Queue.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Passaggi successivi

Ora che sono state apprese le nozioni di base dell'archiviazione code, seguire i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse.

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Provider di tipi di archiviazione di Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Informazioni di riferimento sull'API REST dei servizi di archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
