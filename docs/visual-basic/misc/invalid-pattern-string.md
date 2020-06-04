---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: aa408f4cecc2a2774cb98cba96cd04a67afcc546
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402213"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="b48bf-102">Stringa di ricerca non valida</span><span class="sxs-lookup"><span data-stu-id="b48bf-102">Invalid pattern string</span></span>
<span data-ttu-id="b48bf-103">La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.</span><span class="sxs-lookup"><span data-stu-id="b48bf-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b48bf-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b48bf-104">To correct this error</span></span>  
  
1. <span data-ttu-id="b48bf-105">Esaminare i valori validi per le espressioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b48bf-105">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="b48bf-106">Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="b48bf-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="b48bf-107">Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="b48bf-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="b48bf-108">Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.</span><span class="sxs-lookup"><span data-stu-id="b48bf-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48bf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b48bf-109">See also</span></span>

- [<span data-ttu-id="b48bf-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="b48bf-110">Like Operator</span></span>](../language-reference/operators/like-operator.md)
