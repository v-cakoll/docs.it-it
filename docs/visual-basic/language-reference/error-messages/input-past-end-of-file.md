---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586741"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="ec08a-102">Input oltre la fine del file</span><span class="sxs-lookup"><span data-stu-id="ec08a-102">Input past end of file</span></span>
<span data-ttu-id="ec08a-103">Entrambi un `Input` istruzione sta leggendo da un file che è vuoto o uno in cui tutti i dati vengono utilizzati, o è stato utilizzato il `EOF` funzione con un file aperto per l'accesso binario.</span><span class="sxs-lookup"><span data-stu-id="ec08a-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ec08a-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ec08a-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="ec08a-105">Utilizzare il `EOF` funzione immediatamente prima di `Input` istruzione per individuare la fine del file.</span><span class="sxs-lookup"><span data-stu-id="ec08a-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="ec08a-106">Se il file è aperto per l'accesso binario, utilizzare `Seek` e `Loc`.</span><span class="sxs-lookup"><span data-stu-id="ec08a-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec08a-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec08a-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
