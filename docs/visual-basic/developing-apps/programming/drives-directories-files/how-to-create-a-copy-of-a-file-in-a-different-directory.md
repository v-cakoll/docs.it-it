---
title: 'Procedura: Creare una copia di un file in una directory diversa'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: 3b4b41e105d6bb6a17fbb688aa4718b33c23b9d6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401693"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a>Procedura: creare una copia di un file in una directory diversa in Visual Basic

Il metodo `My.Computer.FileSystem.CopyFile` consente di copiare i file. I sui parametri consentono di sovrascrivere file esistenti, rinominare il file, visualizzare lo stato di avanzamento dell'operazione e consentire all'utente di annullare l'operazione.  
  
### <a name="to-copy-a-text-file-to-another-folder"></a>Per copiare un file di testo in un'altra cartella  
  
- Usare il metodo `CopyFile` per copiare un file, specificando il file di origine e la directory di destinazione. Il parametro `overwrite` consente di specificare se sovrascrivere o meno i file esistenti. Negli esempi di codice seguenti viene illustrato l'uso di `CopyFile`.  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le condizioni seguenti possono generare un'eccezione:  
  
- Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
- Il sistema non ha recuperato il percorso assoluto (<xref:System.ArgumentException>).  
  
- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
- Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).  
  
- Il percorso combinato punta a una directory esistente (<xref:System.IO.IOException>).  
  
- Il file di destinazione esiste e `overwrite` è impostato su `False` (<xref:System.IO.IOException>).  
  
- L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).  
  
- Un file nella cartella di destinazione con lo stesso nome è in uso (<xref:System.IO.IOException>).  
  
- Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
- `ShowUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e l'utente ha annullato l'operazione (<xref:System.OperationCanceledException>).  
  
- `ShowUI`è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e si verifica un errore di I/O non specificato (<xref:System.OperationCanceledException>).  
  
- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
- L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [Procedura: Copiare file con un criterio specifico in una directory](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [Procedura: Creare una copia di un file nella stessa directory](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [Procedura: Copiare una directory in un'altra directory](how-to-copy-a-directory-to-another-directory.md)
- [Procedura: Rinominare un file](how-to-rename-a-file.md)
