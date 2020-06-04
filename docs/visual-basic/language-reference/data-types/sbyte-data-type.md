---
title: Tipo di dati SByte
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: e7d45c74056ce5b6aa66674c99e48b5ab60015f0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415570"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="6d420-102">Tipo di dati SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d420-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="6d420-103">Include interi con segno a 8 bit (1 byte) compresi tra-128 e 127.</span><span class="sxs-lookup"><span data-stu-id="6d420-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d420-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="6d420-104">Remarks</span></span>

<span data-ttu-id="6d420-105">Utilizzare il `SByte` tipo di dati per contenere valori integer che non richiedono la larghezza dei dati completa di `Integer` o persino la lunghezza della metà dei dati di `Short` .</span><span class="sxs-lookup"><span data-stu-id="6d420-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="6d420-106">In alcuni casi, il Common Language Runtime potrebbe essere in grado di comprimere le variabili in modo `SByte` stretto e di risparmiare sull'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="6d420-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="6d420-107">Il valore predefinito di `SByte` è 0.</span><span class="sxs-lookup"><span data-stu-id="6d420-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="6d420-108">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="6d420-108">Literal assignments</span></span>

<span data-ttu-id="6d420-109">È possibile dichiarare e inizializzare una `SByte` variabile assegnandogli un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="6d420-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="6d420-110">Nell'esempio seguente, i numeri interi uguali a-102 rappresentati come valori letterali decimali, esadecimali e binari vengono assegnati ai `SByte` valori.</span><span class="sxs-lookup"><span data-stu-id="6d420-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="6d420-111">Questo esempio richiede la compilazione con l' `/removeintchecks` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6d420-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="6d420-112">Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="6d420-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="6d420-113">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="6d420-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="6d420-114">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6d420-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="6d420-115">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="6d420-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6d420-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6d420-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="6d420-117">Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6d420-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="6d420-118">Quando un valore letterale integer non ha alcun suffisso, viene dedotto un [valore integer](integer-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="6d420-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="6d420-119">Se il valore letterale integer non è compreso nell'intervallo del `Integer` tipo, viene dedotto un valore [Long](long-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="6d420-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="6d420-120">Ciò significa che, negli esempi precedenti, i valori letterali numerici `0x9A` e `0b10011010` vengono interpretati come interi con segno a 32 bit con un valore di 156, che supera <xref:System.SByte.MaxValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6d420-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6d420-121">Per compilare correttamente codice simile a questo che assegna un Integer non decimale a un `SByte` , è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d420-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="6d420-122">Disabilitare i controlli dei limiti Integer compilando con l' `/removeintchecks` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6d420-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="6d420-123">Usare un [carattere tipo](../../programming-guide/language-features/data-types/type-characters.md) per definire in modo esplicito il valore letterale che si vuole assegnare a `SByte` .</span><span class="sxs-lookup"><span data-stu-id="6d420-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="6d420-124">Nell'esempio seguente viene assegnato un valore letterale negativo `Short` a un oggetto `SByte` .</span><span class="sxs-lookup"><span data-stu-id="6d420-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="6d420-125">Si noti che, per i numeri negativi, è necessario impostare il bit più significativo della parola più ordinata del valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="6d420-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="6d420-126">Nel caso dell'esempio, si tratta del bit 15 del valore letterale `Short` .</span><span class="sxs-lookup"><span data-stu-id="6d420-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="6d420-127">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="6d420-127">Programming tips</span></span>

- <span data-ttu-id="6d420-128">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="6d420-128">**CLS Compliance.**</span></span> <span data-ttu-id="6d420-129">Il `SByte` tipo di dati non fa parte del [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="6d420-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="6d420-130">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="6d420-130">**Widening.**</span></span> <span data-ttu-id="6d420-131">Il `SByte` tipo di dati viene ampliato in `Short` , `Integer` , `Long` , `Decimal` , `Single` e `Double` .</span><span class="sxs-lookup"><span data-stu-id="6d420-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="6d420-132">Ciò significa che è possibile `SByte` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="6d420-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="6d420-133">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="6d420-133">**Type Characters.**</span></span> <span data-ttu-id="6d420-134">`SByte`non ha un carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="6d420-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="6d420-135">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="6d420-135">**Framework Type.**</span></span> <span data-ttu-id="6d420-136">Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6d420-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d420-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d420-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="6d420-138">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6d420-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="6d420-139">CString</span><span class="sxs-lookup"><span data-stu-id="6d420-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="6d420-140">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="6d420-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="6d420-141">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="6d420-141">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="6d420-142">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="6d420-142">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="6d420-143">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="6d420-143">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="6d420-144">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6d420-144">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
