---
title: Gestione degli errori di I/O in .NET
ms.date: 08/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, exception handling
- I/O, errors
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c592039b3b12eedcfceda45c2f54403a8e04b5d5
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242673"
---
# <a name="handling-io-errors-in-net"></a>Gestione degli errori di I/O in .NET

Oltre alle eccezioni che possono essere generate in qualsiasi chiamata a un metodo (ad esempio, <xref:System.OutOfMemoryException> quando un sistema è in sovraccarico o <xref:System.NullReferenceException> a causa di un errore del programmatore), i metodi del file system .NET possono generare le eccezioni seguenti:

- <xref:System.IO.IOException?displayProperty=nameWithType>, la classe di base di tutti i tipi di eccezioni <xref:System.IO>. Viene generata per gli errori i cui codici restituiti dal sistema operativo non eseguono il mapping diretto a nessun altro tipo di eccezione.
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DriveNotFoundException??displayProperty=nameWithType>.
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType>.
- <xref:System.OperationCanceledException?displayProperty=nameWithType>.
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType>.
- <xref:System.ArgumentException?displayProperty=nameWithType>, generata per i caratteri non validi nel percorso in .NET Framework e in .NET Core 2.0 e versioni precedenti.
- <xref:System.NotSupportedException?displayProperty=nameWithType>, generata per i caratteri due punti non validi in .NET Framework.
- <xref:System.Security.SecurityException?displayProperty=nameWithType>, generata per le applicazioni in esecuzione con attendibilità limitata senza le autorizzazioni necessarie solo in .NET Framework. L'attendibilità totale è l'impostazione predefinita in .NET Framework.

## <a name="mapping-error-codes-to-exceptions"></a>Mapping dei codici di errore alle eccezioni

Poiché il file system è una risorsa del sistema operativo, i metodi di I/O sia in .NET Core che in .NET eseguono il wrapping delle chiamate nel sistema operativo sottostante. Quando si verifica un errore di I/O nel codice eseguito dal sistema operativo, il sistema operativo restituisce le informazioni sull'errore al metodo di I/O di .NET. Il metodo converte quindi le informazioni sull'errore, in genere in formato codice di errore, in un tipo di eccezione .NET. Nella maggior parte dei casi, esegue questa operazione convertendo direttamente il codice di errore nel tipo di eccezione corrispondente, senza eseguire mapping specifici dell'errore basati sul contesto della chiamata al metodo.

Nel sistema operativo Windows, ad esempio, una chiamata a un metodo che restituisce un codice di errore `ERROR_FILE_NOT_FOUND` (o 0x02) esegue il mapping a <xref:System.IO.FileNotFoundException> e un codice di errore `ERROR_PATH_NOT_FOUND` (o 0x03) esegue il mapping a <xref:System.IO.DirectoryNotFoundException>.

Tuttavia, le condizioni esatte in cui il sistema operativo restituisce determinati codici di errore spesso sono poco o per nulla documentate. Possono quindi verificarsi eccezioni impreviste. Poiché ad esempio si usa una directory invece di un file, se si fornisse un percorso di directory non valido al costruttore <xref:System.IO.DirectoryInfo.%23ctor%2A>, dovrebbe essere generata un'eccezione <xref:System.IO.DirectoryNotFoundException>, ma potrebbe anche venire generata un'eccezione <xref:System.IO.FileNotFoundException>.

## <a name="exception-handling-in-io-operations"></a>Gestione delle eccezioni nelle operazioni di I/O

A causa di questa dipendenza dal sistema operativo, con condizioni di eccezione identiche (come l'errore di directory non trovata dell'esempio) un metodo di I/O può generare una qualsiasi tra tutte le eccezioni di I/O della classe. Pertanto, quando si chiamano le API di I/O, il codice deve essere preparato per gestire tutte o quasi tutte le eccezioni, come illustrato nella tabella seguente:

| Tipo di eccezione | .NET Core | .NET Framework |
|---|---|---|
| <xref:System.IO.IOException> | Sì | Sì |
| <xref:System.IO.FileNotFoundException> | Sì | Sì |
| <xref:System.IO.DirectoryNotFoundException> | Sì | Sì |
| <xref:System.IO.DriveNotFoundException?> | Sì | Sì |
| <xref:System.IO.PathTooLongException> | Sì | Sì |
| <xref:System.OperationCanceledException> | Sì | Sì |
| <xref:System.UnauthorizedAccessException> | Sì | Sì |
| <xref:System.ArgumentException> | .NET Core 2.0 e versioni precedenti| Sì |
| <xref:System.NotSupportedException> | No | Sì |
| <xref:System.Security.SecurityException> | No | Solo attendibilità limitata |

## <a name="handling-ioexception"></a>Gestione di IOException

In quanto classe di base per le eccezioni nello spazio dei nomi <xref:System.IO>, viene generata un'eccezione <xref:System.IO.IOException> anche per i codici di errore che non eseguono il mapping a un tipo di eccezione predefinito. Può essere quindi generata da qualsiasi operazione di I/O.

> [!IMPORTANT]
> Poiché <xref:System.IO.IOException> è la classe di base degli altri tipi di eccezioni nello spazio dei nomi <xref:System.IO>, è consigliabile gestire un blocco `catch` dopo aver gestito le altre eccezioni relative alle operazioni di I/O.

Inoltre, a partire da .NET Core 2.1, i controlli di convalida della correttezza del percorso (ad esempio, per assicurarsi che in un percorso non siano presenti caratteri non validi) sono stati rimossi e il runtime genera un'eccezione di cui viene eseguito il mapping da un codice di errore del sistema operativo invece che dal proprio codice di convalida. In questo caso l'eccezione che viene generata con maggior probabilità è <xref:System.IO.IOException>, ma potrebbe essere generato qualsiasi altro tipo di eccezione.

Si noti che nel codice di gestione dell'eccezione, si dovrà gestire sempre per ultima <xref:System.IO.IOException>. In caso contrario, poiché si tratta della classe di base di tutte le altre eccezioni di I/O, i blocchi catch di classi derivate non verranno valutati.

Nel caso di <xref:System.IO.IOException>, è possibile ottenere altre informazioni sull'errore dalla proprietà [IOException.HResult](xref:System.Exception.HResult). Per convertire il valore HResult in un codice di errore Win32, si rimuovono i 16 bit superiori del valore da 32 bit. La tabella seguente elenca i codici di errore di cui potrebbe essere eseguito il wrapping in un'eccezione <xref:System.IO.IOException>.

| HResult | Costante | Description |
| --- | --- | --- |
| ERROR_SHARING_VIOLATION | 32 | Il nome del file è mancante oppure il file o la directory è in uso. |
| ERROR_FILE_EXISTS | 80 | File già esistente. |
| ERROR_INVALID_PARAMETER | 87 | Un argomento fornito al metodo non è valido. |
| ERROR_ALREADY_EXISTS | 183 | File o directory già esistente. |

È possibile gestirli usando una clausola `When` in un'istruzione catch, come illustrato nell'esempio seguente.

[!code-csharp[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/cs/io-exceptions.cs)]
[!code-vb[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/vb/io-exceptions.vb)]

## <a name="see-also"></a>Vedere anche

- [Gestione e generazione di eccezioni in .NET](../exceptions/index.md)
- [Gestione delle eccezioni (Task Parallel Library)](../parallel-programming/exception-handling-task-parallel-library.md)
- [Procedure consigliate per le eccezioni](../exceptions/best-practices-for-exceptions.md)
- [Come usare eccezioni specifiche in un blocco catch](../exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)
