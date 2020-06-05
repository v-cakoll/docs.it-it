---
title: Operatore ^
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: e139becf74ae367266a23513e18d0bdbdd24cdea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371388"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="8797b-102">Operatore ^ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8797b-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="8797b-103">Eleva un numero alla potenza di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="8797b-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="8797b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8797b-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="8797b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8797b-105">Parts</span></span>

`number`\
<span data-ttu-id="8797b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8797b-106">Required.</span></span> <span data-ttu-id="8797b-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="8797b-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="8797b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8797b-108">Required.</span></span> <span data-ttu-id="8797b-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="8797b-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="8797b-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="8797b-110">Result</span></span>

<span data-ttu-id="8797b-111">Il risultato viene `number` elevato alla potenza di `exponent` , sempre come `Double` valore.</span><span class="sxs-lookup"><span data-stu-id="8797b-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="8797b-112">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="8797b-112">Supported Types</span></span>

<span data-ttu-id="8797b-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="8797b-113">`Double`.</span></span> <span data-ttu-id="8797b-114">Gli operandi di qualsiasi tipo diverso vengono convertiti in `Double` .</span><span class="sxs-lookup"><span data-stu-id="8797b-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8797b-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="8797b-115">Remarks</span></span>

<span data-ttu-id="8797b-116">Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8797b-116">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span>

<span data-ttu-id="8797b-117">Il valore di `exponent` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="8797b-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="8797b-118">Quando in un'unica espressione viene eseguita più di un elevamento a potenza, l' `^` operatore viene valutato in base a quanto rilevato da sinistra verso destra.</span><span class="sxs-lookup"><span data-stu-id="8797b-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="8797b-119">L' `^` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="8797b-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8797b-120">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="8797b-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8797b-121">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8797b-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="8797b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="8797b-122">Example</span></span>

<span data-ttu-id="8797b-123">Nell'esempio seguente viene usato l' `^` operatore per aumentare un numero alla potenza di un esponente.</span><span class="sxs-lookup"><span data-stu-id="8797b-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="8797b-124">Il risultato è il primo operando elevato alla potenza del secondo.</span><span class="sxs-lookup"><span data-stu-id="8797b-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="8797b-125">L'esempio precedente produce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="8797b-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="8797b-126">`exp1`è impostato su 4 (2 quadrato).</span><span class="sxs-lookup"><span data-stu-id="8797b-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="8797b-127">`exp2`è impostato su 19683 (3 cubid, quindi il valore Cubed).</span><span class="sxs-lookup"><span data-stu-id="8797b-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="8797b-128">`exp3`è impostato su-125 (-5 Cubed).</span><span class="sxs-lookup"><span data-stu-id="8797b-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="8797b-129">`exp4`è impostato su 625 (-5 alla quarta potenza).</span><span class="sxs-lookup"><span data-stu-id="8797b-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="8797b-130">`exp5`è impostato su 2 (radice cubo di 8).</span><span class="sxs-lookup"><span data-stu-id="8797b-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="8797b-131">`exp6`è impostato su 0,5 (1,0 diviso per la radice del cubo di 8).</span><span class="sxs-lookup"><span data-stu-id="8797b-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="8797b-132">Si noti l'importanza delle parentesi nelle espressioni dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="8797b-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="8797b-133">A causa della *precedenza degli operatori*, Visual Basic esegue normalmente l' `^` operatore prima di qualsiasi altro, anche l'operatore unario `–` .</span><span class="sxs-lookup"><span data-stu-id="8797b-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="8797b-134">Se `exp4` e sono `exp6` stati calcolati senza parentesi, avrebbero prodotto i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="8797b-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="8797b-135">`exp4 = -5 ^ 4`verrebbe calcolato come – (dal 5 al quarto), il che comporterebbe-625.</span><span class="sxs-lookup"><span data-stu-id="8797b-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="8797b-136">`exp6 = 8 ^ -1.0 / 3.0`verrebbe calcolato come (da 8 a-1 potenza o 0,125) diviso per 3,0, il che comporterebbe 0.041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="8797b-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="8797b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8797b-137">See also</span></span>

- [<span data-ttu-id="8797b-138">^ = (Operatore)</span><span class="sxs-lookup"><span data-stu-id="8797b-138">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="8797b-139">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="8797b-139">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="8797b-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8797b-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8797b-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="8797b-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="8797b-142">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8797b-142">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
