---
title: Tipo di dati SByte (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
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
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="a6265-102">Tipo di dati SByte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6265-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="a6265-103">Contiene valori integer a 8 bit (1-byte) in un intervallo compreso tra -128 e 127.</span><span class="sxs-lookup"><span data-stu-id="a6265-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6265-104">Note</span><span class="sxs-lookup"><span data-stu-id="a6265-104">Remarks</span></span>

<span data-ttu-id="a6265-105">Utilizzare il `SByte` il tipo di dati per contenere i valori integer che non richiedono l'ampiezza dei dati completo `Integer` o anche l'ampiezza dei dati metà `Short`.</span><span class="sxs-lookup"><span data-stu-id="a6265-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="a6265-106">In alcuni casi, potrebbe essere in grado di pack common language runtime il `SByte` variabili e ridurre il consumo di memoria.</span><span class="sxs-lookup"><span data-stu-id="a6265-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="a6265-107">Il valore predefinito di `SByte` è 0.</span><span class="sxs-lookup"><span data-stu-id="a6265-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="a6265-108">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="a6265-108">Literal assignments</span></span>
  
<span data-ttu-id="a6265-109">È possibile dichiarare e inizializzare un `SByte` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="a6265-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="a6265-110">Nell'esempio seguente, i numeri interi uguale a-102 rappresentati come decimali, esadecimali, e valori letterali binari vengono assegnati a `SByte` valori.</span><span class="sxs-lookup"><span data-stu-id="a6265-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="a6265-111">In questo esempio richiede la compilazione con il `/removeintchecks` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a6265-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="a6265-112">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="a6265-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a6265-113">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="a6265-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a6265-114">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="a6265-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="a6265-115">Se il valore letterale integer è esterno all'intervallo di `SByte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.SByte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a6265-115">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="a6265-116">Quando un valore letterale integer non ha alcun suffisso, un [intero](integer-data-type.md) è dedotto.</span><span class="sxs-lookup"><span data-stu-id="a6265-116">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="a6265-117">Se il valore letterale integer è compreso nell'intervallo del `Integer` tipo, un [lungo](long-data-type.md) è dedotto.</span><span class="sxs-lookup"><span data-stu-id="a6265-117">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="a6265-118">Ciò significa che, negli esempi precedenti, i valori letterali numerici `0x9A` e `0b10011010` vengono interpretati come interi con segno a 32 bit con un valore di 156, che supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6265-118">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a6265-119">Per la corretta compilazione di codice simile al seguente che assegna un intero decimale non a un `SByte`, è possibile effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6265-119">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="a6265-120">Disabilitare i controlli dei limiti integer per la compilazione con il `/removeintchecks` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a6265-120">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="a6265-121">Utilizzare un [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) definire in modo esplicito il valore letterale che si desidera assegnare il `SByte`.</span><span class="sxs-lookup"><span data-stu-id="a6265-121">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="a6265-122">Nell'esempio seguente viene assegnato un valore negativo letterale `Short` valore un `SByte`.</span><span class="sxs-lookup"><span data-stu-id="a6265-122">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="a6265-123">Si noti che, per i numeri negativi, è necessario impostare il bit più significativo della parola significativa del valore letterale numerico.</span><span class="sxs-lookup"><span data-stu-id="a6265-123">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="a6265-124">Nel caso di questo esempio, questo è di tipo bit 15 del valore letterale `Short` valore.</span><span class="sxs-lookup"><span data-stu-id="a6265-124">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="a6265-125">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="a6265-125">Programming tips</span></span>
  
-   <span data-ttu-id="a6265-126">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="a6265-126">**CLS Compliance.**</span></span> <span data-ttu-id="a6265-127">Il `SByte` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.</span><span class="sxs-lookup"><span data-stu-id="a6265-127">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="a6265-128">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="a6265-128">**Widening.**</span></span> <span data-ttu-id="a6265-129">Il `SByte` può ampliarsi nel tipo di dati `Short`, `Integer`, `Long`, `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="a6265-129">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="a6265-130">È pertanto possibile convertire `SByte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="a6265-130">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="a6265-131">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="a6265-131">**Type Characters.**</span></span> <span data-ttu-id="a6265-132">`SByte`non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="a6265-132">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="a6265-133">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="a6265-133">**Framework Type.**</span></span> <span data-ttu-id="a6265-134">Il tipo corrispondente in .NET Framework è la struttura <xref:System.SByte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6265-134">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6265-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6265-135">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="a6265-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a6265-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a6265-137">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="a6265-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a6265-138">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="a6265-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="a6265-139">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="a6265-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="a6265-140">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="a6265-140">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="a6265-141">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="a6265-141">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="a6265-142">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a6265-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
