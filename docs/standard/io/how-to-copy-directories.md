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
# <a name="how-to-copy-directories"></a><span data-ttu-id="01d4e-103">Procedura: copiare le directory</span><span class="sxs-lookup"><span data-stu-id="01d4e-103">How to: Copy directories</span></span>
<span data-ttu-id="01d4e-104">Questo argomento illustra come usare le classi di I/O per copiare in modalità sincrona il contenuto di una directory in un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="01d4e-104">This topic demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="01d4e-105">Per un esempio di copia di file asincrona, vedere [I/O di file asincrono](asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="01d4e-105">For an example of asynchronous file copy, see [Asynchronous file I/O](asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="01d4e-106">In questo esempio le sottodirectory vengono copiate impostando l'elemento `copySubDirs` del metodo `DirectoryCopy` su `true`.</span><span class="sxs-lookup"><span data-stu-id="01d4e-106">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="01d4e-107">Il metodo `DirectoryCopy` copia le sottodirectory in modo ricorsivo chiamando se stesso in ogni sottodirectory finché non ci sono più sottodirectory da copiare.</span><span class="sxs-lookup"><span data-stu-id="01d4e-107">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01d4e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="01d4e-108">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="01d4e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01d4e-109">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="01d4e-110">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="01d4e-110">File and stream I/O</span></span>](index.md)
- [<span data-ttu-id="01d4e-111">Attività di I/O comuni</span><span class="sxs-lookup"><span data-stu-id="01d4e-111">Common I/O tasks</span></span>](common-i-o-tasks.md)
- [<span data-ttu-id="01d4e-112">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="01d4e-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)
