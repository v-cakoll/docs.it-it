---
title: 'Procedura: creare una copia di un file nella stessa directory in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af592e16bb1f7f0bbb188b2ea39394ec1074d302
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a>Procedura: creare una copia di un file nella stessa directory in Visual Basic
Usare il metodo `My.Computer.FileSystem.CopyFile` per copiare i file. I parametri consentono di sovrascrivere file esistenti, rinominare il file, visualizzare lo stato di avanzamento dell'operazione e permettere all'utente di annullare l'operazione.  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a>Per creare una copia di un file nella stessa directory  
  
-   Usare il metodo `CopyFile` specificando il percorso e il file di destinazione. Nell'esempio seguente viene creata una copia di `test2.txt` denominata `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_1.vb)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a>Per creare una copia di un file nella stessa cartella, sovrascrivendo i file esistenti  
  
-   Usare il metodo `CopyFile` specificando il percorso e il file di destinazione e impostando `overwrite` su `True`. Nell'esempio riportato di seguito viene creata una copia di `test.txt` denominata `test2.txt` e i file esistenti vengono sovrascritti con questo nome.  
  
     [!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_2.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le condizioni seguenti possono generare un'eccezione:  
  
-   Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Il sistema non ha recuperato il percorso assoluto (<xref:System.ArgumentException>).  
  
-   Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).  
  
-   Il percorso combinato punta a una directory esistente (<xref:System.IO.IOException>).  
  
-   Il file di destinazione esiste e `overwrite` è impostato su `False` (<xref:System.IO.IOException>).  
  
-   L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).  
  
-   Un file nella cartella di destinazione con lo stesso nome è in uso (<xref:System.IO.IOException>).  
  
-   Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
-   `ShowUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e l'utente ha annullato l'operazione (<xref:System.OperationCanceledException>).  
  
-   `ShowUI`è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e si verifica un errore di I/O non specificato (<xref:System.OperationCanceledException>).  
  
-   La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
-   L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
-   L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>  
 [Procedura: copiare file con un criterio specifico in una directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)  
 [Procedura: creare una copia di un file in una directory diversa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)  
 [Procedura: copiare una directory in un'altra directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)  
 [Procedura: rinominare un file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
