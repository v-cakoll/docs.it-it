---
title: Combinazione efficace di operatori
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
ms.openlocfilehash: 3088072646278dac13e4d483cb4f99297eaad9ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403472"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="e0674-102">Combinazione efficace di operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0674-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="e0674-103">Le espressioni complesse possono contenere molti operatori diversi.</span><span class="sxs-lookup"><span data-stu-id="e0674-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="e0674-104">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0674-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="e0674-105">La creazione di espressioni complesse come quella nell'esempio precedente richiede una conoscenza approfondita delle regole di precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="e0674-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="e0674-106">Per ulteriori informazioni, vedere [precedenza degli operatori in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="e0674-106">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="e0674-107">Espressioni parentesi</span><span class="sxs-lookup"><span data-stu-id="e0674-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="e0674-108">Spesso si desidera che le operazioni procedano in un ordine diverso rispetto a quello determinato dalla precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="e0674-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="e0674-109">Si consideri l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0674-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="e0674-110">Nell'esempio precedente viene moltiplicato per `z` `y` , quindi viene aggiunto il risultato a `4` .</span><span class="sxs-lookup"><span data-stu-id="e0674-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="e0674-111">Tuttavia, se si desidera aggiungere `y` e `4` prima di moltiplicare il risultato per `z` , è possibile eseguire l'override della normale precedenza degli operatori utilizzando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="e0674-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="e0674-112">Racchiudendo un'espressione tra parentesi, si impone la valutazione iniziale di tale espressione, indipendentemente dalla precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="e0674-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="e0674-113">Per forzare l'esempio precedente a eseguire prima l'aggiunta, è possibile riscriverla come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0674-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="e0674-114">Nell'esempio precedente vengono aggiunti `y` e `4` , quindi viene moltiplicato tale somma per `z` .</span><span class="sxs-lookup"><span data-stu-id="e0674-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="e0674-115">Espressioni parentesi annidate</span><span class="sxs-lookup"><span data-stu-id="e0674-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="e0674-116">È possibile annidare le espressioni in più livelli di parentesi per ignorare ulteriormente la precedenza.</span><span class="sxs-lookup"><span data-stu-id="e0674-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="e0674-117">Le espressioni più profondamente annidate tra parentesi vengono valutate per prime, seguite dalla successiva nidificazione più approfondita e così via fino al meno annidato e infine le espressioni all'esterno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="e0674-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="e0674-118">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0674-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="e0674-119">Nell'esempio precedente, `z + 2` viene valutato per primo, quindi le altre espressioni parentesi.</span><span class="sxs-lookup"><span data-stu-id="e0674-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="e0674-120">L'elevamento a potenza, che in genere ha una precedenza più alta rispetto all'addizione o alla moltiplicazione, viene valutato per ultimo in questo esempio perché le altre espressioni sono racchiuse tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="e0674-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0674-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0674-121">See also</span></span>

- [<span data-ttu-id="e0674-122">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0674-122">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e0674-123">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0674-123">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="e0674-124">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0674-124">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="e0674-125">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0674-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="e0674-126">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="e0674-126">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="e0674-127">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="e0674-127">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="e0674-128">Procedura: calcolare valori numerici</span><span class="sxs-lookup"><span data-stu-id="e0674-128">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="e0674-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0674-129">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
