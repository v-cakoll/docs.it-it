---
title: '- Operatore'
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
ms.openlocfilehash: 6539beb5cf8078281357445e2391fac189208087
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406353"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="a411e-102">Operatore - (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a411e-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="a411e-103">Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="a411e-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a411e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a411e-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="a411e-105">Oppure</span><span class="sxs-lookup"><span data-stu-id="a411e-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="a411e-106">Parti</span><span class="sxs-lookup"><span data-stu-id="a411e-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="a411e-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a411e-107">Required.</span></span> <span data-ttu-id="a411e-108">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="a411e-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a411e-109">Obbligatorio a meno che l' `–` operatore non calcoli un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="a411e-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="a411e-110">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="a411e-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="a411e-111">Risultato</span><span class="sxs-lookup"><span data-stu-id="a411e-111">Result</span></span>  
 <span data-ttu-id="a411e-112">Il risultato è la differenza tra `expression1` e `expression2` o il valore negato di `expression1` .</span><span class="sxs-lookup"><span data-stu-id="a411e-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="a411e-113">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` .</span><span class="sxs-lookup"><span data-stu-id="a411e-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a411e-114">Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="a411e-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="a411e-115">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="a411e-115">Supported Types</span></span>  
 <span data-ttu-id="a411e-116">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="a411e-116">All numeric types.</span></span> <span data-ttu-id="a411e-117">Sono inclusi i tipi a virgola mobile e non firmati e `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="a411e-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a411e-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="a411e-118">Remarks</span></span>  
 <span data-ttu-id="a411e-119">Nel primo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di sottrazione aritmetica *binario* per la differenza tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="a411e-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="a411e-120">Nel secondo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di negazione *unario* per il valore negativo di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="a411e-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="a411e-121">In questo senso, la negazione consiste nell'inversione del segno di in `expression1` modo che il risultato sia positivo se `expression1` è negativo.</span><span class="sxs-lookup"><span data-stu-id="a411e-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="a411e-122">Se una delle due espressioni restituisce [Nothing](../nothing.md), l' `–` operatore lo considera come zero.</span><span class="sxs-lookup"><span data-stu-id="a411e-122">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a411e-123">L' `–` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="a411e-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a411e-124">Se il codice usa questo operatore su una classe o una struttura di questo tipo, verificare di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="a411e-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="a411e-125">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a411e-125">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a411e-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="a411e-126">Example</span></span>  
 <span data-ttu-id="a411e-127">Nell'esempio seguente viene usato l' `–` operatore per calcolare e restituire la differenza tra due numeri e quindi per negare un numero.</span><span class="sxs-lookup"><span data-stu-id="a411e-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="a411e-128">Dopo l'esecuzione di queste istruzioni, `binaryResult` contiene 124,45 e `unaryResult` contiene – 334,90.</span><span class="sxs-lookup"><span data-stu-id="a411e-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a411e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a411e-129">See also</span></span>

- [<span data-ttu-id="a411e-130">Operatore-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a411e-130">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="a411e-131">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="a411e-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a411e-132">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a411e-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="a411e-133">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a411e-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="a411e-134">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a411e-134">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
