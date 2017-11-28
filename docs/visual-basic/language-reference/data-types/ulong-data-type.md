---
title: Tipo di dati ULong (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ulong
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
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc52bfd16541feed599d5445adad7aba04f8e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="bfe9d-102">Tipo di dati ULong (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfe9d-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="bfe9d-103">Contiene interi senza segno a 64 bit (8 byte) compresi nell'intervallo da 0 a 18.446.744.073.709.551.615 (oltre 1,84 volte 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="bfe9d-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe9d-104">Note</span><span class="sxs-lookup"><span data-stu-id="bfe9d-104">Remarks</span></span>

<span data-ttu-id="bfe9d-105">Utilizzare il `ULong` il tipo di dati per contenere dati binari troppo grandi per `UInteger`, o il massimo valori unsigned integer.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="bfe9d-106">Il valore predefinito di `ULong` è 0.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="bfe9d-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="bfe9d-107">Literal assignments</span></span>

<span data-ttu-id="bfe9d-108">È possibile dichiarare e inizializzare un `ULong` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="bfe9d-109">Se il valore letterale integer è esterno all'intervallo di `ULong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="bfe9d-110">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ULong`.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="bfe9d-111">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="bfe9d-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bfe9d-113">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="bfe9d-114">Valori letterali numerici possono includere anche il `UL` o `ul` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `ULong` il tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-114">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="bfe9d-115">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="bfe9d-115">Programming tips</span></span>
  
-   <span data-ttu-id="bfe9d-116">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-116">**Negative Numbers.**</span></span> <span data-ttu-id="bfe9d-117">Poiché `ULong` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-117">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="bfe9d-118">Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `ULong`, Visual Basic converte l'espressione `Decimal` prima.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="bfe9d-119">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-119">**CLS Compliance.**</span></span> <span data-ttu-id="bfe9d-120">Il `ULong` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-120">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="bfe9d-121">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-121">**Interop Considerations.**</span></span> <span data-ttu-id="bfe9d-122">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `ulong` può avere un'ampiezza dei dati diversa (32 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="bfe9d-123">Se si passa un argomento a 32 bit a tale componente, dichiararla come `UInteger` anziché `ULong` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-123">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="bfe9d-124">Inoltre, automazione non supporta valori integer a 64 bit in Windows 95, Windows 98, Windows ME o Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-124">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="bfe9d-125">Non è possibile passare un Visual Basic `ULong` argomento a un componente di automazione su queste piattaforme.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-125">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="bfe9d-126">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-126">**Widening.**</span></span> <span data-ttu-id="bfe9d-127">Il `ULong` può ampliarsi nel tipo di dati `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-127">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="bfe9d-128">È pertanto possibile convertire `ULong` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-128">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="bfe9d-129">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-129">**Type Characters.**</span></span> <span data-ttu-id="bfe9d-130">Aggiungendo i caratteri di tipo letterale `UL` a un valore letterale indica al sistema di `ULong` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-130">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="bfe9d-131">`ULong`non include alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-131">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="bfe9d-132">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="bfe9d-132">**Framework Type.**</span></span> <span data-ttu-id="bfe9d-133">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bfe9d-133">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe9d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe9d-134">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="bfe9d-135">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="bfe9d-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="bfe9d-136">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="bfe9d-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="bfe9d-137">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="bfe9d-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="bfe9d-138">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="bfe9d-138">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="bfe9d-139">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="bfe9d-139">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
