---
title: 'Procedura: calcolare valori numerici (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649786"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="e4c5a-102">Procedura: calcolare valori numerici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4c5a-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="e4c5a-103">È possibile calcolare valori numerici tramite l'utilizzo di espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="e4c5a-104">Oggetto *espressione numerica* è un'espressione che contiene i valori letterali, costanti e variabili che rappresentano valori numerici e operatori che agiscono su quei valori.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="e4c5a-105">Calcolo di valori numerici</span><span class="sxs-lookup"><span data-stu-id="e4c5a-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="e4c5a-106">Per calcolare un valore numerico</span><span class="sxs-lookup"><span data-stu-id="e4c5a-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="e4c5a-107">Combinare uno o più valori letterali numerici, costanti e variabili in un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="e4c5a-108">L'esempio seguente mostra alcune espressioni numeriche valide.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="e4c5a-109">Le prime tre righe mostrano un valore letterale, una costante e una variabile.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="e4c5a-110">Ognuno di essi costituisce un'espressione numerica valida da se stesso.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="e4c5a-111">L'ultima riga mostra una combinazione di una variabile con due valori letterali.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="e4c5a-112">Si noti che un'espressione numerica non forma un'istruzione completa di Visual Basic da se stesso.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="e4c5a-113">È necessario utilizzare l'espressione come parte di un'istruzione completa.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="e4c5a-114">Per archiviare un valore numerico</span><span class="sxs-lookup"><span data-stu-id="e4c5a-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="e4c5a-115">È possibile utilizzare un'istruzione di assegnazione per assegnare il valore rappresentato da un'espressione numerica per una variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     <span data-ttu-id="e4c5a-116">Nell'esempio precedente, il valore dell'espressione sul lato destro dell'operatore uguale (`=`) viene assegnato alla variabile `j` sul lato sinistro dell'operatore, in modo `j` restituisce 276.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="e4c5a-117">Per altre informazioni, vedere [Istruzioni](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="e4c5a-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="e4c5a-118">Più operatori</span><span class="sxs-lookup"><span data-stu-id="e4c5a-118">Multiple Operators</span></span>  
 <span data-ttu-id="e4c5a-119">Se l'espressione numerica contiene più di un operatore, l'ordine in cui vengono valutati è determinato dalle regole di precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="e4c5a-120">Per ignorare le regole di precedenza degli operatori, racchiudere le espressioni tra parentesi, come illustrato nell'esempio precedente; le espressioni tra parentesi vengono valutate per primi.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="e4c5a-121">Per eseguire l'override di precedenza degli operatori normale</span><span class="sxs-lookup"><span data-stu-id="e4c5a-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="e4c5a-122">Utilizzare le parentesi per racchiudere le operazioni che si desidera venga eseguita per prima.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="e4c5a-123">L'esempio seguente mostra due risultati diversi con gli stessi operandi e operatori.</span><span class="sxs-lookup"><span data-stu-id="e4c5a-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     <span data-ttu-id="e4c5a-124">Nell'esempio precedente, il calcolo di `j` esegue l'operatore di addizione (`+`) prima perché le parentesi che racchiudono `(67 + i)` eseguire l'override della precedenza normale e il valore assegnato a `j` è 276 (4 volte 69).</span><span class="sxs-lookup"><span data-stu-id="e4c5a-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="e4c5a-125">Il calcolo di `k` esegue gli operatori nella loro precedenza normale (`*` prima `+`) e il valore assegnato a `k` 270 (268 più 2).</span><span class="sxs-lookup"><span data-stu-id="e4c5a-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="e4c5a-126">Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="e4c5a-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c5a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4c5a-127">See Also</span></span>  
 [<span data-ttu-id="e4c5a-128">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="e4c5a-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="e4c5a-129">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="e4c5a-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="e4c5a-130">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="e4c5a-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="e4c5a-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4c5a-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="e4c5a-132">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="e4c5a-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="e4c5a-133">Combinazione efficace di operatori</span><span class="sxs-lookup"><span data-stu-id="e4c5a-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
