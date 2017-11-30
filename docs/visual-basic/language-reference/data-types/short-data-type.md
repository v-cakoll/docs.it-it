---
title: Tipo di dati Short (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
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
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="53380-102">Tipo di dati short (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53380-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="53380-103">Contiene valori integer a 16 bit (2 byte) in un intervallo compreso tra -32.768 e 32.767.</span><span class="sxs-lookup"><span data-stu-id="53380-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53380-104">Note</span><span class="sxs-lookup"><span data-stu-id="53380-104">Remarks</span></span>  
 <span data-ttu-id="53380-105">Utilizzare il `Short` il tipo di dati per contenere i valori integer che non richiedono l'ampiezza dei dati completo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="53380-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="53380-106">In alcuni casi, è possibile comprimere common language runtime il `Short` variabili e ridurre il consumo di memoria.</span><span class="sxs-lookup"><span data-stu-id="53380-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="53380-107">Il valore predefinito di `Short` è 0.</span><span class="sxs-lookup"><span data-stu-id="53380-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="53380-108">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="53380-108">Literal assignments</span></span>

<span data-ttu-id="53380-109">È possibile dichiarare e inizializzare un `Short` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="53380-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="53380-110">Se il valore letterale integer è esterno all'intervallo di `Short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="53380-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="53380-111">Nell'esempio seguente, i numeri interi uguale a 1,034 rappresentati come decimali, esadecimali, e valori letterali binari vengono convertiti implicitamente dal [intero](integer-data-type.md) a `Short` valori.</span><span class="sxs-lookup"><span data-stu-id="53380-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="53380-112">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="53380-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="53380-113">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="53380-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="53380-114">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="53380-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="53380-115">Valori letterali numerici possono includere anche il `S` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `Short` il tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="53380-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="53380-116">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="53380-116">Programming tips</span></span>

-   <span data-ttu-id="53380-117">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="53380-117">**Widening.**</span></span> <span data-ttu-id="53380-118">Il `Short` può ampliarsi nel tipo di dati `Integer`, `Long`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="53380-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="53380-119">È pertanto possibile convertire `Short` in uno di questi tipi senza generare un errore <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53380-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="53380-120">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="53380-120">**Type Characters.**</span></span> <span data-ttu-id="53380-121">Aggiungendo il carattere di tipo letterale `S` a un valore letterale, se ne determina la conversione nel tipo di dati `Short`.</span><span class="sxs-lookup"><span data-stu-id="53380-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="53380-122">`Short`non include alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="53380-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="53380-123">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="53380-123">**Framework Type.**</span></span> <span data-ttu-id="53380-124">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Int16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53380-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53380-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53380-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="53380-126">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="53380-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="53380-127">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="53380-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="53380-128">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="53380-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="53380-129">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="53380-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="53380-130">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="53380-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="53380-131">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="53380-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
