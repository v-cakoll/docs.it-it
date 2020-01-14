---
title: Introduzione all'archiviazione BLOB di Azure con F#
description: Archivia i dati non strutturati nel cloud con l'archiviazione BLOB di Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 90ec0d63b11ad00c53a1740211e9a6509582e863
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935509"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introduzione all'archiviazione BLOB di Azure con F\#

Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB. Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione. Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.

Questo articolo illustra come eseguire attività comuni usando l'archiviazione BLOB. Gli esempi vengono scritti usando F# la libreria client di archiviazione di Azure per .NET. Le attività descritte includono come caricare, elencare, scaricare ed eliminare BLOB.

Per una panoramica concettuale dell'archiviazione BLOB, vedere [la Guida di .NET per l'archiviazione BLOB](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account). È necessaria anche la chiave di accesso alle archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `blobs.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare i pacchetti `WindowsAzure.Storage` e `Microsoft.WindowsAzure.ConfigurationManager` e `WindowsAzure.Storage.dll` di riferimento e `Microsoft.WindowsAzure.Configuration.dll` nello script usando una direttiva `#r`.

### <a name="add-namespace-declarations"></a>Aggiungere dichiarazioni di spazi dei nomi

Aggiungere le istruzioni `open` seguenti all'inizio del file `blobs.fsx`:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere una stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, come segue:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Questa operazione non è tuttavia **consigliata** per i progetti reali. La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione. È consigliabile proteggere sempre la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

L'uso di Gestione configurazione di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo di `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Viene restituito un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Creare alcuni dati fittizi locali

Prima di iniziare, creare alcuni dati locali fittizi nella directory dello script. In seguito si caricherà questi dati.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Creare il client del servizio BLOB

Il tipo di `CloudBlobClient` consente di recuperare contenitori e BLOB archiviati nell'archivio BLOB. Ecco come creare il client del servizio:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archivio BLOB.

## <a name="create-a-container"></a>Creare un contenitore

In questo esempio viene creato un contenitore, nel caso in cui non esista già:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Per impostazione predefinita, il nuovo contenitore è privato, ovvero è necessario specificare la chiave di accesso alle risorse di archiviazione per scaricare BLOB da questo contenitore. Se si desidera che i file all'interno del contenitore siano disponibili a tutti, è possibile impostare il contenitore come pubblico usando il codice seguente:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

I BLOB in un contenitore pubblico sono visibili a tutti gli utenti di Internet, tuttavia è possibile modificarli o eliminarli solo se è disponibile la chiave di accesso dell'account appropriata o una firma di accesso condiviso.

## <a name="upload-a-blob-into-a-container"></a>Caricare un BLOB in un contenitore

In Archiviazione BLOB di Azure sono supportati BLOB in blocchi e BLOB di pagine. Nella maggior parte dei casi, un BLOB in blocchi è il tipo consigliato da usare.

Per caricare un file in un BLOB in blocchi, ottenere un riferimento a un contenitore e utilizzarlo per ottenere un riferimento a un BLOB in blocchi. Una volta ottenuto un riferimento al BLOB, è possibile caricarvi qualsiasi flusso di dati chiamando il metodo `UploadFromFile`. Questa operazione crea il BLOB se non esisteva in precedenza o lo sovrascrive se esiste.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Elencare i BLOB in un contenitore

Per elencare i BLOB in un contenitore, ottenere prima un riferimento al contenitore. È quindi possibile usare il metodo `ListBlobs` del contenitore per recuperare i BLOB e/o le directory al suo interno. Per accedere al set completo di proprietà e metodi per un `IListBlobItem`restituito, è necessario eseguirne il cast a un oggetto `CloudBlockBlob`, `CloudPageBlob`o `CloudBlobDirectory`. Se il tipo è sconosciuto, è possibile usare un controllo del tipo per determinare quello in cui viene eseguito il cast. Il codice seguente illustra come recuperare e visualizzare l'URI di ogni elemento del contenitore `mydata` :

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

