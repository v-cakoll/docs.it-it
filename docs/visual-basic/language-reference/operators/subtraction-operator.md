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
ms.openlocfilehash: eb34b34986613f36b624c43c04f98390ffba4fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965858"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="2796e-102">Operatore - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2796e-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="2796e-103">Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2796e-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2796e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2796e-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="2796e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2796e-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="2796e-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="2796e-106">Required.</span></span> <span data-ttu-id="2796e-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2796e-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="2796e-108">Obbligatorio a meno che `–` l'operatore non calcoli un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="2796e-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="2796e-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2796e-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="2796e-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="2796e-110">Result</span></span>  
 <span data-ttu-id="2796e-111">Il risultato è la differenza tra `expression1` e `expression2`o il valore negato di `expression1`.</span><span class="sxs-lookup"><span data-stu-id="2796e-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="2796e-112">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi `expression1` di `expression2`dati di e.</span><span class="sxs-lookup"><span data-stu-id="2796e-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="2796e-113">Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="2796e-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="2796e-114">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="2796e-114">Supported Types</span></span>  
 <span data-ttu-id="2796e-115">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="2796e-115">All numeric types.</span></span> <span data-ttu-id="2796e-116">Sono inclusi i tipi a virgola mobile e non firmati `Decimal`e.</span><span class="sxs-lookup"><span data-stu-id="2796e-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2796e-117">Note</span><span class="sxs-lookup"><span data-stu-id="2796e-117">Remarks</span></span>  
 <span data-ttu-id="2796e-118">Nel primo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di sottrazione aritmetica *binario* per la differenza tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="2796e-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="2796e-119">Nel secondo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di negazione *unario* per il valore negativo di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2796e-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="2796e-120">In questo senso, la negazione consiste nell'inversione del segno di `expression1` in modo che il risultato sia positivo se `expression1` è negativo.</span><span class="sxs-lookup"><span data-stu-id="2796e-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="2796e-121">Se una delle due espressioni restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), l' `–` operatore lo considera come zero.</span><span class="sxs-lookup"><span data-stu-id="2796e-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2796e-122">L' `–` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="2796e-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2796e-123">Se il codice usa questo operatore su una classe o una struttura di questo tipo, verificare di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="2796e-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="2796e-124">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2796e-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2796e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2796e-125">Example</span></span>  
 <span data-ttu-id="2796e-126">Nell'esempio seguente viene usato `–` l'operatore per calcolare e restituire la differenza tra due numeri e quindi per negare un numero.</span><span class="sxs-lookup"><span data-stu-id="2796e-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="2796e-127">Dopo l'esecuzione di queste istruzioni, `binaryResult` contiene 124,45 e `unaryResult` contiene – 334,90.</span><span class="sxs-lookup"><span data-stu-id="2796e-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2796e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2796e-128">See also</span></span>

- [<span data-ttu-id="2796e-129">Operatore-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2796e-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="2796e-130">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="2796e-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2796e-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2796e-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2796e-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="2796e-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2796e-133">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2796e-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
