---
title: Combinazione efficace di operatori (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: daaf75256b3449209b4e3c030cc6b54692c6a172
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620427"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="afe5b-102">Combinazione efficace di operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afe5b-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="afe5b-103">Le espressioni complesse possono contenere molti operatori diversi.</span><span class="sxs-lookup"><span data-stu-id="afe5b-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="afe5b-104">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="afe5b-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="afe5b-105">Per creare espressioni complesse come quello nell'esempio precedente richiede una conoscenza approfondita delle regole di precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="afe5b-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="afe5b-106">Per altre informazioni, vedere [precedenza degli operatori in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="afe5b-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="afe5b-107">Espressioni tra parentesi</span><span class="sxs-lookup"><span data-stu-id="afe5b-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="afe5b-108">Spesso è necessario di operazioni in un ordine diverso da quello determinato dalla precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="afe5b-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="afe5b-109">Si osservi l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="afe5b-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="afe5b-110">Moltiplica l'esempio precedente `z` dal `y`, quindi aggiunge il risultato a `4`.</span><span class="sxs-lookup"><span data-stu-id="afe5b-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="afe5b-111">Tuttavia, se si desidera aggiungere `y` e `4` prima di moltiplicando il risultato da `z`, è possibile eseguire l'override di precedenza degli operatori normale usando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="afe5b-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="afe5b-112">Racchiudendo un'espressione tra parentesi, si forza quell'espressione da valutare in primo luogo, indipendentemente dalla precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="afe5b-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="afe5b-113">Per forzare l'esempio precedente per eseguire prima l'addizione, è necessario riscriverla come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="afe5b-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="afe5b-114">Nell'esempio precedente viene aggiunto `y` e `4`, quindi moltiplica tale somma per `z`.</span><span class="sxs-lookup"><span data-stu-id="afe5b-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="afe5b-115">Espressioni tra parentesi nidificate</span><span class="sxs-lookup"><span data-stu-id="afe5b-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="afe5b-116">È possibile annidare le espressioni in più livelli di parentesi per ignorare la precedenza ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="afe5b-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="afe5b-117">Le espressioni di annidamento più profondo racchiuso tra parentesi vengono valutate per primi, seguito da quello successivo di annidamento più profondo, e così via fino al minimo di nidificazione e infine le espressioni all'esterno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="afe5b-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="afe5b-118">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="afe5b-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="afe5b-119">Nell'esempio precedente, `z + 2` viene valutato per primo, quindi le altre espressioni tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="afe5b-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="afe5b-120">Elevamento a potenza, che normalmente ha precedenza maggiore rispetto ad addizione e moltiplicazione, viene valutato per ultimo in questo esempio perché le altre espressioni sono racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="afe5b-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe5b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afe5b-121">See also</span></span>
- [<span data-ttu-id="afe5b-122">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afe5b-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="afe5b-123">Operatori di confronto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afe5b-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="afe5b-124">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afe5b-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="afe5b-125">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afe5b-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="afe5b-126">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="afe5b-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="afe5b-127">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="afe5b-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="afe5b-128">Procedura: Calcolare valori numerici</span><span class="sxs-lookup"><span data-stu-id="afe5b-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="afe5b-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afe5b-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
