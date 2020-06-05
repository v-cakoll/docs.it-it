---
title: Nozioni fondamentali sul file system e sulla funzionalità di I/O di file di di .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- file access, file I/O in Visual Basic
- file attributes, determining
- streams, fundamental operations
- file permissions
- streams
- streams, definition
ms.assetid: 49d837c0-cf28-416f-8606-4d83d7b479ef
ms.openlocfilehash: 187a20617ec901e722a30ebfa571e4a55ed0b5c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401797"
---
# <a name="basics-of-net-framework-file-io-and-the-file-system-visual-basic"></a>Nozioni fondamentali sul file system e sulla funzionalità di I/O di file di .NET Framework (Visual Basic)

Le classi dello spazio dei nomi <xref:System.IO> si usano per lavorare con unità, file e directory.

Lo spazio dei nomi <xref:System.IO> contiene le classi <xref:System.IO.File> e <xref:System.IO.Directory> che offrono la funzionalità .NET Framework per la gestione di file e directory. Poiché i metodi di questi oggetti sono membri statici o condivisi, è possibile usarli direttamente senza prima creare un'istanza della classe. Associate a queste classi sono le classi <xref:System.IO.FileInfo> e <xref:System.IO.DirectoryInfo> che saranno note agli utenti della funzionalità `My`. Per usare queste classi è necessario specificare in modo completo i nomi oppure importare gli spazi dei nomi appropriati, includendo le istruzioni `Imports` all'inizio del codice in questione. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).

> [!NOTE]
> Altri argomenti di questa sezione usano l'oggetto `My.Computer.FileSystem` anziché le classi `System.IO` per lavorare con unità, file e directory. L'oggetto `My.Computer.FileSystem` è destinato principalmente all'uso nei programmi Visual Basic. Le classi `System.IO` sono destinate all'uso da parte di qualsiasi linguaggio che supporta .NET Framework, incluso Visual Basic.

## <a name="definition-of-a-stream"></a>Definizione di un flusso

.NET Framework usa i flussi per supportare la lettura e scrittura su file. Un flusso è paragonabile a un set unidimensionale di dati contigui, con un inizio e una fine, e in cui il cursore indica la posizione corrente nel flusso.

