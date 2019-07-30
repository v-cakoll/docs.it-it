---
title: Introduzione all'archiviazione BLOB di Azure con F#
description: Archivia i dati non strutturati nel cloud con l'archiviazione BLOB di Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c8b42339ff1d76f262e956b5e34cc598e0fc855d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630505"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introduzione all'archiviazione BLOB di Azure con F\#

Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB. Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione. Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.

Questo articolo illustra come eseguire attività comuni usando l'archiviazione BLOB. Gli esempi vengono scritti usando F# la libreria client di archiviazione di Azure per .NET. Le attività descritte includono come caricare, elencare, scaricare ed eliminare BLOB.

Per una panoramica concettuale dell'archiviazione BLOB, vedere [la Guida di .NET per l'archiviazione BLOB](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account). È necessaria anche la chiave di accesso alle archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l' `.fsx` estensione, ad esempio `blobs.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare `WindowsAzure.Storage` i `Microsoft.WindowsAzure.ConfigurationManager` pacchetti e e `WindowsAzure.Storage.dll` i `Microsoft.WindowsAzure.Configuration.dll` riferimenti e nello script usando `#r` una direttiva.

### <a name="add-namespace-declarations"></a>Aggiungi dichiarazioni dello spazio dei nomi

Aggiungere le seguenti `open` istruzioni all'inizio `blobs.fsx` del file:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, come segue:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Questa operazione **non** è tuttavia consigliata per i progetti reali. La chiave dell'account di archiviazione è simile alla password radice dell'account di archiviazione. Prestare sempre attenzione a proteggere la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

L'uso di Configuration Manager di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo `ConfigurationManager` di .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Viene restituito `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Creare alcuni dati fittizi locali

Prima di iniziare, creare alcuni dati locali fittizi nella directory dello script. In seguito si caricherà questi dati.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Creare il client del servizio BLOB

Il `CloudBlobClient` tipo consente di recuperare contenitori e BLOB archiviati nell'archivio BLOB. Ecco un modo per creare il client del servizio:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

A questo punto si è pronti per scrivere codice che legge e scrive i dati nell'archivio BLOB.

## <a name="create-a-container"></a>Creare un contenitore

Questo esempio illustra come creare un contenitore, se non esiste già:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Per impostazione predefinita, il nuovo contenitore è privato, vale a dire che è necessario specificare la chiave di accesso alle archiviazione per scaricare BLOB da questo contenitore. Se si desidera rendere i file all'interno del contenitore disponibili per tutti, è possibile impostare il contenitore come pubblico utilizzando il codice seguente:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Chiunque in Internet può visualizzare i BLOB in un contenitore pubblico, ma è possibile modificarli o eliminarli solo se si ha la chiave di accesso dell'account appropriata o una firma di accesso condiviso.

## <a name="upload-a-blob-into-a-container"></a>Caricare un BLOB in un contenitore

Archiviazione BLOB di Azure supporta BLOB in blocchi e BLOB di pagine. Nella maggior parte dei casi, un BLOB in blocchi è il tipo consigliato da usare.

Per caricare un file in un BLOB in blocchi, ottenere un riferimento al contenitore e usarlo per ottenere un riferimento al BLOB in blocchi. Una volta ottenuto un riferimento al BLOB, è possibile caricarvi qualsiasi flusso di dati chiamando il `UploadFromFile` metodo. Questa operazione crea il BLOB se non esisteva in precedenza o lo sovrascrive se esiste.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Elencare i BLOB in un contenitore

Per elencare i BLOB in un contenitore, ottenere prima un riferimento al contenitore. È quindi possibile usare il `ListBlobs` metodo del contenitore per recuperare i BLOB e/o le directory al suo interno. Per accedere al set completo di proprietà e metodi per un oggetto `IListBlobItem`restituito, è necessario eseguirne il `CloudBlockBlob`Cast `CloudPageBlob`a un `CloudBlobDirectory` oggetto, o. Se il tipo è sconosciuto, è possibile usare un controllo del tipo per determinare a quale eseguire il cast. Il codice seguente illustra come recuperare e restituire l'URI di ogni elemento nel `mydata` contenitore:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

