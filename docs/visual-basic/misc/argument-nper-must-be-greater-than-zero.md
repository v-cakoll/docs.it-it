---
title: L'argomento 'NPer' deve essere maggiore di zero
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: 0c2cf0f0000de44e1be796bb2de962b45c1d6969
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368062"
---
# <a name="argument-nper-must-be-greater-than-zero"></a><span data-ttu-id="938c3-102">L'argomento 'NPer' deve essere maggiore di zero</span><span class="sxs-lookup"><span data-stu-id="938c3-102">Argument 'NPer' must be greater than zero</span></span>
<span data-ttu-id="938c3-103">La funzione `NPer` , che restituisce un valore `Double` che specifica il numero di periodi per un'annualità in base a pagamenti periodici fissi e a un tasso di interesse fisso, richiede un argomento maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="938c3-103">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="938c3-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="938c3-104">To correct this error</span></span>  
  
- <span data-ttu-id="938c3-105">Controllare l'ortografia degli argomenti nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="938c3-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="938c3-106">Un nome di variabile scritto in modo non corretto può creare implicitamente una variabile numerica inizializzata su zero.</span><span class="sxs-lookup"><span data-stu-id="938c3-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
- <span data-ttu-id="938c3-107">Controllare le operazioni precedenti nelle variabili dell'espressione, specialmente quelle passate alla routine come argomenti da altre routine.</span><span class="sxs-lookup"><span data-stu-id="938c3-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938c3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="938c3-108">See also</span></span>

- [<span data-ttu-id="938c3-109">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="938c3-109">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
