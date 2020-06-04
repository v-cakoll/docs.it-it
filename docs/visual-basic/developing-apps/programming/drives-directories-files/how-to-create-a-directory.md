---
title: 'Procedura: Creare una directory'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 0da915054a2e38c778f15bc0b472fe9b02521189
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401667"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a>Procedura: creare una directory in Visual Basic

Usare il metodo `CreateDirectory` dell'oggetto `My.Computer.FileSystem` per la creazione di directory.  
  
 Se la directory esiste già, non verranno generate eccezioni.  
  
### <a name="to-create-a-directory"></a>Per creare una directory  
  
- Usare il metodo `CreateDirectory` specificando il percorso completo della posizione in cui deve essere creata la directory. Nell'esempio riportato di seguito la directory `NewDirectory` viene creata in `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Il nome della directory non è valido. Contiene ad esempio caratteri non validi o è costituito solo da uno spazio (<xref:System.ArgumentException>).  
  
- La directory padre della directory da creare è di sola lettura (<xref:System.IO.IOException>).  
  
- Il nome della directory è `Nothing` (<xref:System.ArgumentNullException>).  
  
- Il nome della directory è troppo lungo (<xref:System.IO.PathTooLongException>).  
  
- Il nome della directory è un carattere due punti ":" (<xref:System.NotSupportedException>).  
  
- L'utente non è autorizzato a creare la directory (<xref:System.UnauthorizedAccessException>).  
  
- L'utente non ha le autorizzazioni richieste in una situazione di attendibilità parziale (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [Creazione, eliminazione e spostamento di file e directory](creating-deleting-and-moving-files-and-directories.md)
