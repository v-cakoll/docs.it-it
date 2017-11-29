---
title: Input oltre la fine del file
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="528d8-102">Input oltre la fine del file</span><span class="sxs-lookup"><span data-stu-id="528d8-102">Input past end of file</span></span>
<span data-ttu-id="528d8-103">Entrambi un `Input` istruzione sta leggendo da un file che è vuoto o uno in cui tutti i dati vengono utilizzati, o è stato utilizzato il `EOF` funzione con un file aperto per l'accesso binario.</span><span class="sxs-lookup"><span data-stu-id="528d8-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="528d8-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="528d8-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="528d8-105">Utilizzare il `EOF` funzione immediatamente prima di `Input` istruzione per individuare la fine del file.</span><span class="sxs-lookup"><span data-stu-id="528d8-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="528d8-106">Se il file è aperto per l'accesso binario, utilizzare `Seek` e `Loc`.</span><span class="sxs-lookup"><span data-stu-id="528d8-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528d8-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="528d8-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