È anche possibile assegnare un nome ai BLOB con le informazioni sul percorso nei rispettivi nomi. Consente di creare una struttura di directory virtuale che è possibile organizzare e attraversare come un file system tradizionale. Si noti che la struttura di directory è solo virtuale, le uniche risorse disponibili nell'archiviazione BLOB sono i contenitori e i BLOB. Tuttavia, la libreria client di archiviazione offre un oggetto `CloudBlobDirectory` per fare riferimento a una directory virtuale e semplificare il processo di utilizzo dei BLOB organizzati in questo modo.

Si consideri, ad esempio, il seguente set di BLOB in blocchi di un contenitore denominato `photos`:

*photo1.jpg*\
*2015/architecture/description.txt*\
*2015/architecture/photo3.jpg*\
*2015/architecture/photo4.jpg*\
*2016/architecture/photo5.jpg*\
*2016/architecture/photo6.jpg*\
*2016/architecture/description.txt*\
*2016/photo7.jpg*\

Quando si chiama `ListBlobs` su un contenitore, come nell'esempio precedente, viene restituito un elenco gerarchico. Se contiene sia `CloudBlobDirectory` che oggetti `CloudBlockBlob`, che rappresentano rispettivamente le directory e i BLOB nel contenitore, l'output risultante sarà simile al seguente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Facoltativamente, è possibile impostare il parametro `UseFlatBlobListing` del metodo `ListBlobs` su `true`. In questo caso, ogni BLOB nel contenitore viene restituito come oggetto `CloudBlockBlob`. La chiamata a `ListBlobs` per restituire un elenco semplice ha un aspetto simile al seguente:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

e, a seconda del contenuto corrente del contenitore, i risultati sono simili ai seguenti:

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>Scaricare BLOB

Per scaricare i BLOB, recuperare prima un riferimento al BLOB e quindi chiamare il metodo `DownloadToStream`. Nell'esempio seguente viene usato il metodo `DownloadToStream` per trasferire il contenuto del BLOB in un oggetto Stream che è quindi possibile salvare in modo permanente in un file locale.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

È anche possibile usare il metodo `DownloadToStream` per scaricare il contenuto di un BLOB come stringa di testo.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminare BLOB

Per eliminare un BLOB, ottenere prima un riferimento al BLOB e quindi chiamare il metodo `Delete`.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Elencare BLOB nelle pagine in modalità asincrona

Se si sta elencando un numero elevato di BLOB oppure si vuole controllare il numero di risultati restituiti in un'operazione di elenco, è possibile elencare i BLOB nelle pagine dei risultati. Questo esempio spiega come restituire i risultati nelle pagine in modalità asincrona, in modo che l'esecuzione non venga bloccata durante l'attesa della restituzione di un set di risultati di grandi dimensioni.

Questo esempio illustra un elenco di BLOB Flat, ma è anche possibile eseguire un elenco gerarchico, impostando il parametro `useFlatBlobListing` del metodo `ListBlobsSegmentedAsync` su `false`.

Nell'esempio viene definito un metodo asincrono utilizzando un blocco `async`. La parola chiave ``let!`` sospende l'esecuzione del metodo di esempio fino al completamento dell'attività di elenco.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

È ora possibile usare questa routine asincrona come indicato di seguito. Caricare prima di tutto i dati fittizi (usando il file locale creato in precedenza in questa esercitazione).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

A questo punto, chiamare la routine. Usare `Async.RunSynchronously` per forzare l'esecuzione dell'operazione asincrona.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Scrittura in un blob di Accodamento

Un blob di accodamento è ottimizzato per le operazioni di accodamento, ad esempio la registrazione. Come un blob in blocchi, un blob di accodamento è costituito da blocchi, ma quando si aggiunge un nuovo blocco in un blob di accodamento, viene aggiunto sempre alla fine del blob. È possibile aggiornare o eliminare un blocco esistente in un blob di Accodamento. L'ID di blocco per un blob di accodamento non vengono esposte come in un blob in blocchi.

Ogni blocco di un blob di accodamento può avere dimensioni diverse, con un massimo di 4 MB e un blob di accodamento può includere un massimo di 50.000 blocchi. La dimensione massima di un blob di accodamento è pertanto leggermente superiore a 195 GB (4 MB X 50.000 blocchi).

