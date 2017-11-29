---
title: 'Introduzione all''archiviazione Blob di Azure con F #'
description: Archiviare dati non strutturati nel cloud con archiviazione Blob di Azure.
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c5b74a4f-dcd1-4849-930c-904b6c8a04e1
ms.openlocfilehash: 92e26aff605d3bed89e388dd3616a2a9a3a96081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introduzione all'archiviazione Blob di Azure con F # #

Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB. Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione. Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.

In questo articolo viene illustrato come eseguire attività comuni di utilizzo dell'archiviazione Blob. Gli esempi sono scritte in F # utilizzando la libreria Client di archiviazione di Azure per .NET. Argomenti trattati includono le modalità caricare, elenco, scaricare ed eliminare i BLOB.

Per una panoramica concettuale dell'archiviazione blob, vedere [la Guida di .NET per l'archiviazione blob](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account). È necessario anche la chiave di accesso di archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un Script F # e avvio di F # Interactive

Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #. Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `blobs.fsx`, nell'ambiente di sviluppo F #.

Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` e `Microsoft.WindowsAzure.ConfigurationManager` pacchetti e riferimento `WindowsAzure.Storage.dll` e `Microsoft.WindowsAzure.Configuration.dll` nel script utilizzando un `#r` direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il seguente `open` istruzioni all'inizio di `blobs.fsx` file:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, simile al seguente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Si tratta tuttavia **non è consigliabile** di progetti. La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave di account di archiviazione. Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Utilizzando Gestione configurazione di Azure è facoltativa. È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, utilizzare:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Restituisce un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Creare alcuni dati fittizi locali

Prima di iniziare, creare alcuni dati fittizi locali nella directory dello script. In un secondo momento caricare questi dati.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Creare il client del servizio Blob

Il `CloudBlobClient` tipo consente di recuperare i contenitori e BLOB archiviati nell'archiviazione Blob. Ecco un modo per creare il client del servizio:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati nell'archiviazione Blob.

## <a name="create-a-container"></a>Creare un contenitore

In questo esempio viene illustrato come creare un contenitore, se non esiste già:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Per impostazione predefinita, il nuovo contenitore è privato, vale a dire che è necessario specificare la chiave di accesso di archiviazione per il download di BLOB da questo contenitore. Se si desidera rendere disponibili i file all'interno del contenitore per tutti gli utenti, è possibile impostare il contenitore sia pubblico utilizzando il codice seguente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Chiunque su Internet può visualizzare i BLOB in un contenitore pubblico, ma è possibile modificare o eliminare solo se è la chiave di accesso account appropriato o una firma di accesso condiviso.

## <a name="upload-a-blob-into-a-container"></a>Caricare un blob in un contenitore

Archiviazione Blob di Azure supporta i BLOB in blocchi e BLOB di pagine. Nella maggior parte dei casi, un blob in blocchi è il tipo consigliato da usare.

Per caricare un file di un blob in blocchi, ottenere un riferimento a un contenitore e usarlo per ottenere un riferimento di blob di blocco. Dopo aver creato un riferimento di blob, è possibile caricare qualsiasi flusso di dati a esso tramite la chiamata di `UploadFromFile` metodo. Questa operazione crea il blob se non è stata precedentemente esiste, o sovrascrivere il file se esiste.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Elencare i BLOB in un contenitore

Per elencare i BLOB in un contenitore, innanzitutto ottenere un riferimento di contenitore. È quindi possibile utilizzare il contenitore `ListBlobs` metodo per recuperare il BLOB e/o directory all'interno di esso. Per accedere al set completo di proprietà e metodi per un tipo restituito `IListBlobItem`, è necessario eseguirne il cast a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` oggetto. Se il tipo è sconosciuto, è possibile utilizzare un controllo del tipo per determinare quale eseguire il cast a. Il codice seguente viene illustrato come recuperare e l'URI di ciascun elemento di output di `mydata` contenitore:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

