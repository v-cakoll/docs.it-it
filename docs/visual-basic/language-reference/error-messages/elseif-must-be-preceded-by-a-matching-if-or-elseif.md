---
title: "'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 4832fb80cfbe42c7a1303e0de69f36784711c05a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311058"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="3237b-102">'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente</span><span class="sxs-lookup"><span data-stu-id="3237b-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
`#ElseIf` <span data-ttu-id="3237b-103">è una direttiva di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="3237b-103">is a conditional compilation directive.</span></span> <span data-ttu-id="3237b-104">Un' `#ElseIf` clausola deve essere preceduta da un oggetto corrispondente `#If` o `#ElseIf` clausola.</span><span class="sxs-lookup"><span data-stu-id="3237b-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="3237b-105">**ID errore:** BC30014</span><span class="sxs-lookup"><span data-stu-id="3237b-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3237b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3237b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="3237b-107">Verificare che un precedente `#If` oppure `#ElseIf` non sia stata separata da questo `#ElseIf` mediante un blocco di compilazione condizionale o inserita in posizione errata `#End If`.</span><span class="sxs-lookup"><span data-stu-id="3237b-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="3237b-108">Se il `#ElseIf` è preceduto da un `#Else` direttiva, rimuovere il `#Else` oppure modificarlo in base a un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="3237b-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="3237b-109">Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="3237b-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3237b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3237b-110">See also</span></span>

- [<span data-ttu-id="3237b-111">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="3237b-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