Nell'esempio seguente viene creato un nuovo BLOB di Accodamento e vengono aggiunti alcuni dati, simulando una semplice operazione di registrazione.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Vedere [Informazioni sui BLOB in blocchi, BLOB di pagine e BLOB di accodamento](https://msdn.microsoft.com/library/azure/ee691964.aspx) per ulteriori informazioni sulle differenze tra i tre tipi di BLOB.

## <a name="concurrent-access"></a>Accesso simultaneo

Per supportare l'accesso simultaneo a un BLOB da più client o da più istanze di processo, è possibile usare gli **ETag** o **lease**.

- **Etag** : fornisce un modo per rilevare le eventuali modifiche apportate al BLOB o contenitore da un altro processo

- **Lease** : consente di ottenere accesso esclusivo, rinnovabile, in scrittura o eliminazione a un BLOB per un periodo di tempo

Per ulteriori informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Denominazione di contenitori

Ogni BLOB nell'archiviazione di Azure deve risiedere in un contenitore. Il contenitore fa parte del nome del BLOB. Ad esempio, `mydata` è il nome del contenitore nei seguenti URI del BLOB di esempio:

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Il nome di un contenitore deve essere un nome DNS valido, in conformità con le regole di denominazione seguenti:

1. I nomi dei contenitori devono iniziare con una lettera o un numero e possono contenere solo lettere, numeri e il carattere trattino (-).
1. Ciascun carattere trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero: nei nomi dei contenitori non sono consentiti trattini consecutivi.
1. Tutte le lettere in un nome di contenitore deve essere composto solo da minuscole.
1. La lunghezza dei nomi dei contenitori deve essere compresa tra 3 e 63 caratteri.

Il nome di un contenitore deve sempre essere minuscolo. Se si include una lettera maiuscola nel nome di un contenitore o si violano in altro modo le regole di denominazione del contenitore, è possibile che venga visualizzato un errore 400 (richiesta non valida).

## <a name="managing-security-for-blobs"></a>Gestione della sicurezza dei BLOB

Per impostazione predefinita, Archiviazione di Azure garantisce la sicurezza dei dati limitando l'accesso al proprietario dell'account, che possiede le chiavi di accesso dell'account. Quando è necessario condividere dati BLOB nell'account di archiviazione, è importante farlo senza compromettere la sicurezza delle chiavi di accesso dell'account. È anche possibile crittografare i dati BLOB per assicurarne la sicurezza durante il trasferimento in rete e in Archiviazione di Azure.

### <a name="controlling-access-to-blob-data"></a>Controllo dell'accesso ai dati BLOB

Per impostazione predefinita, solo il proprietario dell'account di archiviazione può accedere ai dati BLOB in tale account. L'autenticazione delle richieste per l'archiviazione BLOB richiede la chiave di accesso dell'account per impostazione predefinita. Tuttavia, potrebbe essere necessario rendere disponibili determinati dati BLOB ad altri utenti.

### <a name="encrypting-blob-data"></a>Crittografia dei dati BLOB

Archiviazione di Azure supporta la crittografia dei dati BLOB sia sul client che sul server.

## <a name="next-steps"></a>Passaggi successivi

A questo punto, dopo avere appreso le nozioni di base dell'archivio BLOB, visitare i collegamenti seguenti per altre informazioni.

### <a name="tools"></a>Strumenti di

- [ F#\ AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)
Un F# provider di tipi che può essere usato per esplorare le risorse di archiviazione di Azure BLOB, tabelle e code e per applicare con facilità le operazioni CRUD.

- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
API F# per l'uso di Microsoft Azure servizio di archiviazione tabelle

- [Microsoft Azure Storage Explorer (Mase)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
App autonoma gratuita di Microsoft che consente di lavorare visivamente con i dati di archiviazione di Azure in Windows, OS X e Linux.

### <a name="blob-storage-reference"></a>Informazioni di riferimento sull'archiviazione BLOB

- [API di Archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Informazioni di riferimento sulle API REST dei servizi di Archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guide correlate

- [Introduzione con archiviazione BLOB di Azure inC#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Trasferire dati con l'utilità della riga di comando AzCopy in Windows](/azure/storage/common/storage-use-azcopy)
- [Trasferire dati con l'utilità della riga di comando AzCopy in Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Blog del team di Archiviazione di Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [Guida introduttiva: usare .NET per creare un BLOB nell'archivio oggetti](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
