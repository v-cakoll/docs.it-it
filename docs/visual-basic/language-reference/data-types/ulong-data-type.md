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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400701"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="a5728-102">Tipo di dati ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5728-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="a5728-103">Contiene interi senza segno a 64 bit (8 byte) che vanno da 0 a 18.446.744.073.709,551.615 (più di 1,84 x 10 x 19).</span><span class="sxs-lookup"><span data-stu-id="a5728-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="a5728-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a5728-104">Remarks</span></span>

<span data-ttu-id="a5728-105">Utilizzare `ULong` il tipo di dati per `UInteger`contenere dati binari troppo grandi per o per i valori integer senza segno più grandi possibili.</span><span class="sxs-lookup"><span data-stu-id="a5728-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="a5728-106">Il valore predefinito di `ULong` è 0.</span><span class="sxs-lookup"><span data-stu-id="a5728-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="a5728-107">Assegnazioni letterali</span><span class="sxs-lookup"><span data-stu-id="a5728-107">Literal assignments</span></span>

<span data-ttu-id="a5728-108">È possibile dichiarare `ULong` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="a5728-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a5728-109">Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5728-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="a5728-110">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.</span><span class="sxs-lookup"><span data-stu-id="a5728-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="a5728-111">Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="a5728-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a5728-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="a5728-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a5728-113">A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a5728-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="a5728-114">A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="a5728-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="a5728-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5728-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="a5728-116">I valori letterali `UL` numerici possono includere anche il `ul` [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo o per indicare il `ULong` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a5728-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="a5728-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="a5728-117">Programming tips</span></span>

- <span data-ttu-id="a5728-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="a5728-118">**Negative Numbers.**</span></span> <span data-ttu-id="a5728-119">Poiché `ULong` è un tipo senza segno, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="a5728-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="a5728-120">Se si utilizza l'operatore meno unario (`-` `ULong`) su un'espressione `Decimal` che restituisce type , Visual Basic converte l'espressione in prima.</span><span class="sxs-lookup"><span data-stu-id="a5728-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="a5728-121">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="a5728-121">**CLS Compliance.**</span></span> <span data-ttu-id="a5728-122">Il `ULong` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="a5728-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="a5728-123">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="a5728-123">**Interop Considerations.**</span></span> <span data-ttu-id="a5728-124">Se si interagisce con componenti non scritti per .NET Framework, ad esempio oggetti `ulong` COM o di automazione, tenere presente che tipi quali possono avere una larghezza di dati diversa (32 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="a5728-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="a5728-125">Se si passa un argomento a 32 bit a `UInteger` un `ULong` componente di questo tipo, dichiararlo come anziché nel codice Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="a5728-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="a5728-126">Inoltre, l'automazione non supporta numeri interi a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a5728-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="a5728-127">Non è possibile `ULong` passare un argomento di Visual Basic a un componente di automazione su queste piattaforme.</span><span class="sxs-lookup"><span data-stu-id="a5728-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="a5728-128">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="a5728-128">**Widening.**</span></span> <span data-ttu-id="a5728-129">Il `ULong` tipo di `Decimal`dati `Single`si `Double`allarga a , , e .</span><span class="sxs-lookup"><span data-stu-id="a5728-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="a5728-130">Ciò significa `ULong` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.</span><span class="sxs-lookup"><span data-stu-id="a5728-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="a5728-131">**Digitare caratteri.**</span><span class="sxs-lookup"><span data-stu-id="a5728-131">**Type Characters.**</span></span> <span data-ttu-id="a5728-132">L'aggiunta dei `UL` caratteri di tipo letterale a un valore letterale lo forza al tipo di `ULong` dati.</span><span class="sxs-lookup"><span data-stu-id="a5728-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="a5728-133">`ULong`non ha alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="a5728-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="a5728-134">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="a5728-134">**Framework Type.**</span></span> <span data-ttu-id="a5728-135">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5728-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5728-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5728-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="a5728-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a5728-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a5728-138">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="a5728-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a5728-139">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="a5728-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="a5728-140">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="a5728-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="a5728-141">Utilizzo efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a5728-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
