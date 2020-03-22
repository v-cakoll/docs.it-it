---
title: 'Procedura: rinominare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: e69dad9ad7f59002ad62b7a06299ff012488e534
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334547"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a>Procedura: rinominare un file in Visual Basic

Usare il metodo `RenameFile` dell'oggetto `My.Computer.FileSystem` per rinominare un file fornendo la posizione corrente, il nome file attuale e il nuovo nome file. Questo metodo non può essere usato per spostare un file. Per spostare e rinominare un file, usare il metodo `MoveFile`.  
  
### <a name="to-rename-a-file"></a>Per rinominare un file  
  
- Usare il metodo `My.Computer.FileSystem.RenameFile`per rinominare un file. In questo esempio il file `Test.txt` viene rinominato in `SecondTest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. Nella casella di selezione dei frammenti di codice il frammento si trova in **File system - Elaborazione di unità, cartelle e file**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
- `newName` contiene informazioni sul percorso (<xref:System.ArgumentException>).  
  
- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
- `newName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>).  
  
- Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).  
  
- Esiste un file o directory con il nome specificato in `newName` (<xref:System.IO.IOException>).  
  
- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
- Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
- L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [Procedura: spostare un file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)
- [Creazione, eliminazione e spostamento di file e directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
- [Procedura: creare una copia di un file nella stessa directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [Procedura: creare una copia di un file in una directory diversa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
