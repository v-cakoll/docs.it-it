---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802648"
---
# <a name="file-already-open"></a><span data-ttu-id="fcd30-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="fcd30-102">File already open</span></span>
<span data-ttu-id="fcd30-103">In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="fcd30-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="fcd30-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="fcd30-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="fcd30-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="fcd30-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="fcd30-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="fcd30-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcd30-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fcd30-107">To correct this error</span></span>  
  
1. <span data-ttu-id="fcd30-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="fcd30-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd30-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd30-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