È inoltre possibile BLOB nome con informazioni sul percorso nei nomi. Questo crea una struttura di directory virtuale che è possibile organizzare e attraversare come si farebbe un sistema di file tradizionali. Si noti che la struttura di directory virtuale solo - solo le risorse disponibili nell'archiviazione Blob sono contenitori e BLOB. Tuttavia, la libreria client di archiviazione offre un `CloudBlobDirectory` oggetto per fare riferimento a una directory virtuale e semplificare il processo d'uso di BLOB sono organizzati in questo modo.

Ad esempio, si consideri il seguente set di BLOB in blocchi in un contenitore denominato `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / architettura/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*

Quando si chiama `ListBlobs` su un contenitore (come nell'esempio precedente), viene restituito un elenco gerarchico. Se contiene entrambe `CloudBlobDirectory` e `CloudBlockBlob` oggetti, che rappresenta la directory e BLOB nel contenitore, rispettivamente, quindi l'output risulta sarà simile al seguente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Facoltativamente, è possibile impostare il `UseFlatBlobListing` parametro del `ListBlobs` metodo `true`. In questo caso, ogni blob nel contenitore viene restituito come un `CloudBlockBlob` oggetto. La chiamata a `ListBlobs` per restituire un elenco semplice è simile al seguente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

Inoltre, a seconda del contenuto corrente del contenitore, i risultati simile al seguente:

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

Per scaricare i BLOB, recuperare innanzitutto un riferimento di blob e quindi chiamare il `DownloadToStream` metodo. L'esempio seguente usa il `DownloadToStream` metodo per trasferire il contenuto del blob a un oggetto flusso che può quindi essere resa persistente in un file locale.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

È inoltre possibile utilizzare il `DownloadToStream` metodo per scaricare il contenuto di un blob come una stringa di testo.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminare i BLOB

Per eliminare un blob, innanzitutto ottenere un riferimento di blob e quindi chiamare il `Delete` metodo su di esso.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Elenco di BLOB di pagine in modo asincrono

Elencare un numero elevato di BLOB, se si desidera controllare il numero di risultati che restituito in un'unica operazione di elenco, è possibile elencare i BLOB di pagine di risultati. In questo esempio viene illustrato come restituire risultati in pagine in modo asincrono, in modo che non l'esecuzione viene bloccata durante l'attesa per restituire un ampio set di risultati.

Questo esempio viene illustrato un semplice elenco di blob, ma è anche possibile eseguire un elenco gerarchico, impostando il `useFlatBlobListing` parametro del `ListBlobsSegmentedAsync` metodo `false`.

L'esempio definisce un metodo asincrono, utilizzando un `async` blocco. Il ``let!`` (parola chiave) sospende l'esecuzione del metodo di esempio fino al completamento dell'attività dell'elenco.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

È possibile utilizzare ora questa routine asincrona, come indicato di seguito. È innanzitutto necessario caricare alcuni dati fittizi (con il file locale creato in precedenza in questa esercitazione).

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

A questo punto, chiamare la routine. Utilizzare ``Async.RunSynchronously`` per forzare l'esecuzione dell'operazione asincrona.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Scrittura in un blob di aggiunta

Un blob di aggiunta è ottimizzato per le operazioni di accodamento, ad esempio la registrazione. Come un blob in blocchi, un blob di aggiunta è costituito da blocchi, ma quando si aggiunge un nuovo blocco per un blob di aggiunta, vengono sempre aggiunte alla fine del blob. È possibile aggiornare o eliminare un blocco esistente in un blob di aggiunta. L'ID di blocco per un blob di aggiunta non vengono esposte come se fossero per un blob in blocchi.

Ogni blocco di un blob di aggiunta può avere dimensioni diverse, fino a un massimo di 4 MB, e un blob di aggiunta può includere un massimo di 50.000 blocchi. Le dimensioni massime di un blob di aggiunta sono leggermente più 195 GB (4 MB X 50.000 blocchi).

Nell'esempio seguente crea un nuovo blob di aggiunta e aggiunge alcuni dati, simulazione di un'operazione di registrazione semplice.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Vedere [informazioni sui BLOB in blocchi, BLOB di pagine e BLOB, accodare](https://msdn.microsoft.com/library/azure/ee691964.aspx) per ulteriori informazioni sulle differenze tra i tre tipi di BLOB.

## <a name="concurrent-access"></a>Accesso simultaneo

Per supportare l'accesso simultaneo a un blob da più client o più istanze di processo, è possibile utilizzare **eTag** o **lease**.

* **ETag** -consente di rilevare che il blob o contenitore è stato modificato da un altro processo

* **Lease** -consente di ottenere rinnovabile a vicenda, scrivere o eliminare l'accesso a un blob per un periodo di tempo

Per ulteriori informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Denominazione dei contenitori

Ogni blob nell'archiviazione di Azure deve risiedere in un contenitore. Il contenitore costituisce parte del nome del blob. Ad esempio, `mydata` è il nome del contenitore in questi blob URI di esempio:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Un nome di contenitore deve essere un nome DNS valido, conforme alle regole di denominazione seguente:

1. Il nome del contenitore devono iniziare con una lettera o un numero e possono contenere solo lettere, numeri e trattini (-).
1. Ogni trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero. nei nomi dei contenitori non sono consentiti trattini consecutivi.
1. Tutte le lettere di un nome di contenitore devono essere minuscole.
1. Il nome del contenitore devono essere compresa tra 3 e 63 caratteri.

Si noti che il nome di un contenitore deve essere sempre lettere minuscole. Se si include una lettera maiuscola in un nome di contenitore o in altro modo il contenitore di regole di denominazione, si potrebbe ricevere un errore 400 (richiesta non valida).

## <a name="managing-security-for-blobs"></a>Gestione della sicurezza per i BLOB

Per impostazione predefinita, archiviazione di Azure i dati rimangono al sicuro limitando l'accesso al proprietario dell'account, che è in possesso delle chiavi di accesso account. Quando è necessario condividere i dati blob nell'account di archiviazione, è importante eseguire questa operazione senza compromettere la protezione di chiavi di accesso account. Inoltre, è possibile crittografare i dati blob per assicurarsi che sia sicuro accedere in rete e archiviazione di Azure.

### <a name="controlling-access-to-blob-data"></a>Controllo dell'accesso ai dati blob

Per impostazione predefinita, i dati blob nell'account di archiviazione sono accessibili solo al proprietario dell'account di archiviazione. Autenticazione delle richieste nel servizio di archiviazione Blob richiede la chiave di account di accesso per impostazione predefinita. Tuttavia, è consigliabile rendere determinati dati blob disponibile ad altri utenti.

Per informazioni dettagliate su come controllare l'accesso all'archiviazione blob, vedere [la Guida di .NET per la sezione di archiviazione blob sul controllo di accesso](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).


### <a name="encrypting-blob-data"></a>La crittografia dei dati blob

Archiviazione di Azure supporta la crittografia dei dati blob nel client e nel server.

Per informazioni dettagliate sulla crittografia dei dati blob, vedere [la Guida di .NET per la sezione di archiviazione blob su crittografia](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).

## <a name="next-steps"></a>Passaggi successivi

Ora che si è appreso le nozioni di base dell'archiviazione Blob, vedere i collegamenti seguenti per ulteriori informazioni.

### <a name="tools"></a>Strumenti
- [F # AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) An i Provider di tipi F # che può essere usato per esplorare le risorse Blob, tabella e coda di archiviazione di Azure e applicare facilmente operazioni CRUD su di essi.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) F # un'API per l'utilizzo del servizio di archiviazione tabelle di Microsoft Azure
- [Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) è un'applicazione autonoma gratuita, da Microsoft che consente di utilizzare visivamente i dati di archiviazione di Azure in Windows, OS X e Linux.

### <a name="blob-storage-reference"></a>Riferimento all'archiviazione BLOB

- [Libreria Client di archiviazione per il riferimento di .NET](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [Riferimento all'API REST](http://msdn.microsoft.com/library/azure/dd179355)

### <a name="related-guides"></a>Guide correlate

- [Introduzione all'archiviazione Blob di Azure in c#](https://azure.microsoft.com/documentation/samples/storage-blob-dotnet-getting-started/)
- [Trasferimento dati con l'utilità della riga di comando AzCopy](/azure/storage/storage-use-azcopy)
- [Configurazione delle stringhe di connessione](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [Blog del Team di archiviazione di Azure](http://blogs.msdn.com/b/windowsazurestorage/)
