---
title: "La dichiarazione dell'operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: f32935dd4aaccd3040655b418badc13c1988c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622273"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="57fd1-102">La dichiarazione dell'operatore deve essere uno di: +,-, \*,\,/, ^, &amp;, Like, Mod e, Or, Xor, non &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="57fd1-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="57fd1-103">È possibile dichiarare solo gli operatori che sono idoneo per l'overload.</span><span class="sxs-lookup"><span data-stu-id="57fd1-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="57fd1-104">Nella tabella seguente vengono elencati gli operatori che è possibile dichiarare.</span><span class="sxs-lookup"><span data-stu-id="57fd1-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="57fd1-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="57fd1-105">Type</span></span>|<span data-ttu-id="57fd1-106">Operatori</span><span class="sxs-lookup"><span data-stu-id="57fd1-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="57fd1-107">Unario</span><span class="sxs-lookup"><span data-stu-id="57fd1-107">Unary</span></span>|<span data-ttu-id="57fd1-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="57fd1-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="57fd1-109">Binario</span><span class="sxs-lookup"><span data-stu-id="57fd1-109">Binary</span></span>|<span data-ttu-id="57fd1-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="57fd1-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="57fd1-111">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="57fd1-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="57fd1-112">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="57fd1-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="57fd1-113">**ID errore:** BC33000</span><span class="sxs-lookup"><span data-stu-id="57fd1-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57fd1-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="57fd1-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="57fd1-115">Selezionare un operatore dal set di operatori che supportano l'overload.</span><span class="sxs-lookup"><span data-stu-id="57fd1-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="57fd1-116">Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="57fd1-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fd1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57fd1-117">See also</span></span>
- [<span data-ttu-id="57fd1-118">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="57fd1-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="57fd1-119">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="57fd1-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="57fd1-120">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="57fd1-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="57fd1-121">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="57fd1-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="57fd1-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="57fd1-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
