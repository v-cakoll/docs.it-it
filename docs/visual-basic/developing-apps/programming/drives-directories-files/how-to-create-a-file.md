---
title: 'Procedura: Creare un file in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: f24fdd6ce1fea7540c33e4a2fdfc06885825f76a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628988"
---
# <a name="how-to-create-a-file-in-visual-basic"></a>Procedura: Creare un file in Visual Basic
In questo esempio viene creato un file di testo vuoto nel percorso specificato usando il metodo <xref:System.IO.File.Create%2A> nella classe <xref:System.IO.File>.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Usare la variabile `file` per scrivere il file.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se il file esiste già, viene sostituito.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il nome del percorso non è valido. Contiene ad esempio caratteri non validi o è costituito solo da uno spazio (<xref:System.ArgumentException>).  
  
- Il percorso è di sola lettura (<xref:System.IO.IOException>).  
  
- Il nome del percorso è `Nothing` (<xref:System.ArgumentNullException>).  
  
- Il nome del percorso è troppo lungo (<xref:System.IO.PathTooLongException>).  
  
- Il percorso non è valido (<xref:System.IO.DirectoryNotFoundException>).  
  
- Il percorso contiene solo due punti ":" (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È possibile che venga generata un'eccezione <xref:System.Security.SecurityException> in ambienti ad attendibilità parziale.  
  
 La chiamata al metodo <xref:System.IO.File.Create%2A> richiede <xref:System.Security.Permissions.FileIOPermission>.  
  
 Viene generata un'eccezione <xref:System.UnauthorizedAccessException> se l'utente non dispone dell'autorizzazione per creare il file.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [Uso di librerie da codice parzialmente attendibile](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [Nozioni fondamentali sulla sicurezza per l’accesso al codice](../../../../framework/misc/code-access-security-basics.md)
