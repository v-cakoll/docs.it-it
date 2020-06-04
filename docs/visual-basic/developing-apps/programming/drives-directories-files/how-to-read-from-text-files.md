---
title: 'Procedura: Leggere da file di testo'
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 0d99209ed123686355e8d49c82ba23f94084f895
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411616"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Procedura: leggere da file di testo in Visual Basic

Il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> dell'oggetto `My.Computer.FileSystem` consente la lettura di un file di testo. È possibile specificare la codifica file se il contenuto del file utilizza, ad esempio, la codifica ASCII o UTF-8.

Se la lettura è eseguita da un file contenente caratteri estesi, è necessario specificare la codifica del file.

> [!NOTE]
> Per leggere un file una riga di testo alla volta, utilizzare il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> dell'oggetto `My.Computer.FileSystem`. Il metodo `OpenTextFileReader` restituisce un oggetto <xref:System.IO.StreamReader>. È possibile utilizzare il metodo <xref:System.IO.StreamReader.ReadLine%2A> dell'oggetto `StreamReader` per leggere un file una riga alla volta. È possibile eseguire il test della fine del file utilizzando il metodo <xref:System.IO.StreamReader.EndOfStream%2A> dell'oggetto `StreamReader`.

## <a name="to-read-from-a-text-file"></a>Per leggere da un file di testo

Utilizzare il metodo `ReadAllText` dell'oggetto `My.Computer.FileSystem` per leggere il contenuto di un file di testo in una stringa, specificando il percorso. Nell'esempio seguente viene letto il contenuto del file test.txt in una stringa e quindi tale contenuto viene visualizzato in una finestra di messaggio.

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a>Per leggere da un file di testo codificato

Utilizzare il metodo `ReadAllText` dell'oggetto `My.Computer.FileSystem` per leggere il contenuto di un file di testo in una stringa, specificando il percorso e il tipo di codifica file. Nell'esempio seguente viene letto il contenuto del file test.txt UTF32 in una stringa e quindi tale contenuto viene visualizzato in una finestra di messaggio.

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a>Programmazione efficiente

Le seguenti condizioni possono generare un'eccezione:

- Il percorso non è valido per uno dei seguenti motivi: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di una periferica (<xref:System.ArgumentException>).

- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).

- Il file non esiste (<xref:System.IO.FileNotFoundException>).

- Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).

- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).

- Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).

- La memoria disponibile non è sufficiente per la scrittura della stringa nel buffer (<xref:System.OutOfMemoryException>).

- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).

Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.

Prima di usare i dati nell'applicazione verificare tutti gli input. È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [Lettura da file](reading-from-files.md)
- [Procedura: Leggere da file di testo con valori delimitati da virgole](how-to-read-from-comma-delimited-text-files.md)
- [Procedura: Leggere da file di testo a larghezza fissa](how-to-read-from-fixed-width-text-files.md)
- [Procedura: Leggere da file di testo con più formati](how-to-read-from-text-files-with-multiple-formats.md)
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Procedura dettagliata: Modifica di file e directory in Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Codifiche dei file](file-encodings.md)
