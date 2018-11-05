---
title: "Introduzione all'archiviazione Blob di Azure con F #"
description: Store dati non strutturati nel cloud con archiviazione Blob di Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: ea9dc334ec9c2bcd4a80cc501d4b6634da5f64e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44037282"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introduzione all'archiviazione Blob di Azure con F # #

Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB. Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione. Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.

Questo articolo illustra come eseguire attività comuni usando l'archiviazione Blob. Gli esempi sono scritti con F # tramite Azure Storage Client Library per .NET. Argomenti trattati includono come caricare, elencare, scaricare ed eliminare i BLOB.

Per una panoramica concettuale dell'archiviazione blob, vedere [la Guida di .NET per l'archiviazione blob](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account). Occorre anche la chiave di accesso di archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un Script F # e avvio di F # Interactive

Gli esempi in questo articolo possono essere utilizzati in un'applicazione F # o uno script F #. Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `blobs.fsx`, nell'ambiente di sviluppo F #.

Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` e `Microsoft.WindowsAzure.ConfigurationManager` pacchetti e riferimento `WindowsAzure.Storage.dll` e`Microsoft.WindowsAzure.Configuration.dll` nel script utilizzando un `#r` direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il codice seguente `open` istruzioni all'inizio del `blobs.fsx` file:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, simile al seguente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Si tratta tuttavia **sconsigliato** progetti per il real. La chiave dell'account è simile alla password radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave dell'account. Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Usando Gestione configurazione di Azure è facoltativa. È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Restituisce un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Creare alcuni dati fittizi locali

Prima di iniziare, creare alcuni dati fittizi locali nella directory dello script. In un secondo momento è caricare i dati.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Creare il client del servizio Blob

Il `CloudBlobClient` tipo consente di recuperare contenitori e BLOB archiviati nell'archivio Blob. Ecco un modo per creare il client del servizio:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archiviazione Blob.

## <a name="create-a-container"></a>Creare un contenitore

In questo esempio viene illustrato come creare un contenitore, se non esiste già:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Per impostazione predefinita, il nuovo contenitore è privato, vale a dire che è necessario specificare la chiave di accesso di archiviazione per scaricare BLOB da questo contenitore. Se si desidera rendere disponibili per tutti i file all'interno del contenitore, è possibile impostare il contenitore come pubblico utilizzando il codice seguente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Chiunque su Internet può visualizzare i BLOB in un contenitore pubblico, ma è possibile modificarli o eliminarli solo se disponibile la chiave di accesso account appropriato o una firma di accesso condiviso.

## <a name="upload-a-blob-into-a-container"></a>Caricare un blob in un contenitore

Archiviazione Blob di Azure supporta BLOB in blocchi e BLOB di pagine. Nella maggior parte dei casi, un blob in blocchi è il tipo consigliato da usare.

Per caricare un file in un blob in blocchi, ottenere un riferimento al contenitore e utilizzarlo per ottenere un riferimento al blob di blocco. Dopo aver creato un riferimento al blob, è possibile caricarvi qualsiasi flusso di dati a esso chiamando il `UploadFromFile` (metodo). Questa operazione crea il blob se non è stata precedentemente esiste o di sovrascriverlo se esiste.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Elencare i BLOB in un contenitore

Per elencare i BLOB in un contenitore, ottenere prima un riferimento al contenitore. È quindi possibile usare il contenitore `ListBlobs` metodo per recuperare i BLOB e/o le directory in esso contenuti. Per accedere all'insieme avanzato di proprietà e metodi per un `IListBlobItem`, è necessario eseguirne il cast a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` oggetto. Se il tipo è sconosciuto, è possibile usare un controllo del tipo per determinare quale eseguire il cast a. Il codice seguente viene illustrato come recuperare e visualizzare l'URI di ogni elemento di `mydata` contenitore:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

