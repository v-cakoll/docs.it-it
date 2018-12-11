---
title: Tipo di dati Long (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 357b7b42c7ad609b2a86ec3ee79a0f6f38dd9471
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155119"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="85d9f-102">Tipo di dati Long (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85d9f-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="85d9f-103">Contiene valori integer a 64 bit (8 byte) nell'intervallo compreso tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 (9.2... E + 18).</span><span class="sxs-lookup"><span data-stu-id="85d9f-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85d9f-104">Note</span><span class="sxs-lookup"><span data-stu-id="85d9f-104">Remarks</span></span>

 <span data-ttu-id="85d9f-105">Usare la `Long` contenga numeri interi che sono troppo grandi per rientrare tipo di dati di `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="85d9f-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="85d9f-106">Il valore predefinito di `Long` è 0.</span><span class="sxs-lookup"><span data-stu-id="85d9f-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="85d9f-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="85d9f-107">Literal assignments</span></span> 

<span data-ttu-id="85d9f-108">È possibile dichiarare e inizializzare un `Long` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="85d9f-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="85d9f-109">Se il valore letterale integer è esterno all'intervallo di `Long`, vale a dire se è minore di <xref:System.Int64.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="85d9f-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="85d9f-110">Nell'esempio seguente, i valori interi uguali a 4.294.967.296 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Long`.</span><span class="sxs-lookup"><span data-stu-id="85d9f-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="85d9f-111">Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="85d9f-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="85d9f-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="85d9f-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="85d9f-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="85d9f-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="85d9f-114">A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale.</span><span class="sxs-lookup"><span data-stu-id="85d9f-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="85d9f-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="85d9f-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="85d9f-116">Valori letterali numerici possono includere anche il `L` [Digita carattere](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Long` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="85d9f-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="85d9f-117">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="85d9f-117">Programming tips</span></span>

-   <span data-ttu-id="85d9f-118">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="85d9f-118">**Interop Considerations.**</span></span> <span data-ttu-id="85d9f-119">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che `Long` ha una larghezza diversa dei dati (32 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="85d9f-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="85d9f-120">Se si passa un argomento a 32 bit a tale componente, dichiararlo come `Integer` invece di `Long` nel nuovo codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="85d9f-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="85d9f-121">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="85d9f-121">**Widening.**</span></span> <span data-ttu-id="85d9f-122">Il `Long` può ampliarsi nel tipo di dati `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="85d9f-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="85d9f-123">È pertanto possibile convertire `Long` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85d9f-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="85d9f-124">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="85d9f-124">**Type Characters.**</span></span> <span data-ttu-id="85d9f-125">Aggiungendo il carattere di tipo letterale `L` a un valore letterale, se ne determina la conversione nel tipo di dati `Long`.</span><span class="sxs-lookup"><span data-stu-id="85d9f-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="85d9f-126">Aggiungendo il carattere identificatore di tipo `&` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Long`.</span><span class="sxs-lookup"><span data-stu-id="85d9f-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="85d9f-127">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="85d9f-127">**Framework Type.**</span></span> <span data-ttu-id="85d9f-128">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int64?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85d9f-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="85d9f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85d9f-129">See also</span></span>

<span data-ttu-id="85d9f-130"><xref:System.Int64>
[Tipi di dati](../../../visual-basic/language-reference/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="85d9f-130"><xref:System.Int64>
[Data Types](../../../visual-basic/language-reference/data-types/index.md) </span></span>  
<span data-ttu-id="85d9f-131">[Tipo di dati integer](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="85d9f-131">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="85d9f-132">[Tipo di dati short](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="85d9f-132">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="85d9f-133">[Funzioni di conversione tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="85d9f-133">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="85d9f-134">[Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="85d9f-134">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="85d9f-135">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="85d9f-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
