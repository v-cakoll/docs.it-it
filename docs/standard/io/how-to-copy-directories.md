---
title: 'Procedura: copiare le directory'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cfe07af216da1c35b093a1ca23e4d48c60a7bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571235"
---
# <a name="how-to-copy-directories"></a>Procedura: copiare le directory
Questo esempio mostra come usare classi di I/O per copiare in modo sincronizzato il contenuto di una directory in un altro percorso. In questo esempio l'utente può specificare se copiare anche le sottodirectory. In caso affermativo, le sottodirectory vengono copiate in modo ricorsivo dal metodo di esempio, che chiama se stesso su ogni successiva sottodirectory finché non ci sono più sottodirectory da copiare.  
  
 Per un esempio di copia di file in modo asincrono, vedere [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)  
 [Attività di I/O comuni](../../../docs/standard/io/common-i-o-tasks.md)  
 [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)