![Il cursore mostra la posizione corrente all'interno del flusso dei file](./media/basics-of-net-framework-file-io-and-the-file-system/filestream-cursor-position.gif)

## <a name="stream-operations"></a>Operazioni di flusso

I dati contenuti nel flusso possono provenire dalla memoria, da un file o da un socket TCP/IP. Ai flussi è possibile applicare alcune operazioni fondamentali:

- **Lettura**in corso. È possibile leggere da un flusso, trasferendo i dati dal flusso in una struttura di dati, ad esempio una stringa o una matrice di byte.

- **Scrittura**. È possibile scrivere in un flusso, trasferendo i dati da un'origine dati nel flusso.

- **Ricerca**. È possibile eseguire una query e modificare la propria posizione nel flusso.

Per altre informazioni, vedere [Composing Streams](../../../../standard/io/composing-streams.md).

## <a name="types-of-streams"></a>Tipi di flussi

In .NET Framework un flusso è rappresentato dalla classe <xref:System.IO.Stream> che costituisce la classe astratta per tutti gli altri flussi. Non è possibile creare direttamente un'istanza della classe <xref:System.IO.Stream> ma è necessario usare una delle classi che essa implementa.

Esistono molti tipi di flussi, ma per lavorare con l'input/output (I/O) su file, i tipi più importanti sono la classe <xref:System.IO.FileStream>, che fornisce un modo per leggere e scrivere sui file, e la classe <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>, che consente di creare file e directory in uno spazio di memorizzazione isolato. Altri flussi che possono essere usati quando si lavora con l'I/O su file includono:

- <xref:System.IO.BufferedStream>

- <xref:System.Security.Cryptography.CryptoStream>

- <xref:System.IO.MemoryStream>

- <xref:System.Net.Sockets.NetworkStream>.

La tabella seguente elenca le attività comunemente eseguite con un flusso:

|A|Vedere|
|---|---|
|Leggere e scrivere in un file di dati|[Procedura: Leggere e scrivere in un file di dati appena creato](../../../../standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|
|Leggere testo da un file|[Procedura: Leggere testo da un file](../../../../standard/io/how-to-read-text-from-a-file.md)|
|Scrivere testo in un file|[Procedura: Scrivere testo in un file](../../../../standard/io/how-to-write-text-to-a-file.md)|
|Leggere caratteri da una stringa|[Procedura: Leggere caratteri da una stringa](../../../../standard/io/how-to-read-characters-from-a-string.md)|
|Scrivere caratteri in una stringa|[Procedura: Scrivere caratteri in una stringa](../../../../standard/io/how-to-write-characters-to-a-string.md)|
|Crittografare i dati|[Encrypting Data](../../../../standard/security/encrypting-data.md)|
|Decrittografare i dati|[Decrittografia di dati](../../../../standard/security/decrypting-data.md)|

## <a name="file-access-and-attributes"></a>Accesso ai file e attributi

È possibile controllare come i file vengono creati, aperti e condivisi con le enumerazioni <xref:System.IO.FileAccess>, <xref:System.IO.FileMode> e <xref:System.IO.FileShare>, che contengono i flag utilizzati dai costruttori della classe <xref:System.IO.FileStream>. Ad esempio, quando si apre o si crea un nuovo <xref:System.IO.FileStream>, l'enumerazione <xref:System.IO.FileMode> consente di specificare se il file viene aperto per operazioni di accodamento, se viene creato un nuovo file quando il file specificato non esiste, se il file viene sovrascritto e così via.

L'enumerazione <xref:System.IO.FileAttributes> consente la raccolta di informazioni specifiche del file. L'enumerazione <xref:System.IO.FileAttributes> restituisce gli attributi del file archiviato, ad esempio se è compresso, crittografato, nascosto, in sola lettura, un archivio, una directory, un file di sistema o un file temporaneo.

La tabella seguente elenca le attività che coinvolgono l'accesso ai file e gli attributi di file:

|A|Vedere|
|---|---|
|Aprire e accodare testo in un file di log|[Procedura: Aprire e accodare un file di log](../../../../standard/io/how-to-open-and-append-to-a-log-file.md)|
|Determinare gli attributi di un file|<xref:System.IO.FileAttributes>|

## <a name="file-permissions"></a>Autorizzazioni dei file

Il controllo dell'accesso ai file e alle directory può essere eseguito con la classe <xref:System.Security.Permissions.FileIOPermission>. Questo può essere particolarmente importante per gli sviluppatori che lavorano con i Web Form che, per impostazione predefinita, vengono eseguiti nel contesto di un account utente locale speciale denominato ASPNET, che viene creato come parte delle installazioni di ASP.NET e .NET Framework. Quando una tale applicazione richiede l'accesso a una risorsa, l'account utente ASPNET dispone di autorizzazioni limitate, che potrebbero impedire all'utente di eseguire azioni quali la scrittura in un file da un'applicazione Web. Per altre informazioni, vedere <xref:System.Security.Permissions.FileIOPermission>.

## <a name="isolated-file-storage"></a>Archiviazione di file isolati

Lo spazio di archiviazione isolato è un tentativo di risolvere i problemi creati durante l'uso dei file in cui l'utente o il codice non dispone delle autorizzazioni necessarie. Lo spazio di archiviazione isolato assegna a ciascun utente un raggruppamento di dati che può contenere uno o più archivi. Gli archivi possono essere isolati gli uni dagli altri per utente e per assembly. Solo l'utente e l'assembly che ha creato l'archivio può accedervi. Un archivio opera come un file system virtuale completo: all'interno di un archivio è possibile creare e modificare directory e file.

La tabella seguente elenca le attività comunemente associate all'archiviazione di file isolati.

|A|Vedere|
|---|---|
|Creare un spazio di memorizzazione isolato|[Procedura: Recuperare archivi per lo spazio di memorizzazione isolato](../../../../standard/io/how-to-obtain-stores-for-isolated-storage.md)|
|Enumerare gli spazi di memorizzazione isolati|[Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato](../../../../standard/io/how-to-enumerate-stores-for-isolated-storage.md)|
|Eliminare un spazio di memorizzazione isolato|[Procedura: Eliminare gli archivi nello spazio di memorizzazione isolato](../../../../standard/io/how-to-delete-stores-in-isolated-storage.md)|
|Creare un file o una directory in un spazio di memorizzazione isolato|[Procedura: Creare file e directory nello spazio di memorizzazione isolato](../../../../standard/io/how-to-create-files-and-directories-in-isolated-storage.md)|
|Trovare un file in un spazio di memorizzazione isolato|[Procedura: Trovare file e directory esistenti nello spazio di memorizzazione isolato](../../../../standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)|
|Leggere o scrivere in un file in un spazio di memorizzazione isolato|[Procedura: Leggere e scrivere sui file nello spazio di memorizzazione isolato](../../../../standard/io/how-to-read-and-write-to-files-in-isolated-storage.md)|
|Eliminare un file o una directory in un spazio di memorizzazione isolato|[Procedura: Eliminare file e directory nello spazio di memorizzazione isolato](../../../../standard/io/how-to-delete-files-and-directories-in-isolated-storage.md)|

## <a name="file-events"></a>Eventi di file

Il componente <xref:System.IO.FileSystemWatcher> consente di controllare le modifiche nei file e nelle directory del sistema o in qualsiasi computer a cui si ha accesso dalla rete. Ad esempio, se un file viene modificato, è consigliabile inviare all'utente un avviso che la modifica ha avuto luogo. Quando vengono apportate modifiche, vengono generati uno o più eventi, che vengono archiviati in un buffer e consegnati al componente <xref:System.IO.FileSystemWatcher> per l'elaborazione.

## <a name="see-also"></a>Vedere anche

- [Composizione dei flussi](../../../../standard/io/composing-streams.md)
- [I/O di file e di flussi](../../../../standard/io/index.md)
- [I/O file asincrono](../../../../standard/io/asynchronous-file-i-o.md)
- [Classi utilizzate nel file system e nella funzionalità di I/O di file di .Net Framework (Visual Basic)](classes-used-in-net-framework-file-io-and-the-file-system.md)
