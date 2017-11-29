---
title: Tipo di dati UInteger
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
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
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a><span data-ttu-id="125b4-102">UInteger (tipo di dati)</span><span class="sxs-lookup"><span data-stu-id="125b4-102">UInteger data type</span></span>

<span data-ttu-id="125b4-103">Contiene interi senza segno a 32 bit (4 byte) nell'intervallo compreso tra 0 e 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="125b4-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="125b4-104">Note</span><span class="sxs-lookup"><span data-stu-id="125b4-104">Remarks</span></span>

 <span data-ttu-id="125b4-105">Il `UInteger` tipo di dati fornisce il valore senza segno maggiore larghezza di dati più efficiente.</span><span class="sxs-lookup"><span data-stu-id="125b4-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="125b4-106">Il valore predefinito di `UInteger` è 0.</span><span class="sxs-lookup"><span data-stu-id="125b4-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="125b4-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="125b4-107">Literal assignments</span></span>

<span data-ttu-id="125b4-108">È possibile dichiarare e inizializzare un `UInteger` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="125b4-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="125b4-109">Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="125b4-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="125b4-110">Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="125b4-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="125b4-111">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="125b4-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="125b4-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="125b4-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="125b4-113">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="125b4-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="125b4-114">Valori letterali numerici possono includere anche il `UI` o `ui` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `UInteger` il tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="125b4-114">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="125b4-115">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="125b4-115">Programming tips</span></span>

 <span data-ttu-id="125b4-116">Il `UInteger` e `Integer` tipi di dati forniscono prestazioni ottimali in un processore a 32 bit, poiché i tipi integer più piccolo (`UShort`, `Short`, `Byte`, e `SByte`), anche se utilizzano un numero inferiore di bits, richiedono più tempo caricare, archiviare e recuperare.</span><span class="sxs-lookup"><span data-stu-id="125b4-116">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="125b4-117">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="125b4-117">**Negative Numbers.**</span></span> <span data-ttu-id="125b4-118">Poiché `UInteger` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="125b4-118">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="125b4-119">Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `UInteger`, Visual Basic converte l'espressione `Long` prima.</span><span class="sxs-lookup"><span data-stu-id="125b4-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="125b4-120">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="125b4-120">**CLS Compliance.**</span></span> <span data-ttu-id="125b4-121">Il `UInteger` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.</span><span class="sxs-lookup"><span data-stu-id="125b4-121">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="125b4-122">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="125b4-122">**Interop Considerations.**</span></span> <span data-ttu-id="125b4-123">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `uint` può avere un'ampiezza dei dati diversa (16 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="125b4-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="125b4-124">Se si passa un argomento a 16 bit a tale componente, dichiararla come `UShort` anziché `UInteger` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="125b4-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="125b4-125">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="125b4-125">**Widening.**</span></span> <span data-ttu-id="125b4-126">Il `UInteger` può ampliarsi nel tipo di dati `Long`, `ULong`, `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="125b4-126">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="125b4-127">È pertanto possibile convertire `UInteger` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="125b4-127">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="125b4-128">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="125b4-128">**Type Characters.**</span></span> <span data-ttu-id="125b4-129">Aggiungendo i caratteri di tipo letterale `UI` a un valore letterale indica al sistema di `UInteger` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="125b4-129">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="125b4-130">`UInteger`non include alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="125b4-130">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="125b4-131">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="125b4-131">**Framework Type.**</span></span> <span data-ttu-id="125b4-132">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="125b4-132">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125b4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="125b4-133">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="125b4-134">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="125b4-134">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="125b4-135">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="125b4-135">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="125b4-136">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="125b4-136">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="125b4-137">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="125b4-137">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="125b4-138">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="125b4-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
