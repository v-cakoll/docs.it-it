---
title: Tipo di dati ULong (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214243f6a8a87f4e4cc15f31be23275fff00d07d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863595"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="0968f-102">Tipo di dati ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0968f-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="0968f-103">Contiene valori integer senza segno a 64 bit (8 byte) nell'intervallo compreso tra 0 e 18.446.744.073.709.551.615 (1,84 volte più di 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="0968f-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0968f-104">Note</span><span class="sxs-lookup"><span data-stu-id="0968f-104">Remarks</span></span>

<span data-ttu-id="0968f-105">Usare la `ULong` tipo di dati per contenere dati binari troppo grandi per `UInteger`, o il più grande possibile valori unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="0968f-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="0968f-106">Il valore predefinito di `ULong` è 0.</span><span class="sxs-lookup"><span data-stu-id="0968f-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="0968f-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="0968f-107">Literal assignments</span></span>

<span data-ttu-id="0968f-108">È possibile dichiarare e inizializzare un `ULong` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="0968f-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0968f-109">Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0968f-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0968f-110">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.</span><span class="sxs-lookup"><span data-stu-id="0968f-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="0968f-111">Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="0968f-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0968f-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="0968f-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0968f-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="0968f-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="0968f-114">A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale.</span><span class="sxs-lookup"><span data-stu-id="0968f-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0968f-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0968f-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0968f-116">Valori letterali numerici possono includere anche il `UL` o `ul` [Digita carattere](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `ULong` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0968f-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="0968f-117">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="0968f-117">Programming tips</span></span>
  
-   <span data-ttu-id="0968f-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="0968f-118">**Negative Numbers.**</span></span> <span data-ttu-id="0968f-119">Poiché `ULong` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="0968f-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="0968f-120">Se si usa l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce il tipo `ULong`, Visual Basic consente di convertire l'espressione da `Decimal` prima.</span><span class="sxs-lookup"><span data-stu-id="0968f-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="0968f-121">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="0968f-121">**CLS Compliance.**</span></span> <span data-ttu-id="0968f-122">Il `ULong` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che lo usa.</span><span class="sxs-lookup"><span data-stu-id="0968f-122">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="0968f-123">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="0968f-123">**Interop Considerations.**</span></span> <span data-ttu-id="0968f-124">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `ulong` può avere una larghezza diversa dei dati (32 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="0968f-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="0968f-125">Se si passa un argomento a 32 bit a tale componente, dichiararlo come `UInteger` invece di `ULong` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0968f-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="0968f-126">Inoltre, automazione non supporta valori interi a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="0968f-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="0968f-127">Non è possibile passare un oggetto visivo di base `ULong` argomento a un componente di automazione in queste piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0968f-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="0968f-128">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="0968f-128">**Widening.**</span></span> <span data-ttu-id="0968f-129">Il `ULong` può ampliarsi nel tipo di dati `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="0968f-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="0968f-130">Ciò significa che è possibile convertire `ULong` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="0968f-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="0968f-131">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="0968f-131">**Type Characters.**</span></span> <span data-ttu-id="0968f-132">Aggiungendo i caratteri di tipo di valore letterale `UL` a un valore letterale, se ne determina la `ULong` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="0968f-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="0968f-133">`ULong` possiede alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="0968f-133">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="0968f-134">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="0968f-134">**Framework Type.**</span></span> <span data-ttu-id="0968f-135">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0968f-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0968f-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0968f-136">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="0968f-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0968f-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="0968f-138">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="0968f-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="0968f-139">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="0968f-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="0968f-140">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="0968f-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="0968f-141">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0968f-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
