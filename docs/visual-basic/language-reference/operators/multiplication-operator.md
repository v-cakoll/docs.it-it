---
title: '* Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: b5b601c7604cb7ce1afaebc98b2157634a77fda4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701097"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="62bcf-102">Operatore \* (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62bcf-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="62bcf-103">Moltiplica due numeri.</span><span class="sxs-lookup"><span data-stu-id="62bcf-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62bcf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62bcf-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="62bcf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="62bcf-105">Parts</span></span>  
  
|<span data-ttu-id="62bcf-106">Nome</span><span class="sxs-lookup"><span data-stu-id="62bcf-106">Term</span></span>|<span data-ttu-id="62bcf-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="62bcf-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="62bcf-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="62bcf-108">Required.</span></span> <span data-ttu-id="62bcf-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="62bcf-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="62bcf-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="62bcf-110">Required.</span></span> <span data-ttu-id="62bcf-111">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="62bcf-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="62bcf-112">Risultato</span><span class="sxs-lookup"><span data-stu-id="62bcf-112">Result</span></span>  
 <span data-ttu-id="62bcf-113">Il risultato è il prodotto di `number1` e `number2`.</span><span class="sxs-lookup"><span data-stu-id="62bcf-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="62bcf-114">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="62bcf-114">Supported Types</span></span>  
 <span data-ttu-id="62bcf-115">Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="62bcf-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62bcf-116">Note</span><span class="sxs-lookup"><span data-stu-id="62bcf-116">Remarks</span></span>  
 <span data-ttu-id="62bcf-117">Il tipo di dati del risultato dipende dai tipi degli operandi.</span><span class="sxs-lookup"><span data-stu-id="62bcf-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="62bcf-118">Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.</span><span class="sxs-lookup"><span data-stu-id="62bcf-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="62bcf-119">Tipi di dati degli operandi</span><span class="sxs-lookup"><span data-stu-id="62bcf-119">Operand data types</span></span>|<span data-ttu-id="62bcf-120">Tipo di dati result</span><span class="sxs-lookup"><span data-stu-id="62bcf-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="62bcf-121">Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULONG](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="62bcf-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="62bcf-122">Tipo di dati numerico appropriato per i tipi di dati di `number1` e `number2`.</span><span class="sxs-lookup"><span data-stu-id="62bcf-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="62bcf-123">Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="62bcf-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="62bcf-124">Entrambe le espressioni sono [decimali](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="62bcf-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="62bcf-125">Entrambe le espressioni sono [singole](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="62bcf-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="62bcf-126">Entrambe le espressioni sono un tipo di dati a virgola mobile (`Single` o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) ma non entrambe `Single` (Nota `Decimal` non è un tipo di dati a virgola mobile)</span><span class="sxs-lookup"><span data-stu-id="62bcf-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="62bcf-127">Se un'espressione restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerata come zero.</span><span class="sxs-lookup"><span data-stu-id="62bcf-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="62bcf-128">Overload</span><span class="sxs-lookup"><span data-stu-id="62bcf-128">Overloading</span></span>  
 <span data-ttu-id="62bcf-129">L'operatore `*` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="62bcf-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="62bcf-130">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="62bcf-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="62bcf-131">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="62bcf-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62bcf-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="62bcf-132">Example</span></span>  
 <span data-ttu-id="62bcf-133">In questo esempio viene usato l'operatore `*` per moltiplicare due numeri.</span><span class="sxs-lookup"><span data-stu-id="62bcf-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="62bcf-134">Il risultato è il prodotto dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="62bcf-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="62bcf-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62bcf-135">See also</span></span>

- [<span data-ttu-id="62bcf-136">Operatore \*=</span><span class="sxs-lookup"><span data-stu-id="62bcf-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="62bcf-137">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="62bcf-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="62bcf-138">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62bcf-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="62bcf-139">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="62bcf-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="62bcf-140">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62bcf-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
