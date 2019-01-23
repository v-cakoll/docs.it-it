---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 29a9b5ce3c3f8e6a02b52beda1338fd699143570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491337"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="4a542-102">Input oltre la fine del file</span><span class="sxs-lookup"><span data-stu-id="4a542-102">Input past end of file</span></span>
<span data-ttu-id="4a542-103">Entrambi un `Input` istruzione sta leggendo da un file vuoto o uno in cui tutti i dati viene utilizzato o è stato usato il `EOF` funzione con un file aperto per l'accesso binario.</span><span class="sxs-lookup"><span data-stu-id="4a542-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a542-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4a542-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4a542-105">Usare la `EOF` funzione immediatamente prima di `Input` istruzione per rilevare la fine del file.</span><span class="sxs-lookup"><span data-stu-id="4a542-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="4a542-106">Se il file viene aperto per l'accesso binario, usare `Seek` e `Loc`.</span><span class="sxs-lookup"><span data-stu-id="4a542-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a542-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a542-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
