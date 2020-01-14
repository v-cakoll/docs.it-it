---
title: Introduzione all'archiviazione file di Azure con F#
description: Archiviare i dati dei file nel cloud con Archiviazione file di Azure e montare la condivisione di file nel cloud da una macchina virtuale Azure (VM) o da un'applicazione locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: d58417e1e3161b958754e01423136a9cdd6a08a6
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935622"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introduzione ad archiviazione file di Azure con F\#

Archiviazione file di Azure offre condivisioni file nel cloud usando il [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)standard. Sono supportati sia SMB 2.1 che SMB 3.0. Con Archiviazione file di Azure si può eseguire la migrazione ad Azure delle applicazioni legacy basate su condivisioni file velocemente e senza costose riscritture. Le applicazioni in esecuzione in macchine virtuali di Azure o in servizi cloud oppure in client locali possono montare una condivisione file nel cloud, esattamente come un'applicazione desktop monta una tipica condivisione SMB. Non ci sono limiti per i componenti delle applicazioni che possono montare e accedere contemporaneamente alla condivisione di archiviazione file.

Per una panoramica concettuale dell'archiviazione file, vedere [la Guida di .NET per l'archiviazione di file](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Prerequisiti

Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).
Sarà necessaria anche la chiave di accesso alle archiviazione per questo account.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creare uno F# script e avviare F# interattivo

Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script. Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `files.fsx`, nell'ambiente F# di sviluppo.

Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto di `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`.

### <a name="add-namespace-declarations"></a>Aggiungere dichiarazioni di spazi dei nomi

Aggiungere le istruzioni `open` seguenti all'inizio del file `files.fsx`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Ottenere una stringa di connessione

Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure. Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).

Per l'esercitazione, immettere la stringa di connessione nello script, come segue:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Questa operazione non è tuttavia **consigliata** per i progetti reali. La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione. È consigliabile proteggere sempre la chiave dell'account di archiviazione. Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri. È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.

Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione. Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

L'uso di Gestione configurazione di Azure è facoltativo. È anche possibile usare un'API, ad esempio il tipo di `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizzare la stringa di connessione

Per analizzare la stringa di connessione, usare:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Verrà restituito un `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Creare il client del servizio file

Il tipo di `CloudFileClient` consente di usare i file archiviati nell'archiviazione file a livello di codice. Ecco come creare il client del servizio:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

A questo punto si è pronti per scrivere codice che legge i dati e scrive i dati nell'archiviazione file.

## <a name="create-a-file-share"></a>Creare una condivisione file

Questo esempio illustra come creare una condivisione file, se non esiste già:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Creare una directory radice e una sottodirectory

Qui è possibile ottenere la directory radice e ottenere una sottodirectory della radice. Verranno creati entrambi se non sono già presenti.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Carica testo come file

Questo esempio illustra come caricare il testo come file.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Scaricare un file in una copia locale del file

Qui è possibile scaricare il file appena creato, aggiungendo il contenuto a un file locale.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Impostare la dimensione massima per una condivisione file

L'esempio seguente illustra come controllare l'uso corrente per una condivisione e come impostare la quota per la condivisione. è necessario chiamare `FetchAttributes` per popolare `Properties`della condivisione e `SetProperties` per propagare le modifiche locali all'archiviazione file di Azure.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generare la firma di accesso condiviso per un file o una condivisione file

È possibile generare una firma di accesso condiviso per una condivisione file o un singolo file. È inoltre possibile creare un criterio di accesso condiviso in una condivisione file per gestire le firme di accesso condiviso. È consigliabile creare un criterio di accesso condiviso, in quanto fornisce un modo per revocare la firma SAS se necessario.

Qui è possibile creare un criterio di accesso condiviso in una condivisione e quindi usare tale criterio per fornire i vincoli per una firma di accesso condiviso in un file nella condivisione.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Per altre informazioni sulla creazione e sull'uso di firme di accesso condiviso, vedere [Uso delle firme di accesso condiviso](/azure/storage/storage-dotnet-shared-access-signature-part-1) e [Creare e usare una firma di accesso condiviso con l'archiviazione BLOB](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiare i file

È possibile copiare un file in un altro file o in un BLOB o in un BLOB in un file. Se si copia un BLOB in un file o un file in un BLOB, è *necessario* usare una firma di accesso condiviso (SAS) per autenticare l'oggetto di origine, anche se si esegue la copia nello stesso account di archiviazione.

### <a name="copy-a-file-to-another-file"></a>Copiare un file in un altro file

Qui viene copiato un file in un altro file nella stessa condivisione. Poiché questa operazione esegue la copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiare un file in un BLOB

Qui è possibile creare un file e copiarlo in un BLOB nello stesso account di archiviazione. Si crea una firma di accesso condiviso per il file di origine, che il servizio usa per autenticare l'accesso al file di origine durante l'operazione di copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

È possibile copiare un BLOB in un file nello stesso modo. Se l'oggetto di origine è un BLOB, creare una firma di accesso condiviso per consentire l'accesso al BLOB durante l'operazione di copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Risoluzione dei problemi di Archiviazione file con le metriche

Analisi archiviazione di Azure supporta le metriche per l'archiviazione di file. Grazie ai dati di metrica, è possibile monitorare le richieste e diagnosticare i problemi.

È possibile abilitare le metriche per l'archiviazione file dal [portale di Azure](https://portal.azure.com)oppure è possibile eseguire questa operazione F# da come segue:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Passaggi successivi

Vedere i collegamenti seguenti per ulteriori informazioni sull'archiviazione file di Azure.

### <a name="conceptual-articles-and-videos"></a>Articoli concettuali e video

- [Archiviazione di file in Azure: un file system SMB nel cloud senza problemi per Windows e Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Come usare Archiviazione file di Azure con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Supporto degli strumenti per Archiviazione file

- [Uso di Azure PowerShell con Archiviazione di Azure](/azure/storage/storage-powershell-guide-full)
- [Come usare AzCopy con Archiviazione di Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Uso dell'interfaccia della riga di comando di Azure con Archiviazione di Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Riferimenti

- [Informazioni di riferimento sulla libreria client di archiviazione per .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Riferimento API REST del servizio File](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Post di blog

- [Archiviazione file di Azure è attualmente disponibile a livello generale](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Analisi di archiviazione file di Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Introduzione al servizio File di Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Mantenimento delle connessioni ai file di Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
