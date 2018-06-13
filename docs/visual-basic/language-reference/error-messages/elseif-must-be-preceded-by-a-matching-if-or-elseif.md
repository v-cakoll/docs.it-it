---
title: '&#39;#ElseIf&#39; deve essere preceduto da un oggetto corrispondente &#39;#If&#39; o &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588148"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="f5b12-102">&#39;#ElseIf&#39; deve essere preceduto da un oggetto corrispondente &#39;#If&#39; o &#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="f5b12-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="f5b12-103">`#ElseIf` è una direttiva di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="f5b12-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="f5b12-104">Un `#ElseIf` clausola deve essere preceduta da un oggetto corrispondente `#If` o `#ElseIf` clausola.</span><span class="sxs-lookup"><span data-stu-id="f5b12-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="f5b12-105">**ID errore:** BC30014</span><span class="sxs-lookup"><span data-stu-id="f5b12-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5b12-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f5b12-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f5b12-107">Verificare che un precedente `#If` o `#ElseIf` non è stato separato da questo `#ElseIf` da un blocco di compilazione condizionale o inserita in posizione errata `#End If`.</span><span class="sxs-lookup"><span data-stu-id="f5b12-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="f5b12-108">Se il `#ElseIf` è preceduto da un `#Else` direttiva, rimuovere il `#Else` o modificarla in modo che un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="f5b12-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="f5b12-109">Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="f5b12-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b12-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5b12-110">See Also</span></span>  
 [<span data-ttu-id="f5b12-111">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="f5b12-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
