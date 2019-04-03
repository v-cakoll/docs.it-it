---
title: Operatori ed espressioni in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: 8de4eeaa22f83392bcb6bb79a1fea327281dfec9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843747"
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="6151c-102">Operatori ed espressioni in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6151c-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="6151c-103">Un *operatore* è un elemento di codice che esegue un'operazione su uno o più elementi di codice che contengono valori.</span><span class="sxs-lookup"><span data-stu-id="6151c-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="6151c-104">Gli elementi di valore includono variabili, costanti, valori letterali, proprietà, espressioni e valori restituiti da procedure `Function` e `Operator`.</span><span class="sxs-lookup"><span data-stu-id="6151c-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="6151c-105">Un'*espressione* è una serie di elementi di valore combinati con operatori che restituisce un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="6151c-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="6151c-106">Gli operatori agiscono sugli elementi di valore mediante l'esecuzione di calcoli, confronti o altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="6151c-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="6151c-107">Tipi di operatori</span><span class="sxs-lookup"><span data-stu-id="6151c-107">Types of Operators</span></span>  
 <span data-ttu-id="6151c-108">Visual Basic fornisce i tipi di operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="6151c-108">Visual Basic provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="6151c-109">Gli [operatori aritmetici](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) eseguono calcoli comuni su valori numerici, inclusa l'inversione degli schemi di bit.</span><span class="sxs-lookup"><span data-stu-id="6151c-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="6151c-110">Gli [operatori di confronto](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) confrontano due espressioni e restituiscono un valore `Boolean` che rappresenta il risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="6151c-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="6151c-111">Gli [operatori di concatenamento](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) uniscono più stringhe in un'unica stringa.</span><span class="sxs-lookup"><span data-stu-id="6151c-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="6151c-112">Gli [operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combinano valori `Boolean` o numerici e restituiscono un risultato con lo stesso tipo di dati dei valori.</span><span class="sxs-lookup"><span data-stu-id="6151c-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="6151c-113">Gli elementi di valore che vengono combinati con un operatore sono detti *operandi* di tale operatore.</span><span class="sxs-lookup"><span data-stu-id="6151c-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="6151c-114">Gli operatori combinati con elementi di valore formano espressioni, ad eccezione dell'operatore di assegnazione che forma un'*istruzione*.</span><span class="sxs-lookup"><span data-stu-id="6151c-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="6151c-115">Per altre informazioni, vedere [Istruzioni](../../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="6151c-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="6151c-116">Valutazione delle espressioni</span><span class="sxs-lookup"><span data-stu-id="6151c-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="6151c-117">Il risultato finale di un'espressione rappresenta un valore, in genere espresso con un tipo di dati comune quale `Boolean`, `String` o un tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="6151c-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="6151c-118">Di seguito sono riportati esempi di espressioni.</span><span class="sxs-lookup"><span data-stu-id="6151c-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="6151c-119">Più operatori possono eseguire azioni in un'unica operazione o istruzione, come illustrato nel seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="6151c-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 <span data-ttu-id="6151c-120">Nell'esempio precedente, Visual Basic esegue le operazioni nell'espressione sul lato destro dell'operatore di assegnazione (`=`), quindi assegna il valore risultante nella variabile `x` a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6151c-120">In the preceding example, Visual Basic performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="6151c-121">Non esistono limiti al numero di operatori combinabili in un'espressione, ma per ottenere i risultati previsti è importante tenere presenti le regole di [Precedenza tra gli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="6151c-121">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="6151c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6151c-122">See also</span></span>

- [<span data-ttu-id="6151c-123">Operatori</span><span class="sxs-lookup"><span data-stu-id="6151c-123">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="6151c-124">Combinazione efficace di operatori</span><span class="sxs-lookup"><span data-stu-id="6151c-124">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="6151c-125">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="6151c-125">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
