---
title: "'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: d6fa76b2aba45e3455cef6ceafc0f737ef56225d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271551"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="08659-102">'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente</span><span class="sxs-lookup"><span data-stu-id="08659-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="08659-103">`#ElseIf` è una direttiva di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="08659-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="08659-104">Un' `#ElseIf` clausola deve essere preceduta da un oggetto corrispondente `#If` o `#ElseIf` clausola.</span><span class="sxs-lookup"><span data-stu-id="08659-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="08659-105">**ID errore:** BC30014</span><span class="sxs-lookup"><span data-stu-id="08659-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08659-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="08659-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="08659-107">Verificare che un precedente `#If` oppure `#ElseIf` non sia stata separata da questo `#ElseIf` mediante un blocco di compilazione condizionale o inserita in posizione errata `#End If`.</span><span class="sxs-lookup"><span data-stu-id="08659-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="08659-108">Se il `#ElseIf` è preceduto da un `#Else` direttiva, rimuovere il `#Else` oppure modificarlo in base a un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="08659-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="08659-109">Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="08659-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08659-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08659-110">See also</span></span>
- [<span data-ttu-id="08659-111">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="08659-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
