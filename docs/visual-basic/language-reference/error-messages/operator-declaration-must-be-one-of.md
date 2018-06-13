---
title: "Dichiarazione dell'operatore deve essere uno di: +,-, *,-, -, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: eb1e7e8088ec8661be2469aff043c0f1a96e4d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595020"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="88b06-102">Dichiarazione dell'operatore deve essere uno di: +,-, \*,\,/, ^, &amp;, Like, Mod e, Or, Xor, non, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="88b06-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="88b06-103">È possibile dichiarare solo gli operatori che sono idoneo per l'overload.</span><span class="sxs-lookup"><span data-stu-id="88b06-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="88b06-104">Nella tabella seguente elenca gli operatori che è possibile dichiarare.</span><span class="sxs-lookup"><span data-stu-id="88b06-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="88b06-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="88b06-105">Type</span></span>|<span data-ttu-id="88b06-106">Operatori</span><span class="sxs-lookup"><span data-stu-id="88b06-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="88b06-107">Unario</span><span class="sxs-lookup"><span data-stu-id="88b06-107">Unary</span></span>|<span data-ttu-id="88b06-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="88b06-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="88b06-109">Binario</span><span class="sxs-lookup"><span data-stu-id="88b06-109">Binary</span></span>|<span data-ttu-id="88b06-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="88b06-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="88b06-111">Conversione (unario)</span><span class="sxs-lookup"><span data-stu-id="88b06-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="88b06-112">Si noti che il `=` operatore nell'elenco binario è l'operatore di confronto, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="88b06-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="88b06-113">**ID errore:** BC33000</span><span class="sxs-lookup"><span data-stu-id="88b06-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88b06-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="88b06-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="88b06-115">Selezionare un operatore dal set di operatori che supportano l'overload.</span><span class="sxs-lookup"><span data-stu-id="88b06-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="88b06-116">Se è necessario eseguire l'overload di un operatore che non può essere sottoposto a overload direttamente, creare una routine `Function` che accetti i parametri appropriati e restituisca il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="88b06-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b06-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88b06-117">See Also</span></span>  
 [<span data-ttu-id="88b06-118">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="88b06-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="88b06-119">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="88b06-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="88b06-120">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="88b06-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="88b06-121">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="88b06-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="88b06-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="88b06-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
