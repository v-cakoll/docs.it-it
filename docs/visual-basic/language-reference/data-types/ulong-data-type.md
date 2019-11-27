---
title: Tipo di dati ULong
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343888"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="3a190-102">Tipo di dati ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a190-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="3a190-103">Include interi senza segno a 64 bit (8 byte) compresi tra 0 e 18.446.744.073.709.551.615 (più di 1,84 volte 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="3a190-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="3a190-104">Note</span><span class="sxs-lookup"><span data-stu-id="3a190-104">Remarks</span></span>

<span data-ttu-id="3a190-105">Utilizzare il tipo di dati `ULong` per contenere dati binari troppo grandi per `UInteger`o i valori Unsigned Integer più grandi possibili.</span><span class="sxs-lookup"><span data-stu-id="3a190-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="3a190-106">Il valore predefinito di `ULong` è 0.</span><span class="sxs-lookup"><span data-stu-id="3a190-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="3a190-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="3a190-107">Literal assignments</span></span>

<span data-ttu-id="3a190-108">È possibile dichiarare e inizializzare una variabile di `ULong` assegnando un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="3a190-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="3a190-109">Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3a190-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="3a190-110">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.</span><span class="sxs-lookup"><span data-stu-id="3a190-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="3a190-111">Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="3a190-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="3a190-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="3a190-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="3a190-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a190-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="3a190-114">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="3a190-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="3a190-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3a190-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="3a190-116">I valori letterali numerici possono includere anche il [carattere di tipo](../../programming-guide/language-features/data-types/type-characters.md) `UL` o `ul` per indicare il tipo di dati `ULong`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3a190-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="3a190-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="3a190-117">Programming tips</span></span>

- <span data-ttu-id="3a190-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="3a190-118">**Negative Numbers.**</span></span> <span data-ttu-id="3a190-119">Poiché `ULong` è un tipo senza segno, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="3a190-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="3a190-120">Se si usa l'operatore meno unario (`-`) su un'espressione che restituisce il tipo `ULong`, Visual Basic converte prima l'espressione in `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="3a190-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="3a190-121">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="3a190-121">**CLS Compliance.**</span></span> <span data-ttu-id="3a190-122">Il tipo di dati `ULong` non fa parte della [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="3a190-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="3a190-123">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="3a190-123">**Interop Considerations.**</span></span> <span data-ttu-id="3a190-124">Se si interagisce con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi come `ulong` possono avere una larghezza dati diversa (32 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="3a190-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="3a190-125">Se si passa un argomento a 32 bit a tale componente, dichiararlo come `UInteger` anziché `ULong` nel codice di Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="3a190-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="3a190-126">Inoltre, l'automazione non supporta interi a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="3a190-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="3a190-127">Non è possibile passare un Visual Basic `ULong` argomento a un componente di automazione su queste piattaforme.</span><span class="sxs-lookup"><span data-stu-id="3a190-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="3a190-128">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="3a190-128">**Widening.**</span></span> <span data-ttu-id="3a190-129">Il tipo di dati `ULong` viene ampliato in `Decimal`, `Single`e `Double`.</span><span class="sxs-lookup"><span data-stu-id="3a190-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="3a190-130">Ciò significa che è possibile convertire `ULong` in uno di questi tipi senza riscontrare un errore <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a190-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="3a190-131">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="3a190-131">**Type Characters.**</span></span> <span data-ttu-id="3a190-132">L'aggiunta di caratteri di tipo letterale `UL` a un valore letterale forza il tipo di dati `ULong`.</span><span class="sxs-lookup"><span data-stu-id="3a190-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="3a190-133">`ULong` non dispone di alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="3a190-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="3a190-134">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="3a190-134">**Framework Type.**</span></span> <span data-ttu-id="3a190-135">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a190-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a190-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a190-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="3a190-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3a190-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3a190-138">CString</span><span class="sxs-lookup"><span data-stu-id="3a190-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="3a190-139">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="3a190-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="3a190-140">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="3a190-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="3a190-141">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3a190-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
