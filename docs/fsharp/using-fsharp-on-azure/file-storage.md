---
title: Iniziare a usare archiviazione File di AzureF#
description: Store i dati dei file nel cloud con archiviazione File di Azure e montare la condivisione file nel cloud da una macchina virtuale di Azure (VM) o da un'applicazione in locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031226"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introduzione all'archiviazione File di Azure con F\#

Archiviazione File di Azure è un servizio che offre condivisioni file nel cloud usando lo standard [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Sono supportati sia SMB 2.1 che SMB 3.0. Con archiviazione File di Azure, è possibile eseguire la migrazione delle applicazioni legacy basate su condivisioni file in Azure velocemente e senza costose riscritture. Le applicazioni in esecuzione in macchine virtuali di Azure o servizi cloud o da client locali possono montare una condivisione file nel cloud, esattamente come un'applicazione desktop Monta una tipica condivisione SMB. Qualsiasi numero di componenti dell'applicazione può quindi montare e accedere contemporaneamente alla condivisione di archiviazione File.

Per una panoramica concettuale dell'archiviazione file, vedi [la Guida di .NET per archiviazione file](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
È necessario anche la chiave di accesso di archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare un F# creare uno Script e avviare F# interattivo

Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script. Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `files.fsx`, nella F# ambiente di sviluppo.

Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva.

### <a name="add-namespace-declarations"></a>Aggiungere le dichiarazioni dello spazio dei nomi

Aggiungere il codice seguente `open` istruzioni all'inizio del `files.fsx` file:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere la stringa di connessione

Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Si tratta tuttavia **sconsigliato** progetti per il real. La chiave dell'account è simile alla password radice per l'account di archiviazione. Prestare sempre attenzione proteggere la chiave dell'account. Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti. È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.

In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Usando Gestione configurazione di Azure è facoltativa. È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Creare il client del servizio File

Il `CloudFileClient` tipo consente di utilizzare a livello di programmazione i file archiviati in archiviazione File. Ecco un modo per creare il client del servizio:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione File.

## <a name="create-a-file-share"></a>Creare una condivisione file

In questo esempio viene illustrato come creare una condivisione file se non esiste già:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Creare una directory radice e una sottodirectory

In questo caso, si ottiene la directory radice e ottenere una sottodirectory della radice. Creare entrambi se non sono già presenti.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Caricare il testo come un file

In questo esempio viene illustrato come caricare un file di testo.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Scaricare un file in una copia locale del file

Qui è scaricare il file appena creato, l'accodamento del contenuto in un file locale.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Impostare le dimensioni massime per una condivisione file

L'esempio seguente viene illustrato come controllare l'utilizzo corrente per una condivisione e come impostare la quota per la condivisione. `FetchAttributes` deve essere chiamato per popolare una condivisione `Properties`, e `SetProperties` per propagare le modifiche locali con archiviazione File di Azure.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generare una firma di accesso condiviso per un file o condivisione file

È possibile generare una firma di accesso condiviso (SAS) per una condivisione file o per un singolo file. È anche possibile creare un criterio di accesso condiviso in una condivisione file per gestire le firme di accesso condiviso. È consigliabile creare un criterio di accesso condiviso, in quanto forniscono un modo per revocare la firma di accesso condiviso se si deve essere compromesso.

In questo caso, si crea un oggetto condiviso in una condivisione di criteri di accesso e quindi usare tale criterio per fornire i vincoli per una firma di accesso condiviso in un file nella condivisione.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Per altre informazioni sulla creazione e uso delle firme di accesso condiviso, vedere [uso di firme di accesso condiviso (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) e [creare e usare una firma di accesso condiviso con l'archiviazione Blob](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiare i file

È possibile copiare un file in un altro file o in un blob o un blob in un file. Se si copia un blob in un file o un file in un blob, si *necessario* usare una firma di accesso condiviso (SAS) per autenticare l'oggetto di origine, anche se si copia nello stesso account di archiviazione.

### <a name="copy-a-file-to-another-file"></a>Copiare un file in un altro file

In questo caso, si copia un file in un altro file nella stessa condivisione. Poiché questa operazione esegue la copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiare un file in un blob

In questo caso, si crea un file e copiarlo in un blob nello stesso account di archiviazione. Si crea una firma di accesso condiviso per il file di origine, il servizio Usa per autenticare l'accesso al file di origine durante l'operazione di copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

È possibile copiare un blob in un file nello stesso modo. Se l'oggetto di origine è un blob, creare una firma di accesso condiviso per autenticare l'accesso al blob durante l'operazione di copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Risoluzione dei problemi di archiviazione di File con le metriche

Analitica di archiviazione di Azure supporta le metriche per archiviazione File. Con i dati delle metriche, è possibile tenere traccia delle richieste e diagnosticare i problemi.

È possibile abilitare le metriche per archiviazione File dal [portale di Azure](https://portal.azure.com), oppure è possibile farlo da F# simile al seguente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Passaggi successivi

Vedere i collegamenti seguenti per altre informazioni sull'archiviazione File di Azure.

### <a name="conceptual-articles-and-videos"></a>Articoli concettuali e video

- [Archiviazione file di Azure: file di SMB nel cloud del sistema per Windows e Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Come usare archiviazione File di Azure con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Supporto degli strumenti per archiviazione File

- [Uso di Azure PowerShell con archiviazione di Azure](/azure/storage/storage-powershell-guide-full)
- [Come usare AzCopy con archiviazione di Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Tramite la CLI di Azure con archiviazione di Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Riferimenti

- [Storage Client Library per .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Riferimento API REST del servizio file](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Post di blog

- [Archiviazione File di Azure è ora disponibile a livello generale](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Inside Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Introduzione a servizio File di Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Mantenimento delle connessioni ai file di Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
