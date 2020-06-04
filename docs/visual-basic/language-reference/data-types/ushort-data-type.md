---
title: Tipo di dati UShort
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: ee31156e00059699125fd72a7f091afbb21beab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415479"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="87781-102">Tipo di dati UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87781-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="87781-103">Include interi senza segno a 16 bit (a 2 byte) compresi tra 0 e 65.535.</span><span class="sxs-lookup"><span data-stu-id="87781-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87781-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="87781-104">Remarks</span></span>

 <span data-ttu-id="87781-105">Utilizzare il `UShort` tipo di dati per contenere dati binari troppo grandi per `Byte` .</span><span class="sxs-lookup"><span data-stu-id="87781-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="87781-106">Il valore predefinito di `UShort` è 0.</span><span class="sxs-lookup"><span data-stu-id="87781-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="87781-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="87781-107">Literal assignments</span></span>

<span data-ttu-id="87781-108">È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `UShort` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="87781-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="87781-109">Se il valore letterale integer è esterno all'intervallo di `UShort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="87781-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="87781-110">Nell'esempio seguente, i numeri interi uguali a 65.034 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai `UShort` valori.</span><span class="sxs-lookup"><span data-stu-id="87781-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="87781-111">Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="87781-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="87781-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="87781-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="87781-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="87781-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="87781-114">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="87781-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="87781-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87781-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="87781-116">I valori letterali numerici possono includere anche il `US` `us` [carattere di tipo](../../programming-guide/language-features/data-types/type-characters.md) o per indicare il `UShort` tipo di dati, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87781-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="87781-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="87781-117">Programming tips</span></span>
  
- <span data-ttu-id="87781-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="87781-118">**Negative Numbers.**</span></span> <span data-ttu-id="87781-119">Poiché `UShort` è un tipo senza segno, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="87781-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="87781-120">Se si usa l'operatore unario meno ( `-` ) su un'espressione che restituisce il tipo `UShort` , Visual Basic converte prima l'espressione in `Integer` .</span><span class="sxs-lookup"><span data-stu-id="87781-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="87781-121">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="87781-121">**CLS Compliance.**</span></span> <span data-ttu-id="87781-122">Il `UShort` tipo di dati non fa parte del [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="87781-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="87781-123">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="87781-123">**Widening.**</span></span> <span data-ttu-id="87781-124">Il `UShort` tipo di dati viene ampliato in `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` e `Double` .</span><span class="sxs-lookup"><span data-stu-id="87781-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="87781-125">Ciò significa che è possibile `UShort` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="87781-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="87781-126">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="87781-126">**Type Characters.**</span></span> <span data-ttu-id="87781-127">L'aggiunta di caratteri di tipo letterale `US` a un valore letterale impone il `UShort` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="87781-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="87781-128">`UShort`non ha un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="87781-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="87781-129">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="87781-129">**Framework Type.**</span></span> <span data-ttu-id="87781-130">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87781-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87781-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87781-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="87781-132">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="87781-132">Data Types</span></span>](index.md)
- [<span data-ttu-id="87781-133">CString</span><span class="sxs-lookup"><span data-stu-id="87781-133">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="87781-134">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="87781-134">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="87781-135">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="87781-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="87781-136">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="87781-136">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
