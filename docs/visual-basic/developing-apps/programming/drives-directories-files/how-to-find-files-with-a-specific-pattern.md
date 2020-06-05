---
title: 'Procedura: Trovare file con un criterio specifico'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 71073672ed14cb2d5df5b5365266b718c59cb18f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401641"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>Procedura: trovare file con un modello specifico in Visual Basic

Il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> restituisce una raccolta di stringhe di sola lettura che rappresentano i nomi di percorso per i file. È possibile usare il parametro `wildCards` per specificare un criterio specifico. Se si vuole includere le sottodirectory nella ricerca, impostare il parametro `searchType` su `SearchOption.SearchAllSubDirectories`.  
  
 Se non vengono trovati file corrispondenti al criterio specificato, verrà restituita una raccolta vuota.  
  
> [!NOTE]
> Per informazioni sulla restituzione di un elenco di file usando la classe `DirectoryInfo` dello spazio dei nomi `System.IO`, vedere <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>Per trovare i file con un criterio specifico  
  
- Usare il metodo `GetFiles`, specificando il nome e percorso della directory che si vuole cercare e il criterio. L'esempio seguente restituisce tutti i file con estensione `.dll` contenuti nella directory e li aggiunge a `ListBox1`.  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  

 Le seguenti condizioni possono generare un'eccezione:  
  
- Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
- Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
- `directory` non esiste (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` punta a un file esistente (<xref:System.IO.IOException>).  
  
- La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
- Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
- L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
- L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Procedura: Trovare sottodirectory con un criterio specifico](how-to-find-subdirectories-with-a-specific-pattern.md)
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Procedura: Ottenere la raccolta di file di una directory](how-to-get-the-collection-of-files-in-a-directory.md)
