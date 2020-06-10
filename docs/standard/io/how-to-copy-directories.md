---
title: 'Procedura: copiare le directory'
description: Vedere come copiare le directory usando le classi I/O che consentono di copiare in modo sincrono il contenuto di una directory in un altro percorso.
ms.date: 12/27/2018
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
ms.openlocfilehash: 65fe28c90a6cd6f0b3c8c32da19c1d9603900670
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662589"
---
# <a name="how-to-copy-directories"></a>Procedura: copiare le directory
Questo argomento illustra come usare le classi di I/O per copiare in modalità sincrona il contenuto di una directory in un'altra posizione.

Per un esempio di copia di file asincrona, vedere [I/O di file asincrono](asynchronous-file-i-o.md).

In questo esempio le sottodirectory vengono copiate impostando l'elemento `copySubDirs` del metodo `DirectoryCopy` su `true`. Il metodo `DirectoryCopy` copia le sottodirectory in modo ricorsivo chiamando se stesso in ogni sottodirectory finché non ci sono più sottodirectory da copiare.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [I/O di file e di flussi](index.md)
- [Attività di I/O comuni](common-i-o-tasks.md)
- [I/O di file asincrono](asynchronous-file-i-o.md)
