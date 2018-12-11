---
title: Tipo di dati UInteger (Visual Basic)
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
ms.openlocfilehash: c63b9a25c1830f142002e9854e9ce275f55ef54b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154820"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="5f481-102">UInteger (tipo di dati)</span><span class="sxs-lookup"><span data-stu-id="5f481-102">UInteger data type</span></span>

<span data-ttu-id="5f481-103">Contiene valori integer a 32 bit (4 byte) senza segno compresi nell'intervallo compreso tra 0 e 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="5f481-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f481-104">Note</span><span class="sxs-lookup"><span data-stu-id="5f481-104">Remarks</span></span>

 <span data-ttu-id="5f481-105">Il `UInteger` tipo di dati fornisce il valore senza segno massimo alla larghezza di dati più efficiente.</span><span class="sxs-lookup"><span data-stu-id="5f481-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="5f481-106">Il valore predefinito di `UInteger` è 0.</span><span class="sxs-lookup"><span data-stu-id="5f481-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="5f481-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="5f481-107">Literal assignments</span></span>

<span data-ttu-id="5f481-108">È possibile dichiarare e inizializzare un `UInteger` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="5f481-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5f481-109">Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5f481-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5f481-110">Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="5f481-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="5f481-111">Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="5f481-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5f481-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="5f481-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5f481-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="5f481-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="5f481-114">A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale.</span><span class="sxs-lookup"><span data-stu-id="5f481-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5f481-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5f481-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5f481-116">Valori letterali numerici possono includere anche il `UI` o `ui` [Digita carattere](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `UInteger` tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5f481-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="5f481-117">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="5f481-117">Programming tips</span></span>

 <span data-ttu-id="5f481-118">Il `UInteger` e `Integer` tipi di dati forniscono prestazioni ottimali su un processore a 32 bit, poiché i tipi interi più piccoli (`UShort`, `Short`, `Byte`, e `SByte`), anche se usano un minor numero di bit, richiedono più tempo caricare, archiviare e recuperare.</span><span class="sxs-lookup"><span data-stu-id="5f481-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="5f481-119">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="5f481-119">**Negative Numbers.**</span></span> <span data-ttu-id="5f481-120">Poiché `UInteger` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="5f481-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5f481-121">Se si usa l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce il tipo `UInteger`, Visual Basic consente di convertire l'espressione da `Long` prima.</span><span class="sxs-lookup"><span data-stu-id="5f481-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="5f481-122">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="5f481-122">**CLS Compliance.**</span></span> <span data-ttu-id="5f481-123">Il `UInteger` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che lo usa.</span><span class="sxs-lookup"><span data-stu-id="5f481-123">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="5f481-124">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="5f481-124">**Interop Considerations.**</span></span> <span data-ttu-id="5f481-125">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `uint` può avere un'ampiezza dei dati diversa (16 bit) in altri ambienti.</span><span class="sxs-lookup"><span data-stu-id="5f481-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="5f481-126">Se si passa un argomento a 16 bit a un componente, dichiararlo come `UShort` invece di `UInteger` nel codice gestito di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f481-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="5f481-127">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="5f481-127">**Widening.**</span></span> <span data-ttu-id="5f481-128">Il `UInteger` può ampliarsi nel tipo di dati `Long`, `ULong`, `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="5f481-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5f481-129">Ciò significa che è possibile convertire `UInteger` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="5f481-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="5f481-130">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="5f481-130">**Type Characters.**</span></span> <span data-ttu-id="5f481-131">Aggiungendo i caratteri di tipo di valore letterale `UI` a un valore letterale, se ne determina la `UInteger` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5f481-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="5f481-132">`UInteger` possiede alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="5f481-132">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="5f481-133">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="5f481-133">**Framework Type.**</span></span> <span data-ttu-id="5f481-134">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f481-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f481-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f481-135">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="5f481-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="5f481-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="5f481-137">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="5f481-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5f481-138">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="5f481-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="5f481-139">Come si fa: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="5f481-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="5f481-140">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="5f481-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
