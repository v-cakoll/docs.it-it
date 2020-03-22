---
title: Tipo di dati UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400785"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="beb0b-102">UInteger (tipo di dati)</span><span class="sxs-lookup"><span data-stu-id="beb0b-102">UInteger data type</span></span>

<span data-ttu-id="beb0b-103">Contiene interi senza segno a 32 bit (4 byte) compresi in un valore compreso tra 0 e 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="beb0b-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="beb0b-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="beb0b-104">Remarks</span></span>

<span data-ttu-id="beb0b-105">Il `UInteger` tipo di dati fornisce il valore senza segno più grande nella larghezza dei dati più efficiente.</span><span class="sxs-lookup"><span data-stu-id="beb0b-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="beb0b-106">Il valore predefinito di `UInteger` è 0.</span><span class="sxs-lookup"><span data-stu-id="beb0b-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="beb0b-107">Assegnazioni letterali</span><span class="sxs-lookup"><span data-stu-id="beb0b-107">Literal assignments</span></span>

<span data-ttu-id="beb0b-108">È possibile dichiarare `UInteger` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="beb0b-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="beb0b-109">Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="beb0b-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="beb0b-110">Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="beb0b-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="beb0b-111">Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="beb0b-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="beb0b-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="beb0b-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="beb0b-113">A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="beb0b-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="beb0b-114">A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="beb0b-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="beb0b-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="beb0b-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="beb0b-116">I valori letterali `UI` numerici possono includere anche il `ui` [carattere](../../programming-guide/language-features/data-types/type-characters.md) di tipo o per indicare il `UInteger` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="beb0b-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="beb0b-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="beb0b-117">Programming tips</span></span>

<span data-ttu-id="beb0b-118">I `UInteger` `Integer` tipi di dati e offrono prestazioni ottimali su un`UShort`processore `Short` `Byte`a `SByte`32 bit, poiché i tipi Integer più piccoli ( , , e ), anche se utilizzano meno bit, richiedono più tempo per il caricamento, l'archiviazione e il recupero.</span><span class="sxs-lookup"><span data-stu-id="beb0b-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="beb0b-119">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-119">**Negative Numbers.**</span></span> <span data-ttu-id="beb0b-120">Poiché `UInteger` è un tipo senza segno, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="beb0b-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="beb0b-121">Se si utilizza l'operatore meno unario (`-` `UInteger`) su un'espressione `Long` che restituisce type , Visual Basic converte l'espressione in prima.</span><span class="sxs-lookup"><span data-stu-id="beb0b-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="beb0b-122">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-122">**CLS Compliance.**</span></span> <span data-ttu-id="beb0b-123">Il `UInteger` tipo di dati non fa parte di [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="beb0b-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="beb0b-124">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-124">**Interop Considerations.**</span></span> <span data-ttu-id="beb0b-125">Se si interagisce con componenti non scritti per .NET Framework, ad esempio oggetti `uint` COM o di automazione, tenere presente che tipi quali possono avere una larghezza di dati diversa (16 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="beb0b-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="beb0b-126">Se si passa un argomento a 16 bit a `UShort` un `UInteger` componente di questo tipo, dichiararlo come anziché nel codice Visual Basic gestito.</span><span class="sxs-lookup"><span data-stu-id="beb0b-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="beb0b-127">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-127">**Widening.**</span></span> <span data-ttu-id="beb0b-128">Il `UInteger` tipo di `Long`dati `ULong` `Decimal`si `Single`allarga a , , , , e `Double`.</span><span class="sxs-lookup"><span data-stu-id="beb0b-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="beb0b-129">Ciò significa `UInteger` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.</span><span class="sxs-lookup"><span data-stu-id="beb0b-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="beb0b-130">**Digitare caratteri.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-130">**Type Characters.**</span></span> <span data-ttu-id="beb0b-131">L'aggiunta dei `UI` caratteri di tipo letterale a un valore letterale lo forza al tipo di `UInteger` dati.</span><span class="sxs-lookup"><span data-stu-id="beb0b-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="beb0b-132">`UInteger`non ha alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="beb0b-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="beb0b-133">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="beb0b-133">**Framework Type.**</span></span> <span data-ttu-id="beb0b-134">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="beb0b-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="beb0b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="beb0b-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="beb0b-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="beb0b-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="beb0b-137">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="beb0b-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="beb0b-138">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="beb0b-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="beb0b-139">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="beb0b-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="beb0b-140">Utilizzo efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="beb0b-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