È anche possibile BLOB name con le informazioni sul percorso nei nomi. In questo modo viene creata una struttura di directory virtuale che è possibile organizzare e attraversare come un file system tradizionale. Si noti che la struttura di directory è solo virtuale, le uniche risorse disponibili nell'archiviazione Blob sono contenitori e BLOB. Tuttavia, la libreria client di archiviazione offre un `CloudBlobDirectory` oggetto per fare riferimento a una directory virtuale e semplificare il processo di utilizzo dei blob organizzati in questo modo.

Ad esempio, si consideri il seguente set di BLOB in blocchi in un contenitore denominato `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*

Quando si chiama `ListBlobs` su un contenitore (come nell'esempio precedente), viene restituito un elenco gerarchico. Se contiene entrambe `CloudBlobDirectory` e `CloudBlockBlob` oggetti, che rappresenta la directory e i BLOB nel contenitore, rispettivamente, quindi l'output risultante è simile al seguente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Facoltativamente, è possibile impostare il `UseFlatBlobListing` parametro del `ListBlobs` metodo `true`. In questo caso, tutti i blob nel contenitore viene restituito come un `CloudBlockBlob` oggetto. La chiamata a `ListBlobs` per restituire un elenco semplice si presenta come segue:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

e, in base al contenuto corrente del contenitore, i risultati un aspetto simile al seguente:

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

## <a name="download-blobs"></a>Scaricare i BLOB

Per scaricare BLOB, recuperare prima un riferimento al blob e quindi chiamare il `DownloadToStream` (metodo). L'esempio seguente usa il `DownloadToStream` metodo per trasferire il contenuto del blob a un oggetto stream che è quindi possibile rendere persistente in un file locale.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

È anche possibile usare il `DownloadToStream` metodo per scaricare il contenuto di un blob come stringa di testo.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminare i BLOB

Per eliminare un blob, ottenere prima un riferimento al blob e quindi chiamare il `Delete` metodo su di esso.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Elencare i BLOB di pagine in modo asincrono

Se si sta elencando un numero elevato di BLOB o si desidera controllare il numero di risultati restituiti in un'operazione di elenco, è possibile elencare i BLOB di pagine dei risultati. In questo esempio viene illustrato come restituire i risultati nelle pagine in modo asincrono, in modo che l'esecuzione non venga bloccata durante l'attesa della restituzione di un ampio set di risultati.

In questo esempio mostra un elenco di blob lineare, ma è anche possibile eseguire un elenco gerarchico impostando il `useFlatBlobListing` parametro del `ListBlobsSegmentedAsync` metodo `false`.

L'esempio definisce un metodo asincrono, tramite un `async` blocco. Il ``let!`` parola chiave sospende l'esecuzione del metodo di esempio fino al completamento dell'attività di elenco.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

È ora possibile usare questa routine asincrona come indicato di seguito. È innanzitutto necessario caricare alcuni dati fittizi (tramite il file locale creato in precedenza in questa esercitazione).

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

A questo punto, chiamare la routine. Si utilizza `Async.RunSynchronously` per forzare l'esecuzione dell'operazione asincrona.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>La scrittura in un blob di Accodamento

Un blob di accodamento è ottimizzato per operazioni di accodamento, ad esempio la registrazione. Come un blob in blocchi, un blob di accodamento è costituito da blocchi, ma quando si aggiunge un nuovo blocco per un blob di accodamento, viene aggiunto sempre alla fine del blob. È possibile aggiornare o eliminare un blocco esistente in un blob di Accodamento. L'ID del blocco per un blob di accodamento non sono esposti come lo sono per un blob in blocchi.

Ogni blocco in un blob di accodamento può avere dimensioni diverse, con un massimo di 4 MB, e un blob di accodamento può includere un massimo di 50.000 blocchi. Le dimensioni massime di un blob di accodamento sono pertanto leggermente superiore a 195 GB (4 MB X 50.000 blocchi).

Nell'esempio seguente crea un nuovo blob di accodamento e aggiunge alcuni dati, simulazione di un'operazione di registrazione semplice.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Visualizzare [informazioni sui BLOB in blocchi, BLOB di pagine e BLOB di Accodamento](https://msdn.microsoft.com/library/azure/ee691964.aspx) per altre informazioni sulle differenze tra i tre tipi di BLOB.

## <a name="concurrent-access"></a>Accesso simultaneo

Per supportare l'accesso simultaneo a un blob da più client o più istanze di processo, è possibile usare **ETags** oppure **lease**.

* **ETag** -fornisce un modo per rilevare che il blob o contenitore è stato modificato da un altro processo

* **Lease** -fornisce un modo per ottenere esclusivo, rinnovabile, scrivere o eliminare l'accesso a un blob per un periodo di tempo

Per altre informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Denominazione dei contenitori

Ogni blob in archiviazione di Azure deve risiedere in un contenitore. Il contenitore fa parte del nome del blob. Ad esempio, `mydata` è il nome del contenitore in questi URI del blob di esempio:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Nome del contenitore deve essere un nome DNS valido, conforme alle regole di denominazione seguente:

1. I nomi dei contenitori devono iniziare con una lettera o un numero e può contenere solo lettere, numeri e il carattere trattino (-).
1. Ogni trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero. nei nomi dei contenitori non sono consentiti trattini consecutivi.
1. Tutte le lettere di un nome di contenitore devono essere minuscole.
1. I nomi dei contenitori deve essere compresa tra 3 e 63 caratteri.

Si noti che il nome di un contenitore deve sempre essere minuscolo. Se si include una lettera maiuscola nel nome del contenitore o altrimenti viola le regole di denominazione del contenitore, si potrebbe ricevere un errore 400 (richiesta non valida).

## <a name="managing-security-for-blobs"></a>Gestione della sicurezza per i BLOB

Per impostazione predefinita, archiviazione di Azure protegge i dati, limitando l'accesso al proprietario dell'account, che possiede le chiavi dell'account l'accesso. Quando è necessario condividere dati blob nell'account di archiviazione, è importante farlo senza compromettere la protezione delle chiavi di accesso dell'account. Inoltre, è possibile crittografare i dati blob per assicurarsi che sia sicuro accedere in rete e in archiviazione di Azure.

### <a name="controlling-access-to-blob-data"></a>Controllo dell'accesso ai dati blob

Per impostazione predefinita, i dati blob nell'account di archiviazione sono accessibili solo al proprietario dell'account di archiviazione. Autenticare le richieste all'archiviazione Blob richiede la chiave di accesso di account per impostazione predefinita. Tuttavia, si potrebbe voler rendere disponibile ad altri utenti determinati dati blob.

Per informazioni dettagliate su come controllare l'accesso all'archiviazione blob, vedere [la Guida di .NET per la sezione di archiviazione blob sul controllo degli accessi](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).


### <a name="encrypting-blob-data"></a>La crittografia dei dati blob

Archiviazione di Azure supporta la crittografia dei dati blob sia nel client e nel server.

Per informazioni dettagliate sulla crittografia dei dati blob, vedere [la Guida di .NET per la sezione di archiviazione blob Encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).

## <a name="next-steps"></a>Passaggi successivi

A questo punto, dopo aver appreso le nozioni di base dell'archiviazione Blob, visitare i collegamenti seguenti per altre informazioni.

### <a name="tools"></a>Strumenti
- [F # AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An i Provider di tipi F # che può essere usato per esplorare le risorse Blob, tabelle e archiviazione code di Azure e applicare facilmente operazioni CRUD su di essi.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) F # un'API per l'uso del servizio di archiviazione tabelle di Microsoft Azure
- [Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) è un'app autonoma gratuita di Microsoft che consente di rappresentare facilmente dati di archiviazione di Azure in Windows, OS X e Linux.

### <a name="blob-storage-reference"></a>Riferimento all'archiviazione BLOB

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Riferimento all'API REST dei servizi di archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guide correlate

- [Introduzione all'archiviazione Blob di Azure nel linguaggio c#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Trasferire dati con l'utilità della riga di comando di AzCopy in Windows](/azure/storage/common/storage-use-azcopy)
- [Trasferire dati con l'utilità della riga di comando di AzCopy in Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Blog del Team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
