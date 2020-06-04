---
title: "'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409660"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="ec5bd-102">'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente</span><span class="sxs-lookup"><span data-stu-id="ec5bd-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="ec5bd-103">`#ElseIf` è una direttiva di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="ec5bd-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="ec5bd-104">Una `#ElseIf` clausola deve essere preceduta da una `#If` clausola OR corrispondente `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="ec5bd-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="ec5bd-105">**ID errore:** BC30014</span><span class="sxs-lookup"><span data-stu-id="ec5bd-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ec5bd-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ec5bd-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ec5bd-107">Verificare che un oggetto `#If` o precedente `#ElseIf` non sia stato separato da questo oggetto `#ElseIf` mediante un blocco di compilazione condizionale o un oggetto inserito in modo errato `#End If` .</span><span class="sxs-lookup"><span data-stu-id="ec5bd-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="ec5bd-108">Se `#ElseIf` è preceduto da una `#Else` direttiva, rimuovere `#Else` o modificare il valore in un oggetto `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="ec5bd-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="ec5bd-109">Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="ec5bd-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5bd-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec5bd-110">See also</span></span>

- [<span data-ttu-id="ec5bd-111">#If... Direttive then... #Else</span><span class="sxs-lookup"><span data-stu-id="ec5bd-111">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
