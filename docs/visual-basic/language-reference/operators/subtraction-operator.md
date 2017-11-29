---
title: '- Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ffb7c96fe95e73dc857a15608df94ed8468f9df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="4594e-102">Operatore - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4594e-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="4594e-103">Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4594e-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4594e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4594e-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="4594e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4594e-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="4594e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4594e-106">Required.</span></span> <span data-ttu-id="4594e-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4594e-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4594e-108">Obbligatorio a meno che il `–` operatore viene calcolato un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="4594e-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="4594e-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4594e-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="4594e-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="4594e-110">Result</span></span>  
 <span data-ttu-id="4594e-111">Il risultato è la differenza tra `expression1` e `expression2`, o il valore negato di `expression1`.</span><span class="sxs-lookup"><span data-stu-id="4594e-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="4594e-112">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="4594e-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4594e-113">Vedere le tabelle "Calcoli di interi" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4594e-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="4594e-114">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="4594e-114">Supported Types</span></span>  
 <span data-ttu-id="4594e-115">Tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="4594e-115">All numeric types.</span></span> <span data-ttu-id="4594e-116">Sono inclusi i tipi senza segno a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="4594e-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4594e-117">Note</span><span class="sxs-lookup"><span data-stu-id="4594e-117">Remarks</span></span>  
 <span data-ttu-id="4594e-118">Nel primo utilizzo illustrato nella sintassi precedente, il `–` operatore è il *binario* operatore di sottrazione aritmetica per la differenza tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="4594e-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="4594e-119">Nel secondo utilizzo illustrato nella sintassi precedente, il `–` operatore è il *unario* operatore di negazione per il valore negativo di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4594e-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="4594e-120">In questo senso, la negazione consiste inversione del segno di `expression1` in modo che il risultato è positivo se `expression1` è negativo.</span><span class="sxs-lookup"><span data-stu-id="4594e-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="4594e-121">Se un'espressione restituisce [nulla](../../../visual-basic/language-reference/nothing.md), `–` operatore lo considera come zero.</span><span class="sxs-lookup"><span data-stu-id="4594e-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4594e-122">Il `–` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="4594e-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4594e-123">Se il codice utilizza l'operatore su una classe o una struttura, assicurarsi di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="4594e-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="4594e-124">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4594e-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4594e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="4594e-125">Example</span></span>  
 <span data-ttu-id="4594e-126">L'esempio seguente usa il `–` operatore per calcolare e restituire la differenza tra due numeri interi, quindi per negare un numero.</span><span class="sxs-lookup"><span data-stu-id="4594e-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="4594e-127">Dopo l'esecuzione di queste istruzioni, `binaryResult` contiene il valore 124,45 e `unaryResult` 334,90.</span><span class="sxs-lookup"><span data-stu-id="4594e-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4594e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4594e-128">See Also</span></span>  
 <span data-ttu-id="4594e-129">[-= Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="4594e-129">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span></span>  
 [<span data-ttu-id="4594e-130">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4594e-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4594e-131">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="4594e-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4594e-132">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4594e-132">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
