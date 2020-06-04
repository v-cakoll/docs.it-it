---
title: Tipo di dati Integer
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: aa7b64162308d6af2763b29034c5a7276c973876
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415609"
---
# <a name="integer-data-type-visual-basic"></a><span data-ttu-id="fe653-102">Tipo di dati Integer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe653-102">Integer data type (Visual Basic)</span></span>

<span data-ttu-id="fe653-103">Contiene valori integer con segno a 32 bit (4 byte) in un intervallo compreso tra -2.147.483.648 e 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="fe653-103">Holds signed 32-bit (4-byte) integers that range in value from -2,147,483,648 through 2,147,483,647.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe653-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="fe653-104">Remarks</span></span>

 <span data-ttu-id="fe653-105">Il tipo di dati `Integer` consente di ottenere prestazioni ottimali su processori a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="fe653-105">The `Integer` data type provides optimal performance on a 32-bit processor.</span></span> <span data-ttu-id="fe653-106">Gli altri tipi integrali vengono caricati e memorizzati più lentamente.</span><span class="sxs-lookup"><span data-stu-id="fe653-106">The other integral types are slower to load and store from and to memory.</span></span>  
  
 <span data-ttu-id="fe653-107">Il valore predefinito di `Integer` è 0.</span><span class="sxs-lookup"><span data-stu-id="fe653-107">The default value of `Integer` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="fe653-108">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="fe653-108">Literal assignments</span></span>

<span data-ttu-id="fe653-109">È possibile dichiarare e inizializzare una `Integer` variabile assegnandogli un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="fe653-109">You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="fe653-110">Se il valore letterale integer è esterno all'intervallo di `Integer`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fe653-110">If the integer literal is outside the range of `Integer` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="fe653-111">Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fe653-111">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `Integer` values.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> <span data-ttu-id="fe653-112">Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="fe653-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="fe653-113">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="fe653-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="fe653-114">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe653-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

<span data-ttu-id="fe653-115">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="fe653-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="fe653-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fe653-116">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="fe653-117">I valori letterali numerici possono includere anche il `I` [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Integer` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe653-117">Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.</span></span>

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a><span data-ttu-id="fe653-118">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="fe653-118">Programming tips</span></span>

- <span data-ttu-id="fe653-119">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="fe653-119">**Interop Considerations.**</span></span> <span data-ttu-id="fe653-120">Se si interagisce con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che `Integer` in altri ambienti è presente una larghezza dei dati diversa (16 bit).</span><span class="sxs-lookup"><span data-stu-id="fe653-120">If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="fe653-121">Se si passa un argomento a 16 bit a un componente di questo tipo, nel nuovo codice Visual Basic è necessario eseguirne la dichiarazione come `Short` anziché come `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fe653-121">If you are passing a 16-bit argument to such a component, declare it as `Short` instead of `Integer` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="fe653-122">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="fe653-122">**Widening.**</span></span> <span data-ttu-id="fe653-123">Il tipo di dati `Integer` può ampliarsi nel tipo `Long`, `Decimal`, `Single` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="fe653-123">The `Integer` data type widens to `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="fe653-124">È pertanto possibile convertire `Integer` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe653-124">This means you can convert `Integer` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="fe653-125">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="fe653-125">**Type Characters.**</span></span> <span data-ttu-id="fe653-126">Aggiungendo il carattere di tipo letterale `I` a un valore letterale, se ne determina la conversione nel tipo di dati `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fe653-126">Appending the literal type character `I` to a literal forces it to the `Integer` data type.</span></span> <span data-ttu-id="fe653-127">Aggiungendo il carattere identificatore di tipo `%` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Integer`.</span><span class="sxs-lookup"><span data-stu-id="fe653-127">Appending the identifier type character `%` to any identifier forces it to `Integer`.</span></span>  
  
- <span data-ttu-id="fe653-128">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="fe653-128">**Framework Type.**</span></span> <span data-ttu-id="fe653-129">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe653-129">The corresponding type in the .NET Framework is the <xref:System.Int32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="fe653-130">Range</span><span class="sxs-lookup"><span data-stu-id="fe653-130">Range</span></span>

<span data-ttu-id="fe653-131">Se si tenta di impostare una variabile di un tipo integrale su un numero esterno all'intervallo valido per tale tipo, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="fe653-131">If you try to set a variable of an integral type to a number outside the range for that type, an error occurs.</span></span> <span data-ttu-id="fe653-132">Se si tenta di impostarlo in una frazione, il numero viene arrotondato all'intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="fe653-132">If you try to set it to a fraction, the number is rounded up or down to the nearest integer value.</span></span> <span data-ttu-id="fe653-133">Se il numero è egualmente vicino a due valori interi, il valore viene arrotondato all'intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="fe653-133">If the number is equally close to two integer values, the value is rounded to the nearest even integer.</span></span> <span data-ttu-id="fe653-134">Questo comportamento riduce al minimo gli errori di arrotondamento risultanti dall'arrotondamento coerente di un valore del punto centrale in una singola direzione.</span><span class="sxs-lookup"><span data-stu-id="fe653-134">This behavior minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.</span></span> <span data-ttu-id="fe653-135">Nel codice riportato di seguito vengono illustrati esempi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="fe653-135">The following code shows examples of rounding.</span></span>  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a><span data-ttu-id="fe653-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe653-136">See also</span></span>

- <xref:System.Int32?displayProperty=nameWithType>
- [<span data-ttu-id="fe653-137">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fe653-137">Data Types</span></span>](index.md)
- [<span data-ttu-id="fe653-138">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="fe653-138">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="fe653-139">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="fe653-139">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="fe653-140">CString</span><span class="sxs-lookup"><span data-stu-id="fe653-140">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="fe653-141">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="fe653-141">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="fe653-142">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fe653-142">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
