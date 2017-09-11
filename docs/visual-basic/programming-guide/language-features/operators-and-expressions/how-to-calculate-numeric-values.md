---
title: 'Procedura: calcolare valori numerici (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe781cca8f716c792d3af153b2004c716bc87f90
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="b4fc6-102">Procedura: calcolare valori numerici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4fc6-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="b4fc6-103">È possibile calcolare valori numerici tramite l'utilizzo di espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="b4fc6-104">Oggetto *espressione numerica* è un'espressione che contiene i valori letterali, costanti e variabili che rappresentano valori numerici e operatori che agiscono su quei valori.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="b4fc6-105">Calcolo di valori numerici</span><span class="sxs-lookup"><span data-stu-id="b4fc6-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="b4fc6-106">Per calcolare un valore numerico</span><span class="sxs-lookup"><span data-stu-id="b4fc6-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="b4fc6-107">Combinare uno o più valori letterali numerici, costanti e variabili in un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="b4fc6-108">L'esempio seguente mostra alcune espressioni numeriche valide.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="b4fc6-109">Le prime tre righe mostrano un valore letterale, una costante e una variabile.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="b4fc6-110">Ognuno forma un'espressione numerica valida da sola.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="b4fc6-111">La riga finale Mostra una combinazione di una variabile con due valori letterali.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="b4fc6-112">Si noti che un'espressione numerica non forma completa [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] istruzione da sola.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statement by itself.</span></span> <span data-ttu-id="b4fc6-113">È necessario utilizzare l'espressione come parte di un'istruzione completa.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="b4fc6-114">Per archiviare un valore numerico</span><span class="sxs-lookup"><span data-stu-id="b4fc6-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="b4fc6-115">È possibile utilizzare un'istruzione di assegnazione per assegnare il valore rappresentato da un'espressione numerica a una variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     <span data-ttu-id="b4fc6-116">[!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4fc6-116">[!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span></span>  
  
     <span data-ttu-id="b4fc6-117">Nell'esempio precedente, il valore dell'espressione sul lato destro dell'operatore uguale (`=`) viene assegnato alla variabile `j` sul lato sinistro dell'operatore, in modo `j` restituisce 276.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="b4fc6-118">Per ulteriori informazioni, vedere [istruzioni](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4fc6-118">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="b4fc6-119">Operatori multipli</span><span class="sxs-lookup"><span data-stu-id="b4fc6-119">Multiple Operators</span></span>  
 <span data-ttu-id="b4fc6-120">Se l'espressione numerica contiene più di un operatore, l'ordine in cui vengono valutati è determinato dalle regole di precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="b4fc6-121">Per ignorare le regole di precedenza degli operatori, racchiudere le espressioni tra parentesi, come illustrato nell'esempio precedente; le espressioni racchiuse tra parentesi vengono valutate per primi.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="b4fc6-122">Per eseguire l'override di precedenza normale degli operatori</span><span class="sxs-lookup"><span data-stu-id="b4fc6-122">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="b4fc6-123">Utilizzare le parentesi per racchiudere le operazioni che si desidera venga eseguita per prima.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="b4fc6-124">L'esempio seguente mostra due risultati diversi con lo stesso operandi e operatori.</span><span class="sxs-lookup"><span data-stu-id="b4fc6-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     <span data-ttu-id="b4fc6-125">[!code-vb[VbVbalrOperators&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4fc6-125">[!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span></span>  
  
     <span data-ttu-id="b4fc6-126">Nell'esempio precedente, il calcolo per `j` esegue l'operatore di addizione (`+`) prima in quanto le parentesi che racchiudono `(67 + i)` eseguire l'override della precedenza normale e il valore assegnato a `j` corrisponde a 276 (4 volte 69).</span><span class="sxs-lookup"><span data-stu-id="b4fc6-126">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="b4fc6-127">Il calcolo per `k` esegue gli operatori nella loro precedenza normale (`*` prima `+`) e il valore assegnato a `k` corrisponde a 270 (268 più 2).</span><span class="sxs-lookup"><span data-stu-id="b4fc6-127">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="b4fc6-128">Per ulteriori informazioni, vedere [precedenza tra operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b4fc6-128">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fc6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4fc6-129">See Also</span></span>  
 <span data-ttu-id="b4fc6-130">[Operatori ed espressioni](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4fc6-130">[Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="b4fc6-131"> [Confronto di valori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="b4fc6-131"> [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="b4fc6-132"> [Istruzioni](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4fc6-132"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="b4fc6-133"> [Precedenza tra operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="b4fc6-133"> [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="b4fc6-134"> [Aritmetici (operatori)](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="b4fc6-134"> [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="b4fc6-135"> [Combinazione efficace di operatori](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="b4fc6-135"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
