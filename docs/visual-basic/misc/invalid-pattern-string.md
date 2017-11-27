---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f824a5844d6d2b365358030119826266a4b42ef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="fbfc5-102">Stringa di ricerca non valida</span><span class="sxs-lookup"><span data-stu-id="fbfc5-102">Invalid pattern string</span></span>
<span data-ttu-id="fbfc5-103">La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.</span><span class="sxs-lookup"><span data-stu-id="fbfc5-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fbfc5-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fbfc5-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="fbfc5-105">Esaminare i valori validi per le espressioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fbfc5-105">Review the valid characters for list expressions.</span></span>  
  
2.  <span data-ttu-id="fbfc5-106">Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="fbfc5-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3.  <span data-ttu-id="fbfc5-107">Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="fbfc5-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4.  <span data-ttu-id="fbfc5-108">Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.</span><span class="sxs-lookup"><span data-stu-id="fbfc5-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfc5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbfc5-109">See Also</span></span>  
 [<span data-ttu-id="fbfc5-110">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="fbfc5-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
