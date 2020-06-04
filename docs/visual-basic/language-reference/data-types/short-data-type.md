---
title: Tipo di dati Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 176d27c86127dac1d9c9c0231790f7a5c2a2fefc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415557"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="9e850-102">Tipo di dati short (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e850-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="9e850-103">Include interi con segno a 16 bit (2 byte) compresi tra-32.768 e 32.767.</span><span class="sxs-lookup"><span data-stu-id="9e850-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e850-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="9e850-104">Remarks</span></span>  

 <span data-ttu-id="9e850-105">Utilizzare il `Short` tipo di dati per contenere valori integer per i quali non è necessaria la larghezza dei dati completa di `Integer` .</span><span class="sxs-lookup"><span data-stu-id="9e850-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="9e850-106">In alcuni casi, il Common Language Runtime è in grado di comprimere le variabili in modo `Short` stretto e di risparmiare sull'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="9e850-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="9e850-107">Il valore predefinito di `Short` è 0.</span><span class="sxs-lookup"><span data-stu-id="9e850-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="9e850-108">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="9e850-108">Literal assignments</span></span>

<span data-ttu-id="9e850-109">È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `Short` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="9e850-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="9e850-110">Se il valore letterale integer è esterno all'intervallo di `Short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9e850-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="9e850-111">Nell'esempio seguente, i numeri interi uguali a 1.034 rappresentati come valori letterali decimali, esadecimali e binari vengono convertiti in modo implicito da [Integer](integer-data-type.md) a `Short` valori.</span><span class="sxs-lookup"><span data-stu-id="9e850-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="9e850-112">Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="9e850-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="9e850-113">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="9e850-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="9e850-114">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9e850-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="9e850-115">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="9e850-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="9e850-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9e850-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="9e850-117">I valori letterali numerici possono includere anche il `S` [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `Short` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9e850-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="9e850-118">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="9e850-118">Programming tips</span></span>

- <span data-ttu-id="9e850-119">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="9e850-119">**Widening.**</span></span> <span data-ttu-id="9e850-120">Il `Short` tipo di dati viene ampliato in `Integer` , `Long` , `Decimal` , `Single` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="9e850-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="9e850-121">È pertanto possibile convertire `Short` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e850-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="9e850-122">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="9e850-122">**Type Characters.**</span></span> <span data-ttu-id="9e850-123">Aggiungendo il carattere di tipo letterale `S` a un valore letterale, se ne determina la conversione nel tipo di dati `Short`.</span><span class="sxs-lookup"><span data-stu-id="9e850-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="9e850-124">`Short`non ha un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="9e850-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="9e850-125">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="9e850-125">**Framework Type.**</span></span> <span data-ttu-id="9e850-126">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e850-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e850-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e850-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="9e850-128">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9e850-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="9e850-129">CString</span><span class="sxs-lookup"><span data-stu-id="9e850-129">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="9e850-130">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="9e850-130">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="9e850-131">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="9e850-131">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="9e850-132">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="9e850-132">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="9e850-133">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9e850-133">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
