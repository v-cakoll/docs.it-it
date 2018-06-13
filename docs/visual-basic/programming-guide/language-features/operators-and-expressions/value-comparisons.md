---
title: Confronto di valori (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649607"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="cac42-102">Confronto di valori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cac42-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="cac42-103">Gli operatori di confronto consente di creare espressioni che confrontano i valori di variabili numeriche.</span><span class="sxs-lookup"><span data-stu-id="cac42-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="cac42-104">Queste espressioni restituiscono un `Boolean` valore a seconda che il confronto sia true o false.</span><span class="sxs-lookup"><span data-stu-id="cac42-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="cac42-105">Esempi di un'espressione di questo tipo sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="cac42-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="cac42-106">Restituisce la prima espressione `True`, in quanto 45 è maggiore di 26.</span><span class="sxs-lookup"><span data-stu-id="cac42-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="cac42-107">Restituisce il secondo esempio `False`, in quanto 26 è maggiore di 45.</span><span class="sxs-lookup"><span data-stu-id="cac42-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="cac42-108">È inoltre possibile confrontare le espressioni numeriche in questo modo.</span><span class="sxs-lookup"><span data-stu-id="cac42-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="cac42-109">Le espressioni che confronto possono essere autonomamente le espressioni complesse, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cac42-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="cac42-110">L'espressione complessa precedente include valori letterali, variabili e chiamate di funzione.</span><span class="sxs-lookup"><span data-stu-id="cac42-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="cac42-111">Le espressioni su entrambi i lati dell'operatore di confronto vengono valutate e i valori risultanti vengono confrontati utilizzando il `>=` operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="cac42-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="cac42-112">Se il valore dell'espressione a sinistra è maggiore o uguale al valore dell'espressione a destra, l'intera espressione restituisce `True`; in caso contrario, restituisce `False`.</span><span class="sxs-lookup"><span data-stu-id="cac42-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="cac42-113">Le espressioni di confronto di valori utilizzate più frequentemente `If...Then` costruzioni, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cac42-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="cac42-114">Il `=` segno è un operatore di confronto, nonché un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="cac42-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="cac42-115">Quando usato come operatore di confronto, valuta se il valore a sinistra è uguale al valore a destra, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cac42-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="cac42-116">È inoltre possibile utilizzare un'espressione di confronto in qualsiasi punto un `Boolean` valore è necessario, ad esempio in un `If`, `While`, `Loop`, o `ElseIf` istruzione, o durante l'assegnazione o passare un valore a un `Boolean` variabile.</span><span class="sxs-lookup"><span data-stu-id="cac42-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="cac42-117">Nell'esempio seguente, viene assegnato il valore restituito dall'espressione di confronto per un `Boolean` variabile.</span><span class="sxs-lookup"><span data-stu-id="cac42-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cac42-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cac42-118">See Also</span></span>  
 [<span data-ttu-id="cac42-119">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="cac42-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="cac42-120">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="cac42-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="cac42-121">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cac42-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="cac42-122">Procedura: Calcolare valori numerici</span><span class="sxs-lookup"><span data-stu-id="cac42-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="cac42-123">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cac42-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
