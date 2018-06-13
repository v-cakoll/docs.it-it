---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586670"
---
# <a name="file-already-open"></a><span data-ttu-id="90b5a-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="90b5a-102">File already open</span></span>
<span data-ttu-id="90b5a-103">In alcuni casi un file deve essere chiusi prima di un altro `FileOpen` oppure può avvenire in un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="90b5a-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="90b5a-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="90b5a-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="90b5a-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="90b5a-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="90b5a-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="90b5a-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90b5a-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="90b5a-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="90b5a-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="90b5a-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b5a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90b5a-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
