---
title: 'Procedura: Eliminare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 0c8213786b8073d784f1f3ea51417741d5ad4cba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401654"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Procedura: eliminare un file in Visual Basic

Il metodo `DeleteFile` dell'oggetto `My.Computer.FileSystem` consente l'eliminazione di un file. È possibile scegliere di inviare il file eliminato al **Cestino**, chiedere all'utente di confermare l'eliminazione del file e decidere cosa fare quando l'utente annulla l'operazione.  
  
### <a name="to-delete-a-text-file"></a>Per eliminare un file di testo  
  
- Usare il metodo `DeleteFile` per eliminare il file. Il codice seguente illustra come eliminare il file denominato `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Per eliminare un file di testo e chiedere all'utente di confermare l'eliminazione del file  
  
- Usare il metodo `DeleteFile` per eliminare il file, impostando `showUI` su `AllDialogs`. Il codice seguente illustra come eliminare il file denominato `test.txt` e consentire all'utente di confermare l'eliminazione del file.  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Per eliminare un file di testo e inviarlo al Cestino  
  
- Usare il metodo `DeleteFile` per eliminare il file, specificando `SendToRecycleBin` per il parametro `recycle`. Il codice seguente illustra come eliminare il file denominato `test.txt` e inviarlo al **Cestino**.  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
- Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
- Il file è in uso (<xref:System.IO.IOException>).  
  
- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
- Il file non esiste (<xref:System.IO.FileNotFoundException>).  
  
- L'utente non è autorizzato a eliminare il file oppure il file è di sola lettura (<xref:System.UnauthorizedAccessException>).  
  
- Esiste un contesto di attendibilità parziale in cui l'utente non ha autorizzazioni sufficienti (<xref:System.Security.SecurityException>).  
  
- L'utente ha annullato l'operazione e `onUserCancel` è impostato su `ThrowException` (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [Procedura: Ottenere la raccolta di file di una directory](how-to-get-the-collection-of-files-in-a-directory.md)
