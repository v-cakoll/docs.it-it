---
title: 'Procedura: leggere il testo da file con un oggetto StreamReader (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: cd6f7b70f2ddabfc5a1476c45ca9813b9a4d949f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Procedura: leggere il testo da file con un oggetto StreamReader (Visual Basic)
L'oggetto `My.Computer.FileSystem` offre metodi per aprire <xref:System.IO.TextReader> e <xref:System.IO.TextWriter>. `OpenTextFileWriter` e `OpenTextFileReader` sono metodi avanzati che non vengono visualizzati in IntelliSense, a meno che non venga selezionata la scheda **Tutti**.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Per leggere una riga da un file con il lettore di testo  
  
-   Usare il metodo `OpenTextFileReader` per aprire <xref:System.IO.TextReader>, specificando il file. In questo esempio viene aperto il file denominato `testfile.txt`, da cui una riga viene letta e visualizzata in una finestra di messaggio.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il file letto deve essere un file di testo.  
  
 Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.  
  
 Prima di usare i dati nell'applicazione verificare tutti gli input. È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per leggere da un file, l'assembly richiede un livello di privilegi concesso dalla classe <xref:System.Security.Permissions.FileIOPermission>. Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi. Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice). È anche necessario che l'utente possa accedere al file. Per altre informazioni, vedere [Panoramica della tecnologia ACL](http://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>  
 [Componente SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)  
 [Lettura da file](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
