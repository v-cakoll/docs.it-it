---
title: "La dichiarazione dell'operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non, <<>>,, <>, <, < =, >, > =, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: dac8613d79e3262e4d1fd6ad1599fd01182e329b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819372"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="b5ed4-102">La dichiarazione dell'operatore deve essere uno di: +,-, \*,\,/, ^, &amp;, Like, Mod e, Or, Xor, non \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="b5ed4-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="b5ed4-103">È possibile dichiarare solo gli operatori che sono idoneo per l'overload.</span><span class="sxs-lookup"><span data-stu-id="b5ed4-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="b5ed4-104">Nella tabella seguente vengono elencati gli operatori che è possibile dichiarare.</span><span class="sxs-lookup"><span data-stu-id="b5ed4-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="b5ed4-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="b5ed4-105">Type</span></span>|<span data-ttu-id="b5ed4-106">Operatori</span><span class="sxs-lookup"><span data-stu-id="b5ed4-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="b5ed4-107">Unario</span><span class="sxs-lookup"><span data-stu-id="b5ed4-107">Unary</span></span>|<span data-ttu-id="b5ed4-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="b5ed4-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="b5ed4-109">Binario</span><span class="sxs-lookup"><span data-stu-id="b5ed4-109">Binary</span></span>|<span data-ttu-id="b5ed4-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="b5ed4-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="b5ed4-111">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="b5ed4-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="b5ed4-112">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b5ed4-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="b5ed4-113">**ID errore:** BC33000</span><span class="sxs-lookup"><span data-stu-id="b5ed4-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5ed4-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b5ed4-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="b5ed4-115">Selezionare un operatore dal set di operatori che supportano l'overload.</span><span class="sxs-lookup"><span data-stu-id="b5ed4-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="b5ed4-116">Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="b5ed4-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ed4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5ed4-117">See also</span></span>

- [<span data-ttu-id="b5ed4-118">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="b5ed4-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="b5ed4-119">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="b5ed4-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="b5ed4-120">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="b5ed4-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="b5ed4-121">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="b5ed4-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="b5ed4-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="b5ed4-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
