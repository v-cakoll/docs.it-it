---
title: "&#39; #Region &#39; e &#39; area #End &#39; le istruzioni non sono valide all'interno di espressioni lambda su più righe di corpi di metodo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="88a08-102">&#39; #Region &#39; e &#39; area #End &#39; le istruzioni non sono valide all'interno di espressioni lambda corpi/su più righe (metodo)</span><span class="sxs-lookup"><span data-stu-id="88a08-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="88a08-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="88a08-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="88a08-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="88a08-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="88a08-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="88a08-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88a08-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="88a08-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="88a08-107">Verificare che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="88a08-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="88a08-108">Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="88a08-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a08-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88a08-109">See Also</span></span>  
 [<span data-ttu-id="88a08-110">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="88a08-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
