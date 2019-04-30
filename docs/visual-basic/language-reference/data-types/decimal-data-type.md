---
title: Tipo di dati Decimal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 4d530a8c1f85d2f0045184c05df63849047a8204
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971769"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="480ca-102">Tipo di dati Decimal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="480ca-102">Decimal Data Type (Visual Basic)</span></span>
<span data-ttu-id="480ca-103">Contiene con segno a 128 bit (16 byte) valori che rappresentano numeri integer a 96 bit (12 byte) scalati in base una potenza variabile di 10.</span><span class="sxs-lookup"><span data-stu-id="480ca-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="480ca-104">Il fattore di scala specifica il numero di cifre a destra del separatore decimale; è compreso tra 0 e 28.</span><span class="sxs-lookup"><span data-stu-id="480ca-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="480ca-105">Con una scala pari a 0 (nessuna posizione decimale), il massimo valore possibile è + /-79.228.162.514.264.337.593.543.950.335 (+ /-7 .9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="480ca-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="480ca-106">Il valore massimo è + /-7,9228162514264337593543950335 con 28 posizioni decimali, e il più piccolo valore diverso da zero è + /-0,0000000000000000000000000001 (+ /-1E-28).</span><span class="sxs-lookup"><span data-stu-id="480ca-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="480ca-107">Note</span><span class="sxs-lookup"><span data-stu-id="480ca-107">Remarks</span></span>  
 <span data-ttu-id="480ca-108">Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero.</span><span class="sxs-lookup"><span data-stu-id="480ca-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="480ca-109">Supporta fino a 29 cifre significative e può rappresentare i valori che superano 7,9228 x 10 ^ 28.</span><span class="sxs-lookup"><span data-stu-id="480ca-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="480ca-110">È particolarmente adatto per i calcoli, come finanziario, che richiedono un elevato numero di cifre, ma non è in grado di tollerare errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="480ca-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>  
  
 <span data-ttu-id="480ca-111">Il valore predefinito di `Decimal` è 0.</span><span class="sxs-lookup"><span data-stu-id="480ca-111">The default value of `Decimal` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="480ca-112">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="480ca-112">Programming Tips</span></span>  
  
- <span data-ttu-id="480ca-113">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="480ca-113">**Precision.**</span></span> <span data-ttu-id="480ca-114">`Decimal` non è un tipo di dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="480ca-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="480ca-115">Il `Decimal` struttura contiene un valore integer binario, insieme ai bit di segno e un numero intero che specifica quale parte del valore è una frazione decimale fattore di scala.</span><span class="sxs-lookup"><span data-stu-id="480ca-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="480ca-116">Ne consegue `Decimal` numeri di avere una rappresentazione più precisa in memoria rispetto a tipi a virgola mobile (`Single` e `Double`).</span><span class="sxs-lookup"><span data-stu-id="480ca-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>  
  
- <span data-ttu-id="480ca-117">**Prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="480ca-117">**Performance.**</span></span> <span data-ttu-id="480ca-118">Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="480ca-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="480ca-119">È opportuno valutare l'importanza della precisione rispetto alle prestazioni prima di scegliere un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="480ca-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>  
  
- <span data-ttu-id="480ca-120">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="480ca-120">**Widening.**</span></span> <span data-ttu-id="480ca-121">Il `Decimal` può ampliarsi nel tipo di dati `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="480ca-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="480ca-122">Ciò significa che è possibile convertire `Decimal` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="480ca-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="480ca-123">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="480ca-123">**Trailing Zeros.**</span></span> <span data-ttu-id="480ca-124">Visual Basic non archivia gli zeri finali in un `Decimal` letterale.</span><span class="sxs-lookup"><span data-stu-id="480ca-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="480ca-125">Tuttavia, un `Decimal` variabile mantiene gli zeri finali acquisiti dal punto di vista.</span><span class="sxs-lookup"><span data-stu-id="480ca-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="480ca-126">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="480ca-126">The following example illustrates this.</span></span>  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     <span data-ttu-id="480ca-127">L'output di `MsgBox` nell'esempio precedente è come segue:</span><span class="sxs-lookup"><span data-stu-id="480ca-127">The output of `MsgBox` in the preceding example is as follows:</span></span>  
  
     <span data-ttu-id="480ca-128">D1 = profondità 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span><span class="sxs-lookup"><span data-stu-id="480ca-128">d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span></span>  
  
- <span data-ttu-id="480ca-129">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="480ca-129">**Type Characters.**</span></span> <span data-ttu-id="480ca-130">Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="480ca-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="480ca-131">Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="480ca-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>  
  
- <span data-ttu-id="480ca-132">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="480ca-132">**Framework Type.**</span></span> <span data-ttu-id="480ca-133">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="480ca-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="480ca-134">Intervallo</span><span class="sxs-lookup"><span data-stu-id="480ca-134">Range</span></span>  
 <span data-ttu-id="480ca-135">Potrebbe essere necessario usare il `D` tipo di carattere per assegnare un valore elevato per un `Decimal` variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="480ca-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="480ca-136">Questo requisito è perché il compilatore interpreta un valore letterale come `Long` , a meno che un carattere letterale di tipo segue il valore letterale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="480ca-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 <span data-ttu-id="480ca-137">La dichiarazione `bigDec1` non produce un overflow perché il valore assegnato a esso rientra nell'intervallo per `Long`.</span><span class="sxs-lookup"><span data-stu-id="480ca-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="480ca-138">Il `Long` valore può essere assegnato al `Decimal` variabile.</span><span class="sxs-lookup"><span data-stu-id="480ca-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="480ca-139">La dichiarazione `bigDec2` genera un errore di overflow perché è troppo grande per il valore assegnato a esso `Long`.</span><span class="sxs-lookup"><span data-stu-id="480ca-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="480ca-140">Poiché i valori letterali numerici non possono essere interpretato prima di tutto come un `Long`, non può essere assegnato per il `Decimal` variabile.</span><span class="sxs-lookup"><span data-stu-id="480ca-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="480ca-141">Per la `bigDec3`, il carattere di tipo letterale `D` risolve il problema, forzando il compilatore a interpretare il valore letterale come una `Decimal` anziché come un `Long`.</span><span class="sxs-lookup"><span data-stu-id="480ca-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480ca-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="480ca-142">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="480ca-143">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="480ca-143">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="480ca-144">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="480ca-144">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="480ca-145">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="480ca-145">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="480ca-146">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="480ca-146">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="480ca-147">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="480ca-147">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="480ca-148">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="480ca-148">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
