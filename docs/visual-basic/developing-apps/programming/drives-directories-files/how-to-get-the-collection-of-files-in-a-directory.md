---
title: 'Procedura: Ottenere la raccolta di file di una directory in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- folders, working with
- files [Visual Basic], accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
ms.openlocfilehash: a708d9cfd7b1a5ded3088ee567660bd0b3a5423f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731933"
---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a>Procedura: Ottenere la raccolta di file di una directory in Visual Basic
Gli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> restituiscono una raccolta di stringhe di sola lettura che rappresenta i nomi dei file contenuti in una directory:  
  
-   Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> per eseguire una ricerca di file semplice in una directory specificata senza cercare nelle sottodirectory.  
  
-   Usare l'overload <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> per specificare opzioni aggiuntive per la ricerca. È possibile usare il parametro `wildCards` per specificare un criterio di ricerca. Per includere le sottodirectory nella ricerca, impostare il parametro `searchType` su <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>.  
  
 Se non vengono trovati file corrispondenti al criterio specificato, verrà restituita una raccolta vuota.  
  
### <a name="to-list-files-in-a-directory"></a>Per elencare i file in una directory  
  
-   Usare uno degli overload del metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType>, fornendo il nome e il percorso della directory in cui cercare nel parametro `directory`. L'esempio seguente restituisce tutti i file della directory e li aggiunge a `ListBox1`.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `directory` non esiste (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` punta a un file esistente (<xref:System.IO.IOException>).  
  
-   La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
-   Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
-   L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
-   L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>
- [Procedura: Trovare file con un criterio specifico](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
- [Procedura: Trovare sottodirectory con un criterio specifico](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
