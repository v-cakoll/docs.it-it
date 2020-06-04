---
title: Tipo di dati Decimal
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
ms.openlocfilehash: 690c8061b6df1115aa24668520170b44edfa8287
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415647"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="15f5c-102">Tipo di dati Decimal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15f5c-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="15f5c-103">Contiene valori Signed a 128 bit (16 byte) che rappresentano numeri di tipo Integer a 96 bit (12 byte) scalati in base a una potenza variabile di 10.</span><span class="sxs-lookup"><span data-stu-id="15f5c-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="15f5c-104">Il fattore di scala specifica il numero di cifre a destra del separatore decimale. l'intervallo è compreso tra 0 e 28.</span><span class="sxs-lookup"><span data-stu-id="15f5c-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="15f5c-105">Con una scala pari a 0 (senza posizioni decimali), il valore massimo possibile è +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="15f5c-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="15f5c-106">Con 28 cifre decimali, il valore più grande è +/-7.9228162514264337593543950335 e il valore diverso da zero è +/-0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="15f5c-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="15f5c-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="15f5c-107">Remarks</span></span>

<span data-ttu-id="15f5c-108">Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero.</span><span class="sxs-lookup"><span data-stu-id="15f5c-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="15f5c-109">Supporta fino a 29 cifre significative e può rappresentare valori superiori a 7,9228 x 10 ^ 28.</span><span class="sxs-lookup"><span data-stu-id="15f5c-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="15f5c-110">È particolarmente adatto per i calcoli, ad esempio Financial, che richiedono un numero elevato di cifre ma non tollerano errori di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="15f5c-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="15f5c-111">Il valore predefinito di `Decimal` è 0.</span><span class="sxs-lookup"><span data-stu-id="15f5c-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="15f5c-112">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="15f5c-112">Programming Tips</span></span>

- <span data-ttu-id="15f5c-113">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-113">**Precision.**</span></span> <span data-ttu-id="15f5c-114">`Decimal`non è un tipo di dati a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="15f5c-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="15f5c-115">La `Decimal` struttura include un valore intero binario, insieme a un bit di segno e a un fattore di scala integer che specifica quale parte del valore è una frazione decimale.</span><span class="sxs-lookup"><span data-stu-id="15f5c-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="15f5c-116">Per questo motivo, i `Decimal` numeri presentano una rappresentazione più precisa in memoria rispetto ai tipi a virgola mobile ( `Single` e `Double` ).</span><span class="sxs-lookup"><span data-stu-id="15f5c-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="15f5c-117">**Prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-117">**Performance.**</span></span> <span data-ttu-id="15f5c-118">Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="15f5c-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="15f5c-119">Prima di scegliere un tipo di dati, è necessario valutare l'importanza della precisione rispetto alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="15f5c-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="15f5c-120">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-120">**Widening.**</span></span> <span data-ttu-id="15f5c-121">Il `Decimal` tipo di dati viene convertito in `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="15f5c-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="15f5c-122">Ciò significa che è possibile `Decimal` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="15f5c-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="15f5c-123">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-123">**Trailing Zeros.**</span></span> <span data-ttu-id="15f5c-124">Visual Basic non archivia gli zeri finali in un `Decimal` valore letterale.</span><span class="sxs-lookup"><span data-stu-id="15f5c-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="15f5c-125">Una variabile, tuttavia, `Decimal` conserva gli zeri finali acquisiti in modo computazionale.</span><span class="sxs-lookup"><span data-stu-id="15f5c-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="15f5c-126">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15f5c-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="15f5c-127">L'output di `MsgBox` nell'esempio precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="15f5c-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="15f5c-128">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-128">**Type Characters.**</span></span> <span data-ttu-id="15f5c-129">Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="15f5c-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="15f5c-130">Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="15f5c-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="15f5c-131">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="15f5c-131">**Framework Type.**</span></span> <span data-ttu-id="15f5c-132">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15f5c-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="15f5c-133">Range</span><span class="sxs-lookup"><span data-stu-id="15f5c-133">Range</span></span>

 <span data-ttu-id="15f5c-134">Potrebbe essere necessario usare il `D` carattere tipo per assegnare un valore di grandi dimensioni a una `Decimal` variabile o a una costante.</span><span class="sxs-lookup"><span data-stu-id="15f5c-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="15f5c-135">Questo requisito è dovuto al fatto che il compilatore interpreta un valore letterale come a `Long` meno che un carattere di tipo letterale non segua il valore letterale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15f5c-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="15f5c-136">La dichiarazione per `bigDec1` non produce un overflow perché il valore assegnato è compreso nell'intervallo per `Long` .</span><span class="sxs-lookup"><span data-stu-id="15f5c-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="15f5c-137">Il `Long` valore può essere assegnato alla `Decimal` variabile.</span><span class="sxs-lookup"><span data-stu-id="15f5c-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="15f5c-138">La dichiarazione per `bigDec2` genera un errore di overflow perché il valore assegnato è troppo grande per `Long` .</span><span class="sxs-lookup"><span data-stu-id="15f5c-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="15f5c-139">Poiché il valore letterale numerico non può essere prima interpretato come `Long` , non può essere assegnato alla `Decimal` variabile.</span><span class="sxs-lookup"><span data-stu-id="15f5c-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="15f5c-140">Per `bigDec3` , il carattere di tipo letterale `D` risolve il problema forzando il compilatore a interpretare il valore letterale come `Decimal` anziché come `Long` .</span><span class="sxs-lookup"><span data-stu-id="15f5c-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="15f5c-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f5c-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="15f5c-142">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="15f5c-142">Data Types</span></span>](index.md)
- [<span data-ttu-id="15f5c-143">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="15f5c-143">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="15f5c-144">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="15f5c-144">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="15f5c-145">CString</span><span class="sxs-lookup"><span data-stu-id="15f5c-145">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="15f5c-146">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="15f5c-146">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="15f5c-147">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="15f5c-147">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
