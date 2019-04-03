---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823506"
---
# <a name="file-already-open"></a><span data-ttu-id="bb732-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="bb732-102">File already open</span></span>
<span data-ttu-id="bb732-103">In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="bb732-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="bb732-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="bb732-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="bb732-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="bb732-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="bb732-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="bb732-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb732-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bb732-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="bb732-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="bb732-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb732-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb732-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