È anche possibile assegnare un nome ai BLOB con le informazioni sul percorso nei rispettivi nomi. In questo modo si crea una struttura di directory virtuale che è possibile organizzare e attraversare come si farebbe con una tradizionale file system. Si noti che la struttura di directory è solo virtuale: le uniche risorse disponibili nell'archivio BLOB sono i contenitori e i BLOB. Tuttavia, la libreria client di archiviazione offre `CloudBlobDirectory` un oggetto per fare riferimento a una directory virtuale e semplificare il processo di utilizzo dei BLOB organizzati in questo modo.

Si consideri, ad esempio, il seguente set di BLOB in `photos`blocchi in un contenitore denominato:

*photo1.jpg*\
*2015/architecture/description.txt*\
*2015/architecture/photo3.jpg*\
*2015/architecture/photo4.jpg*\
*2016/architecture/photo5.jpg*\
*2016/architecture/photo6.jpg*\
*2016/architecture/description.txt*\
*2016/photo7.jpg*\

Quando si chiama `ListBlobs` su un contenitore, come nell'esempio precedente, viene restituito un elenco gerarchico. Se contiene entrambi `CloudBlobDirectory` gli oggetti `CloudBlockBlob` e, che rappresentano rispettivamente le directory e i BLOB nel contenitore, l'output risultante sarà simile al seguente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Facoltativamente, è possibile impostare il `UseFlatBlobListing` parametro `ListBlobs` del metodo su `true`. In questo caso, ogni BLOB nel contenitore viene restituito come `CloudBlockBlob` oggetto. La chiamata a `ListBlobs` per restituire un elenco semplice ha un aspetto simile al seguente:

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

## <a name="download-blobs"></a>Scaricare i BLOB

Per scaricare i BLOB, recuperare prima un riferimento al BLOB e quindi `DownloadToStream` chiamare il metodo. Nell'esempio seguente viene usato `DownloadToStream` il metodo per trasferire il contenuto del BLOB in un oggetto Stream che è quindi possibile salvare in modo permanente in un file locale.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

È anche possibile usare il `DownloadToStream` metodo per scaricare il contenuto di un BLOB come stringa di testo.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Elimina BLOB

Per eliminare un BLOB, ottenere prima un riferimento al BLOB e quindi chiamare `Delete` il metodo su di esso.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Elencare i BLOB in pagine in modo asincrono

Se si elenca un numero elevato di BLOB o si vuole controllare il numero di risultati restituiti in un'operazione di elenco, è possibile elencare i BLOB in pagine di risultati. Questo esempio Mostra come restituire i risultati in pagine in modo asincrono, in modo che l'esecuzione non venga bloccata durante l'attesa di restituire un set di risultati di grandi dimensioni.

Questo esempio illustra un elenco di BLOB Flat, ma è anche possibile eseguire un elenco gerarchico, impostando `useFlatBlobListing` il parametro `ListBlobsSegmentedAsync` del metodo su `false`.

Nell'esempio viene definito un metodo asincrono utilizzando un `async` blocco. La ``let!`` parola chiave sospende l'esecuzione del metodo di esempio fino al completamento dell'attività di elenco.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

È ora possibile usare questa routine asincrona come indicato di seguito. Caricare prima di tutto i dati fittizi (usando il file locale creato in precedenza in questa esercitazione).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

A questo punto, chiamare la routine. Usare `Async.RunSynchronously` per forzare l'esecuzione dell'operazione asincrona.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Scrittura in un BLOB di Accodamento

Un BLOB di accodamento è ottimizzato per le operazioni di Accodamento, ad esempio la registrazione. Analogamente a un BLOB in blocchi, un BLOB di accodamento è costituito da blocchi, ma quando si aggiunge un nuovo blocco a un BLOB di Accodamento, viene sempre accodato alla fine del BLOB. Non è possibile aggiornare o eliminare un blocco esistente in un BLOB di Accodamento. Gli ID blocco per un BLOB di Accodamento non vengono esposti come per un BLOB in blocchi.

Ogni blocco in un BLOB di accodamento può avere dimensioni diverse, fino a un massimo di 4 MB e un BLOB di accodamento può includere un massimo di 50.000 blocchi. La dimensione massima di un BLOB di accodamento è quindi leggermente superiore a 195 GB (4 MB X 50.000 blocchi).

