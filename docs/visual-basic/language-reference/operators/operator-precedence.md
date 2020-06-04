---
title: Ordine di precedenza degli operatori
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
ms.openlocfilehash: eef6314f5fc1f5a7fffa7997559f697130f6f755
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401446"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="0f2c0-102">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f2c0-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="0f2c0-103">Quando più operazioni si verificano in un'espressione, ogni parte viene valutata e risolta in base a un ordine predeterminato denominato *precedenza degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="0f2c0-104">Regole di precedenza</span><span class="sxs-lookup"><span data-stu-id="0f2c0-104">Precedence Rules</span></span>
 <span data-ttu-id="0f2c0-105">Quando le espressioni contengono operatori di più di una categoria, vengono valutate in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f2c0-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="0f2c0-106">Gli operatori aritmetici e di concatenazione hanno l'ordine di precedenza descritto nella sezione seguente e hanno tutti una maggiore precedenza rispetto agli operatori di confronto, logici e bit per bit.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="0f2c0-107">Tutti gli operatori di confronto hanno uguale precedenza e hanno una precedenza maggiore rispetto agli operatori logici e bit per bit, ma con precedenza più bassa rispetto agli operatori aritmetici e di concatenazione.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="0f2c0-108">Gli operatori logici e bit per bit hanno l'ordine di precedenza descritto nella sezione seguente e hanno una precedenza più bassa rispetto agli operatori aritmetici, di concatenazione e di confronto.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="0f2c0-109">Gli operatori con uguale precedenza vengono valutati da sinistra a destra nell'ordine in cui sono visualizzati nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="0f2c0-110">Ordine di precedenza</span><span class="sxs-lookup"><span data-stu-id="0f2c0-110">Precedence Order</span></span>
 <span data-ttu-id="0f2c0-111">Gli operatori vengono valutati nel seguente ordine di precedenza:</span><span class="sxs-lookup"><span data-stu-id="0f2c0-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="0f2c0-112">Operatore Await</span><span class="sxs-lookup"><span data-stu-id="0f2c0-112">Await Operator</span></span>
 <span data-ttu-id="0f2c0-113">Attendono</span><span class="sxs-lookup"><span data-stu-id="0f2c0-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="0f2c0-114">Operatori aritmetici e di concatenazione</span><span class="sxs-lookup"><span data-stu-id="0f2c0-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="0f2c0-115">Elevamento a potenza ( `^` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="0f2c0-116">Identità e negazione unari ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="0f2c0-117">Moltiplicazione e divisione a virgola mobile ( `*` , `/` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="0f2c0-118">Divisione di interi ( `\` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-118">Integer division (`\`)</span></span>

 <span data-ttu-id="0f2c0-119">Aritmetica modulare ( `Mod` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="0f2c0-120">Addizione e sottrazione ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="0f2c0-121">Concatenazione di stringhe ( `&` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="0f2c0-122">Spostamento di bit aritmetico ( `<<` , `>>` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="0f2c0-123">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="0f2c0-123">Comparison Operators</span></span>
 <span data-ttu-id="0f2c0-124">Tutti gli operatori di confronto ( `=` , `<>` , `<` , `<=` , `>` , `>=` , `Is` , `IsNot` , `Like` , `TypeOf` ... `Is` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="0f2c0-125">Operatori logici e bit per bit</span><span class="sxs-lookup"><span data-stu-id="0f2c0-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="0f2c0-126">Negazione ( `Not` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-126">Negation (`Not`)</span></span>

 <span data-ttu-id="0f2c0-127">Congiunzione ( `And` , `AndAlso` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="0f2c0-128">Disgiunzione inclusiva ( `Or` , `OrElse` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="0f2c0-129">Disgiunzione esclusiva ( `Xor` )</span><span class="sxs-lookup"><span data-stu-id="0f2c0-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="0f2c0-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="0f2c0-130">Comments</span></span>
 <span data-ttu-id="0f2c0-131">L' `=` operatore è solo l'operatore di confronto di uguaglianza, non l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="0f2c0-132">L'operatore di concatenazione `&` di stringhe () non è un operatore aritmetico, ma in precedenza è raggruppato con gli operatori aritmetici.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="0f2c0-133">Gli `Is` `IsNot` operatori e sono operatori di confronto dei riferimenti agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="0f2c0-134">Non confrontano i valori di due oggetti; controllano solo per determinare se due variabili oggetto fanno riferimento alla stessa istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="0f2c0-135">Associatività</span><span class="sxs-lookup"><span data-stu-id="0f2c0-135">Associativity</span></span>
 <span data-ttu-id="0f2c0-136">Quando gli operatori con la stessa precedenza vengono visualizzati insieme in un'espressione, ad esempio moltiplicazione e divisione, il compilatore valuta ogni operazione quando viene rilevata da sinistra verso destra.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="0f2c0-137">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="0f2c0-138">La prima espressione valuta la divisione 96/8 (che restituisce 12), quindi la divisione 12/4, che produce tre.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="0f2c0-139">Poiché il compilatore valuta le operazioni per `n1` da sinistra a destra, la valutazione è la stessa quando tale ordine è indicato in modo esplicito per `n2` .</span><span class="sxs-lookup"><span data-stu-id="0f2c0-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="0f2c0-140">`n1`E `n2` hanno un risultato di tre.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="0f2c0-141">Al contrario, `n3` ha un risultato di 48, perché le parentesi forzano il compilatore a valutare prima 8/4.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="0f2c0-142">A causa di questo comportamento, gli operatori vengono definiti *associativi a sinistra* in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="0f2c0-143">Override della precedenza e dell'associatività</span><span class="sxs-lookup"><span data-stu-id="0f2c0-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="0f2c0-144">È possibile utilizzare le parentesi per forzare la valutazione di alcune parti di un'espressione prima di altre.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="0f2c0-145">Questo può sostituire l'ordine di precedenza e l'associatività a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="0f2c0-146">Visual Basic esegue sempre le operazioni racchiuse tra parentesi prima di quelle esterne a.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="0f2c0-147">Tuttavia, tra parentesi, gestisce la precedenza e l'associatività ordinarie, a meno che non si utilizzino le parentesi all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="0f2c0-148">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-148">The following example illustrates this.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="0f2c0-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f2c0-149">See also</span></span>

- [<span data-ttu-id="0f2c0-150">= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="0f2c0-150">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="0f2c0-151">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="0f2c0-151">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="0f2c0-152">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="0f2c0-152">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="0f2c0-153">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="0f2c0-153">Like Operator</span></span>](like-operator.md)
- [<span data-ttu-id="0f2c0-154">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="0f2c0-154">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="0f2c0-155">Operatore await</span><span class="sxs-lookup"><span data-stu-id="0f2c0-155">Await Operator</span></span>](await-operator.md)
- [<span data-ttu-id="0f2c0-156">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="0f2c0-156">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="0f2c0-157">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="0f2c0-157">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
