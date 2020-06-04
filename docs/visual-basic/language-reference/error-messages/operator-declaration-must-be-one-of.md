---
title: "La dichiarazione dell'operatore deve essere una delle seguenti: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, false"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409335"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="42c4f-102">La dichiarazione dell'operatore deve essere una delle seguenti: +,-, \*, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="42c4f-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="42c4f-103">È possibile dichiarare solo un operatore idoneo per l'overload.</span><span class="sxs-lookup"><span data-stu-id="42c4f-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="42c4f-104">Nella tabella seguente sono elencati gli operatori che è possibile dichiarare.</span><span class="sxs-lookup"><span data-stu-id="42c4f-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="42c4f-105">Type</span><span class="sxs-lookup"><span data-stu-id="42c4f-105">Type</span></span>|<span data-ttu-id="42c4f-106">Operatori</span><span class="sxs-lookup"><span data-stu-id="42c4f-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="42c4f-107">Unaria</span><span class="sxs-lookup"><span data-stu-id="42c4f-107">Unary</span></span>|<span data-ttu-id="42c4f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="42c4f-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="42c4f-109">Binario</span><span class="sxs-lookup"><span data-stu-id="42c4f-109">Binary</span></span>|<span data-ttu-id="42c4f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="42c4f-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="42c4f-111">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="42c4f-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="42c4f-112">Si noti che l'operatore `=` nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="42c4f-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="42c4f-113">**ID errore:** BC33000</span><span class="sxs-lookup"><span data-stu-id="42c4f-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42c4f-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="42c4f-114">To correct this error</span></span>  
  
1. <span data-ttu-id="42c4f-115">Selezionare un operatore dal set di operatori che supportano l'overload.</span><span class="sxs-lookup"><span data-stu-id="42c4f-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="42c4f-116">Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="42c4f-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c4f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42c4f-117">See also</span></span>

- [<span data-ttu-id="42c4f-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="42c4f-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="42c4f-119">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="42c4f-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="42c4f-120">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="42c4f-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="42c4f-121">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="42c4f-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="42c4f-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="42c4f-122">Function Statement</span></span>](../statements/function-statement.md)