Nell'esempio seguente viene creato un nuovo BLOB di Accodamento e vengono aggiunti alcuni dati, simulando una semplice operazione di registrazione.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Per altre informazioni sulle differenze tra i tre tipi di BLOB, vedere informazioni sui [BLOB in blocchi, BLOB di pagine e BLOB](https://msdn.microsoft.com/library/azure/ee691964.aspx) di Accodamento.

## <a name="concurrent-access"></a>Accesso simultaneo

Per supportare l'accesso simultaneo a un BLOB da più client o da più istanze di processo, è possibile usare **ETag** o **lease**.

* **ETag** : fornisce un modo per rilevare che il BLOB o il contenitore è stato modificato da un altro processo

* **Lease** : fornisce un modo per ottenere l'accesso esclusivo, rinnovabile, in scrittura o eliminazione a un BLOB per un certo periodo di tempo

Per ulteriori informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Denominazione di contenitori

Ogni BLOB in archiviazione di Azure deve risiedere in un contenitore. Il contenitore fa parte del nome del BLOB. Ad esempio, `mydata` è il nome del contenitore negli URI BLOB di esempio:

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Un nome di contenitore deve essere un nome DNS valido, conforme alle seguenti regole di denominazione:

1. I nomi dei contenitori devono iniziare con una lettera o un numero e possono contenere solo lettere, numeri e il carattere trattino (-).
1. Ogni trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero. nei nomi dei contenitori non sono consentiti trattini consecutivi.
1. Tutte le lettere in un nome di contenitore devono essere minuscole.
1. I nomi dei contenitori devono avere una lunghezza compreso tra 3 e 63 caratteri.

Si noti che il nome di un contenitore deve sempre essere minuscolo. Se si include una lettera maiuscola in un nome di contenitore o si violano in altro modo le regole di denominazione dei contenitori, è possibile che venga visualizzato un errore 400 (richiesta non valida).

## <a name="managing-security-for-blobs"></a>Gestione della sicurezza per i BLOB

Per impostazione predefinita, archiviazione di Azure garantisce la sicurezza dei dati limitando l'accesso al proprietario dell'account, che possiede le chiavi di accesso dell'account. Quando è necessario condividere i dati BLOB nell'account di archiviazione, è importante farlo senza compromettere la sicurezza delle chiavi di accesso dell'account. Inoltre, è possibile crittografare i dati BLOB per assicurarsi che siano protetti in rete e in archiviazione di Azure.

### <a name="controlling-access-to-blob-data"></a>Controllo dell'accesso ai dati BLOB

Per impostazione predefinita, i dati BLOB nell'account di archiviazione sono accessibili solo al proprietario dell'account di archiviazione. Per l'autenticazione delle richieste per l'archiviazione BLOB è necessaria la chiave di accesso dell'account per impostazione predefinita. Tuttavia, potrebbe essere necessario rendere disponibili determinati dati BLOB ad altri utenti.

### <a name="encrypting-blob-data"></a>Crittografia dei dati BLOB

Archiviazione di Azure supporta la crittografia dei dati BLOB sia sul client che sul server.

## <a name="next-steps"></a>Passaggi successivi

Ora che sono state apprese le nozioni di base dell'archiviazione BLOB, seguire questi collegamenti per altre informazioni.

### <a name="tools"></a>Strumenti

- [F#AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Un F# provider di tipi che può essere usato per esplorare le risorse di archiviazione di Azure BLOB, tabelle e code e per applicare con facilità le operazioni CRUD.

- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
API F# per l'uso di Microsoft Azure servizio di archiviazione tabelle

- [Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
App autonoma gratuita di Microsoft che consente di lavorare visivamente con i dati di archiviazione di Azure in Windows, OS X e Linux.

### <a name="blob-storage-reference"></a>Riferimento all'archiviazione BLOB

- [API di archiviazione di Azure per .NET](/dotnet/api/overview/azure/storage)
- [Informazioni di riferimento sull'API REST dei servizi di archiviazione di Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guide correlate

- [Introduzione con archiviazione BLOB di Azure inC#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Trasferire dati con l'utilità della riga di comando AzCopy in Windows](/azure/storage/common/storage-use-azcopy)
- [Trasferire dati con l'utilità della riga di comando AzCopy in Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurare le stringhe di connessione di archiviazione di Azure](/azure/storage/common/storage-configure-connection-string)
- [Blog del team di archiviazione di Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Avvio rapido: Usare .NET per creare un BLOB nell'archivio oggetti](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
