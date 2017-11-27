---
title: "File già aperto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="fd64d-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="fd64d-102">File already open</span></span>
<span data-ttu-id="fd64d-103">In alcuni casi un file deve essere chiusi prima di un altro `FileOpen` oppure può avvenire in un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="fd64d-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="fd64d-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="fd64d-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="fd64d-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="fd64d-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="fd64d-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="fd64d-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd64d-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fd64d-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="fd64d-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="fd64d-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd64d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd64d-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
