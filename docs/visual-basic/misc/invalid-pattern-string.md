---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 3fa42632ad6d69642d7b8ec36bf2880bc10a5024
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732479"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="77595-102">Stringa di ricerca non valida</span><span class="sxs-lookup"><span data-stu-id="77595-102">Invalid pattern string</span></span>
<span data-ttu-id="77595-103">La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.</span><span class="sxs-lookup"><span data-stu-id="77595-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77595-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="77595-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="77595-105">Esaminare i valori validi per le espressioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="77595-105">Review the valid characters for list expressions.</span></span>  
  
2.  <span data-ttu-id="77595-106">Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="77595-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3.  <span data-ttu-id="77595-107">Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="77595-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4.  <span data-ttu-id="77595-108">Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.</span><span class="sxs-lookup"><span data-stu-id="77595-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77595-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77595-109">See also</span></span>
- [<span data-ttu-id="77595-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="77595-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
