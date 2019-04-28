---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790598"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="fd1c9-102">Stringa di ricerca non valida</span><span class="sxs-lookup"><span data-stu-id="fd1c9-102">Invalid pattern string</span></span>
<span data-ttu-id="fd1c9-103">La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd1c9-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fd1c9-104">To correct this error</span></span>  
  
1. <span data-ttu-id="fd1c9-105">Esaminare i valori validi per le espressioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-105">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="fd1c9-106">Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="fd1c9-107">Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="fd1c9-108">Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1c9-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd1c9-109">See also</span></span>

- [<span data-ttu-id="fd1c9-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="fd1c9-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
