---
title: 'Procedura: copiare le directory'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5602a4e227f3cd17e4a7c9a086bee69d3e3e506
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="f3cc2-102">Procedura: copiare le directory</span><span class="sxs-lookup"><span data-stu-id="f3cc2-102">How to: Copy Directories</span></span>
<span data-ttu-id="f3cc2-103">Questo esempio mostra come usare classi di I/O per copiare in modo sincronizzato il contenuto di una directory in un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-103">This example demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> <span data-ttu-id="f3cc2-104">In questo esempio l'utente può specificare se copiare anche le sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-104">In this example, the user can specify whether to also copy the subdirectories.</span></span> <span data-ttu-id="f3cc2-105">In caso affermativo, le sottodirectory vengono copiate in modo ricorsivo dal metodo di esempio, che chiama se stesso su ogni successiva sottodirectory finché non ci sono più sottodirectory da copiare.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-105">If the subdirectories are copied, the method in this example recursively copies them by calling itself on each subsequent subdirectory until there are no more to copy.</span></span>  
  
 <span data-ttu-id="f3cc2-106">Per un esempio di copia di file in modo asincrono, vedere [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="f3cc2-106">For an example of copying files asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cc2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3cc2-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f3cc2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3cc2-108">See Also</span></span>  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [<span data-ttu-id="f3cc2-109">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="f3cc2-109">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="f3cc2-110">Attività di I/O comuni</span><span class="sxs-lookup"><span data-stu-id="f3cc2-110">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
 [<span data-ttu-id="f3cc2-111">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="f3cc2-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
