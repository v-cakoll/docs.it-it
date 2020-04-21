---
title: Introduzione all'archiviazione file di Azure con F#
description: Archiviare i dati dei file nel cloud con Archiviazione file di Azure e montare la condivisione di file nel cloud da una macchina virtuale Azure (VM) o da un'applicazione locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 1b38ee53f2f73f7b7f4ee12f712f487cb726d41e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739599"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introduzione all'archiviazione dei file di Azure tramite FGet started with Azure File storage using F\#

Archiviazione file di Azure offre condivisioni file nel cloud usando il [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)standard. Sono supportati sia SMB 2.1 che SMB 3.0. Con Archiviazione file di Azure si può eseguire la migrazione ad Azure delle applicazioni legacy basate su condivisioni file velocemente e senza costose riscritture. Le applicazioni in esecuzione in macchine virtuali di Azure o in servizi cloud oppure in client locali possono montare una condivisione file nel cloud, esattamente come un'applicazione desktop monta una tipica condivisione SMB. Non ci sono limiti per i componenti delle applicazioni che possono montare e accedere contemporaneamente alla condivisione di archiviazione file.

Per una panoramica concettuale dell'archiviazione dei file, vedere [la guida .NET per l'archiviazione dei file](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa guida, è innanzitutto necessario creare un account di archiviazione di [Azure.To](https://docs.microsoft.com/azure/storage/storage-create-storage-account)use this guide, you must first create an Azure storage account .
Sarà inoltre necessaria la chiave di accesso all'archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno script F , e avviare F E Interactive

Gli esempi in questo articolo possono essere usati in un'applicazione F o in uno script F. Per creare uno script F, creare `.fsx` un file `files.fsx`con l'estensione, ad esempio , nell'ambiente di sviluppo F.

Usare quindi un gestore di [pacchetti,](package-management.md) ad esempio `WindowsAzure.Storage` [Paket](https://fsprojects.github.io/Paket/) o [NuGet,](https://www.nuget.org/) per installare il pacchetto e il riferimento `WindowsAzure.Storage.dll` nello script usando una `#r` direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere le istruzioni `open` seguenti all'inizio del file `files.fsx`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere una stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di Archiviazione di Azure.You'll need an Azure Storage connection string for this tutorial. Per ulteriori informazioni sulle stringhe di connessione, vedere [Configurare le stringhe](https://docs.microsoft.com/azure/storage/storage-configure-connection-string)di connessione di archiviazione .

Per l'esercitazione, immettere la stringa di connessione nello script, in questo modo:For the tutorial, you'll enter your connection string in your script, like this:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Tuttavia, questo non è **raccomandato** per i progetti reali. La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione. È consigliabile proteggere sempre la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che sia stata compromessa.

Per le applicazioni reali, il modo migliore per mantenere la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile procedere come segue:To fetch the connection string from a configuration file, you can do this:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

L'uso di Gestione configurazione di Azure è facoltativo. È anche possibile usare un'API, ad `ConfigurationManager` esempio il tipo di .NET Framework.You can also use an API such as the .NET Framework's type.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:To parse the connection string, use:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Verrà restituito `CloudStorageAccount`un file .

### <a name="create-the-file-service-client"></a>Creare il client del servizio FileCreate the File service client

Il `CloudFileClient` tipo consente di utilizzare a livello di codice i file archiviati in Archiviazione file. Ecco come creare il client del servizio:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

A questo punto si è pronti per scrivere codice che legge i dati e scrive i dati nell'archivio file.

## <a name="create-a-file-share"></a>Creare una condivisione file

In questo esempio viene illustrato come creare una condivisione file se non esiste già:This example shows how to create a file share if it does not already exist:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Creare una directory radice e una sottodirectory

Qui, si ottiene la directory radice e ottenere una sottodirectory della radice. Entrambi vengono creati se non esistono già.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Caricare testo come file

In questo esempio viene illustrato come caricare testo come file.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Scaricare un file in una copia locale del file

Qui si scarica il file appena creato, aggiungendo il contenuto a un file locale.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Impostare la dimensione massima per una condivisione file

L'esempio seguente illustra come controllare l'uso corrente per una condivisione e come impostare la quota per la condivisione. `FetchAttributes`deve essere chiamato per popolare `Properties`le `SetProperties` modifiche locali all'archiviazione dei file di Azure di una condivisione e per propagare le modifiche locali all'archiviazione dei file di Azure.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generare la firma di accesso condiviso per un file o una condivisione file

È possibile generare una firma di accesso condiviso per una condivisione file o un singolo file. È inoltre possibile creare un criterio di accesso condiviso in una condivisione file per gestire le firme di accesso condiviso. È consigliabile creare un criterio di accesso condiviso, in quanto fornisce un modo per revocare la firma SAS se necessario.

In questo caso, creare un criterio di accesso condiviso in una condivisione e quindi usare tale criterio per fornire i vincoli per una provider di servizi condivisi in un file nella condivisione.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Per altre informazioni sulla creazione e sull'uso di firme di accesso condiviso, vedere [Uso delle firme di accesso condiviso](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) e [Creare e usare una firma di accesso condiviso con l'archiviazione BLOB](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiare i file

È possibile copiare un file in un altro file o in un BLOB o un BLOB in un file. Se si copia un BLOB in un file o un file in un BLOB, è *necessario* usare una firma di accesso condiviso per autenticare l'oggetto di origine, anche se si esegue la copia all'interno dello stesso account di archiviazione.

### <a name="copy-a-file-to-another-file"></a>Copiare un file in un altro file

Qui, si copia un file in un altro file nella stessa condivisione. Poiché questa operazione esegue la copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiare un file in un BLOB

In questo caso, creare un file e copiarlo in un BLOB all'interno dello stesso account di archiviazione. Creare una firma di accesso client per il file di origine, che il servizio utilizza per autenticare l'accesso al file di origine durante l'operazione di copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

È possibile copiare un BLOB in un file nello stesso modo. Se l'oggetto di origine è un BLOB, creare una firma di accesso condiviso per consentire l'accesso al BLOB durante l'operazione di copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Risoluzione dei problemi di Archiviazione file con le metriche

Analisi archiviazione di Azure supporta le metriche per l'archiviazione dei file. Grazie ai dati di metrica, è possibile monitorare le richieste e diagnosticare i problemi.

È possibile abilitare le metriche per l'archiviazione dei file dal portale di [Azure](https://portal.azure.com)oppure eseguire questa operazione da F .

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni sull'archiviazione dei file di Azure, vedere questi collegamenti.

### <a name="conceptual-articles-and-videos"></a>Articoli concettuali e video

- [Archiviazione di file in Azure: un file system SMB nel cloud senza problemi per Windows e Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Come usare l'archiviazione file di Azure con Linux](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Supporto degli strumenti per Archiviazione file

- [Uso di Azure PowerShell con Archiviazione di Azure](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [Come usare AzCopy con Archiviazione di Microsoft Azure](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [Caricare, scaricare ed elencare BLOB con l'interfaccia della riga di comando di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>Riferimento

- [Informazioni di riferimento sulla libreria client di archiviazione per .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Riferimento API REST del servizio File](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Post di BLOG

- [Archiviazione file di Azure è attualmente disponibile a livello generale](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Archiviazione file di AzureInside Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Introduzione al servizio File di Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Mantenimento delle connessioni ai file di Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
