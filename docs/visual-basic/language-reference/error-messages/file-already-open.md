---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567035"
---
# <a name="file-already-open"></a><span data-ttu-id="20585-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="20585-102">File already open</span></span>
<span data-ttu-id="20585-103">In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="20585-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="20585-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="20585-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="20585-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="20585-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="20585-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="20585-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20585-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="20585-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="20585-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="20585-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20585-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20585-109">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
