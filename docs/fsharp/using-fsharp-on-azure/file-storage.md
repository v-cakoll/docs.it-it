---
title: "Introduzione all'archiviazione di File di Azure con F #"
description: Archiviare i dati del file nel cloud con l'archiviazione di File di Azure e montare la condivisione di file cloud da una macchina virtuale di Azure (VM) o da un'applicazione locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: e772da5f81d2e6827295d0dfe150934a415eb3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introduzione all'archiviazione di File di Azure con F # #

Archiviazione di File di Azure è un servizio che offre le condivisioni file nel cloud utilizzando lo standard [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). SMB 2.1 sia SMB 3.0 sono supportati. Con l'archiviazione di File di Azure, è possibile eseguire la migrazione di applicazioni legacy che si basano su condivisioni file in Azure rapidamente e senza costose. Le applicazioni in esecuzione in macchine virtuali di Azure o i servizi cloud o da client locali è possono montare una condivisione di file nel cloud, come un'applicazione desktop Monta una condivisione SMB tipico. Qualsiasi numero di componenti dell'applicazione può quindi montare e accedere alla condivisione di archiviazione di File contemporaneamente.

Per una panoramica concettuale di archiviazione di file, vedere [la Guida di .NET per l'archiviazione di file](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Per questo account, è necessario anche la chiave di accesso di archiviazione.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un Script F # e avvio di F # Interactive

Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #. Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `files.fsx`, nell'ambiente di sviluppo F #.

Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il seguente `open` istruzioni all'inizio di `files.fsx` file:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Si tratta tuttavia **non è consigliabile** di progetti. La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave di account di archiviazione. Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Utilizzando Gestione configurazione di Azure è facoltativa. È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, utilizzare:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Creare il client del servizio File

Il `CloudFileClient` tipo consente di utilizzare i file memorizzati nell'archiviazione di File a livello di codice. Ecco un modo per creare il client del servizio:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati in archiviazione di File.

## <a name="create-a-file-share"></a>Creare una condivisione file

In questo esempio viene illustrato come creare una condivisione file, se non esiste già:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Creare una directory radice e una sottodirectory

In questo caso, ottenere la directory radice e ottenere una sottodirectory della directory principale. Creare entrambi se non sono già presenti.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Caricare il testo come un file

In questo esempio viene illustrato come caricare un file di testo.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Scaricare una copia locale del file di un file

Qui scaricare il file appena creato, aggiungendo il contenuto in un file locale.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Impostare la dimensione massima per una condivisione file

Nell'esempio seguente viene illustrato come controllare l'utilizzo corrente per una condivisione e come impostare la quota per la condivisione. `FetchAttributes` deve essere chiamato per popolare una condivisione `Properties`, e `SetProperties` per propagare le modifiche locali per l'archiviazione di File di Azure.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generare una firma di accesso condiviso per un file o una condivisione file

È possibile generare una firma di accesso condiviso (SAS) per una condivisione file o per un singolo file. È anche possibile creare un criterio di accesso condiviso in una condivisione di file per gestire le firme di accesso condiviso. È consigliabile creare un criterio di accesso condiviso, in quanto forniscono un mezzo per revocare la firma di accesso condiviso, se questa deve essere compromessa.

In questo caso, si crea un oggetto condiviso criteri in una condivisione di accessi e quindi utilizzare tale criterio per fornire i vincoli per una firma di accesso condiviso in un file nella condivisione.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Per ulteriori informazioni sulla creazione e utilizzo di firme di accesso condiviso, vedere [utilizzando di firme di accesso condiviso (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) e [creare e usare una firma di accesso condiviso all'archiviazione Blob](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiare i file

È possibile copiare un file in un altro file o in un blob o un blob in un file. Se si copia un blob in un file o un file in un blob, è *deve* utilizzare una firma di accesso condiviso (SAS) per autenticare l'oggetto di origine, anche se si copia nello stesso account di archiviazione.

### <a name="copy-a-file-to-another-file"></a>Copiare un file in un altro file

In questo caso, si copia un file in un altro file nella stessa condivisione. Poiché questa operazione di copia copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copia un file in un blob

In questo caso, si crea un file e copiarlo in un blob nello stesso account di archiviazione. Creare una firma di accesso condiviso per il file di origine, il servizio utilizza per autenticare l'accesso al file di origine durante l'operazione di copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

È possibile copiare un blob in un file nello stesso modo. Se l'oggetto di origine è un blob, creare una firma di accesso condiviso per autenticare l'accesso ai blob durante l'operazione di copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Risoluzione dei problemi utilizzando la metrica di archiviazione di File

Analitica di archiviazione Azure supporta le metriche per l'archiviazione di File. Dati di metrica, è possibile tenere traccia delle richieste e diagnosticare i problemi.

È possibile abilitare la metrica per l'archiviazione di File dal [portale Azure](https://portal.azure.com), oppure è possibile farlo da F # simile al seguente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Passaggi successivi

Vedere i collegamenti per ulteriori informazioni sull'archiviazione di File di Azure.

### <a name="conceptual-articles-and-videos"></a>Video e articoli concettuali

- [File di archiviazione Azure: una disposizione cloud SMB file system per Windows e Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Come usare l'archiviazione di File di Azure con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Gli strumenti di supporto per l'archiviazione di File

- [Uso di Azure PowerShell con l'archiviazione di Azure](/azure/storage/storage-powershell-guide-full)
- [Come usare AzCopy con archiviazione di Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Tramite l'interfaccia CLI di Azure con l'archiviazione di Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Riferimenti

- [Libreria Client di archiviazione per il riferimento di .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Riferimento API REST di servizi file](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Post di blog

- [Archiviazione di File di Azure è disponibile](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Archiviazione di File all'interno di Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Introduzione a servizi di File di Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Connessioni persistenti al file di Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
