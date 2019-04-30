---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013790"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="e6f4c-102">Input oltre la fine del file</span><span class="sxs-lookup"><span data-stu-id="e6f4c-102">Input past end of file</span></span>
<span data-ttu-id="e6f4c-103">Entrambi un `Input` istruzione sta leggendo da un file vuoto o uno in cui tutti i dati viene utilizzato o è stato usato il `EOF` funzione con un file aperto per l'accesso binario.</span><span class="sxs-lookup"><span data-stu-id="e6f4c-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e6f4c-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e6f4c-104">To correct this error</span></span>  
  
1. <span data-ttu-id="e6f4c-105">Usare la `EOF` funzione immediatamente prima di `Input` istruzione per rilevare la fine del file.</span><span class="sxs-lookup"><span data-stu-id="e6f4c-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="e6f4c-106">Se il file viene aperto per l'accesso binario, usare `Seek` e `Loc`.</span><span class="sxs-lookup"><span data-stu-id="e6f4c-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f4c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6f4c-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
