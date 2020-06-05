---
title: 'Procedura: Spostare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
ms.openlocfilehash: 2dafeb3b5f8b8c3a8976b25c1a57f405aebb32b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401602"
---
# <a name="how-to-move-a-file-in-visual-basic"></a>Procedura: spostare un file in Visual Basic

Il metodo `My.Computer.FileSystem.MoveFile` consente di spostare un file in una cartella diversa. Se la struttura di destinazione non esiste, verrà creata.  
  
### <a name="to-move-a-file"></a>Per spostare un file  
  
- Per spostare il file, usare il metodo `MoveFile` , specificando il nome e il percorso del file di origine e del file di destinazione. In questo esempio il file `test.txt` viene spostato da `TestDir1` a `TestDir2`. Si noti che il nome del file di destinazione viene specificato anche se corrisponde al nome del file di origine.  
  
     [!code-vb[VbVbcnMyFileSystem#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#24)]  
  
### <a name="to-move-a-file-and-rename-it"></a>Per spostare un file e rinominarlo  
  
- Per spostare il file, usare il metodo `MoveFile` , specificando il nome e il percorso del file di origine, il percorso di destinazione e il nome che si desidera assegnare al file di destinazione. In questo esempio il file `test.txt` viene spostato da `TestDir1` a `TestDir2` e viene rinominato `nexttest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#25)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
- `destinationFileName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>).  
  
- Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).  
  
- Il percorso complessivo corrisponde a una directory esistente, il file di destinazione esiste e `overwrite` è impostato su `False`, un file con lo stesso nome è già in uso nella directory di destinazione oppure l'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).  
  
- Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
- `showUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException`e l'utente ha annullato l'operazione oppure si è verificato un errore di I/O non specificato (<xref:System.OperationCanceledException>).  
  
- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
- L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>
- [Procedura: Rinominare un file](how-to-rename-a-file.md)
- [Procedura: Creare una copia di un file in una directory diversa](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [Procedura: Analizzare percorsi di file](how-to-parse-file-paths.md)
