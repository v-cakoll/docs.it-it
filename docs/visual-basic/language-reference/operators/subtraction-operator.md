---
title: '- Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830669"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="7dd5b-102">Operatore - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dd5b-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="7dd5b-103">Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7dd5b-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="7dd5b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7dd5b-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="7dd5b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-106">Required.</span></span> <span data-ttu-id="7dd5b-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7dd5b-108">Obbligatorio solo se il `–` operatore sta calcolando un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="7dd5b-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7dd5b-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="7dd5b-110">Result</span></span>  
 <span data-ttu-id="7dd5b-111">Il risultato è la differenza tra `expression1` e `expression2`, o il valore negato di `expression1`.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="7dd5b-112">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="7dd5b-113">Vedere le tabelle "Calcoli di interi" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="7dd5b-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7dd5b-114">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="7dd5b-114">Supported Types</span></span>  
 <span data-ttu-id="7dd5b-115">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-115">All numeric types.</span></span> <span data-ttu-id="7dd5b-116">Inclusi i tipi senza segno e a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dd5b-117">Note</span><span class="sxs-lookup"><span data-stu-id="7dd5b-117">Remarks</span></span>  
 <span data-ttu-id="7dd5b-118">Nel primo utilizzo illustrato nella sintassi illustrata in precedenza, il `–` operatore è il *binario* operatore di sottrazione aritmetica per la differenza tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="7dd5b-119">Nel secondo utilizzo illustrato nella sintassi illustrata in precedenza, il `–` operatore è il *unario* operatore di negazione per il valore negativo di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="7dd5b-120">In questo senso, è costituito invertire il segno di negazione `expression1` in modo che il risultato è un valore positivo se `expression1` è negativo.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="7dd5b-121">Se delle espressioni viene valutata [Nothing](../../../visual-basic/language-reference/nothing.md), il `–` operatore lo considera come zero.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dd5b-122">Il `–` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7dd5b-123">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="7dd5b-124">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7dd5b-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd5b-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="7dd5b-125">Example</span></span>  
 <span data-ttu-id="7dd5b-126">L'esempio seguente usa il `–` operatore per calcolare e restituire la differenza tra due numeri, quindi per negare a un numero.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="7dd5b-127">Dopo l'esecuzione di queste istruzioni `binaryResult` contiene il valore 124,45 e `unaryResult` 334,90.</span><span class="sxs-lookup"><span data-stu-id="7dd5b-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd5b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dd5b-128">See also</span></span>

- [<span data-ttu-id="7dd5b-129">-= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dd5b-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="7dd5b-130">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="7dd5b-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7dd5b-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7dd5b-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7dd5b-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="7dd5b-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7dd5b-133">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7dd5b-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
