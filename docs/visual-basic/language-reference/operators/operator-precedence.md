---
title: Precedenza tra gli operatori in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: a87407fe863569ff961f4a2dc320e73719ed4d9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601762"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="d074e-102">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d074e-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="d074e-103">Quando si verificano diverse operazioni in un'espressione, ogni parte viene valutata e risolti in un ordine predeterminato chiamato *precedenza degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="d074e-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="d074e-104">Regole di precedenza</span><span class="sxs-lookup"><span data-stu-id="d074e-104">Precedence Rules</span></span>  
 <span data-ttu-id="d074e-105">Se un'espressione contiene operatori da più di una categoria, vengono valutati in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="d074e-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="d074e-106">Gli operatori aritmetici e di concatenazione hanno l'ordine di precedenza descritta nella sezione seguente e tutti hanno la precedenza maggiore rispetto a confronto, logici e operatori bit per bit.</span><span class="sxs-lookup"><span data-stu-id="d074e-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="d074e-107">Tutti gli operatori di confronto hanno uguale precedenza e hanno la precedenza maggiore rispetto agli operatori logici e bit per bit, ma la precedenza inferiore rispetto agli operatori aritmetici e di concatenazione.</span><span class="sxs-lookup"><span data-stu-id="d074e-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="d074e-108">Gli operatori logici e bit per bit di ordine di precedenza descritta nella sezione seguente e tutti l'aritmetica, di concatenazione e gli operatori di confronto.</span><span class="sxs-lookup"><span data-stu-id="d074e-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="d074e-109">Gli operatori con uguale precedenza vengono valutati da sinistra a destra nell'ordine in cui vengono visualizzati nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="d074e-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="d074e-110">Ordine di precedenza</span><span class="sxs-lookup"><span data-stu-id="d074e-110">Precedence Order</span></span>  
 <span data-ttu-id="d074e-111">Gli operatori vengono valutati nell'ordine di precedenza seguente:</span><span class="sxs-lookup"><span data-stu-id="d074e-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="d074e-112">Operatore Await</span><span class="sxs-lookup"><span data-stu-id="d074e-112">Await Operator</span></span>  
 <span data-ttu-id="d074e-113">Await</span><span class="sxs-lookup"><span data-stu-id="d074e-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="d074e-114">Operazioni aritmetiche e operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="d074e-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="d074e-115">Elevamento a potenza (`^`)</span><span class="sxs-lookup"><span data-stu-id="d074e-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="d074e-116">Unario identità e la negazione (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="d074e-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="d074e-117">Moltiplicazione e divisione a virgola mobile (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="d074e-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="d074e-118">Divisione di interi (`\`)</span><span class="sxs-lookup"><span data-stu-id="d074e-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="d074e-119">Modulo aritmetico (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="d074e-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="d074e-120">Addizione e sottrazione (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="d074e-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="d074e-121">Concatenazione di stringhe (`&`)</span><span class="sxs-lookup"><span data-stu-id="d074e-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="d074e-122">Bit aritmetico (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="d074e-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="d074e-123">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="d074e-123">Comparison Operators</span></span>  
 <span data-ttu-id="d074e-124">Tutti gli operatori di confronto (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="d074e-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="d074e-125">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="d074e-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="d074e-126">Negazione (`Not`)</span><span class="sxs-lookup"><span data-stu-id="d074e-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="d074e-127">Conjunction (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="d074e-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="d074e-128">La disgiunzione (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="d074e-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="d074e-129">Disgiunzione (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="d074e-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="d074e-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="d074e-130">Comments</span></span>  
 <span data-ttu-id="d074e-131">Il `=` operatore è solo l'operatore di confronto uguaglianza, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d074e-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="d074e-132">L'operatore di concatenazione di stringhe (`&`) non è un operatore aritmetico, ma in precedenza viene raggruppato con gli operatori aritmetici.</span><span class="sxs-lookup"><span data-stu-id="d074e-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="d074e-133">Il `Is` e `IsNot` gli operatori sono gli operatori di confronto di riferimento di oggetto.</span><span class="sxs-lookup"><span data-stu-id="d074e-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="d074e-134">Essi non confrontare i valori di due oggetti. si verifica solo per determinare se due variabili oggetto fanno riferimento alla stessa istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d074e-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="d074e-135">Associazione</span><span class="sxs-lookup"><span data-stu-id="d074e-135">Associativity</span></span>  
 <span data-ttu-id="d074e-136">Quando gli operatori uguale precedenza vengono visualizzati insieme in un'espressione, ad esempio la moltiplicazione e divisione, il compilatore valuta ogni operazione che viene rilevato da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="d074e-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="d074e-137">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d074e-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="d074e-138">La prima espressione restituisce la divisione 96 / 8 (con conseguente 12) e quindi la divisione 12 / 4, che restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="d074e-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="d074e-139">Poiché il compilatore valuterà le operazioni per `n1` da sinistra a destra, la versione di valutazione è lo stesso quando quest'ordine è indicato in modo esplicito per `n2`.</span><span class="sxs-lookup"><span data-stu-id="d074e-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="d074e-140">Entrambe `n1` e `n2` dispone di un risultato pari a tre.</span><span class="sxs-lookup"><span data-stu-id="d074e-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="d074e-141">Al contrario, `n3` dispone di un risultato di 48, perché le parentesi forzano il compilatore può valutare 8 / 4 prima.</span><span class="sxs-lookup"><span data-stu-id="d074e-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="d074e-142">A causa di questo comportamento, gli operatori sono detta *associative all'operando sinistro* in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d074e-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="d074e-143">Override della precedenza e associatività degli operatori</span><span class="sxs-lookup"><span data-stu-id="d074e-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="d074e-144">È possibile utilizzare parentesi per forzare alcune parti di un'espressione da valutare prima degli altri.</span><span class="sxs-lookup"><span data-stu-id="d074e-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="d074e-145">Questo consente di ignorare l'ordine di precedenza sia di associatività degli operatori a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d074e-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="d074e-146">Vengono eseguite sempre le operazioni che sono racchiusi tra parentesi prima di quelli di fuori.</span><span class="sxs-lookup"><span data-stu-id="d074e-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="d074e-147">Tuttavia, all'interno delle parentesi, viene mantenuta la precedenza e associatività degli operatori, a meno che non si usano le parentesi all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="d074e-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="d074e-148">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d074e-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d074e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d074e-149">See also</span></span>
- [<span data-ttu-id="d074e-150">Operatore =</span><span class="sxs-lookup"><span data-stu-id="d074e-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="d074e-151">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="d074e-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="d074e-152">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="d074e-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="d074e-153">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="d074e-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="d074e-154">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="d074e-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="d074e-155">Operatore Await</span><span class="sxs-lookup"><span data-stu-id="d074e-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="d074e-156">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="d074e-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d074e-157">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="d074e-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
