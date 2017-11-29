---
title: Tipo di dati UShort (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ushort
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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513e8ce4694788d33c5aa14e34b95e88b6d37ff1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="3dce7-102">Tipo di dati UShort (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dce7-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="3dce7-103">Contiene interi senza segno a 16 bit (2 byte) nell'intervallo compreso tra 0 e 65.535.</span><span class="sxs-lookup"><span data-stu-id="3dce7-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dce7-104">Note</span><span class="sxs-lookup"><span data-stu-id="3dce7-104">Remarks</span></span>

 <span data-ttu-id="3dce7-105">Utilizzare il `UShort` il tipo di dati per contenere dati binari troppo grandi per `Byte`.</span><span class="sxs-lookup"><span data-stu-id="3dce7-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="3dce7-106">Il valore predefinito di `UShort` è 0.</span><span class="sxs-lookup"><span data-stu-id="3dce7-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="3dce7-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="3dce7-107">Literal assignments</span></span>

<span data-ttu-id="3dce7-108">È possibile dichiarare e inizializzare un `UShort` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="3dce7-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="3dce7-109">Se il valore letterale integer è esterno all'intervallo di `UShort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3dce7-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="3dce7-110">Nell'esempio seguente, i numeri interi uguale a 65,034 rappresentati come decimali, esadecimali, e valori letterali binari vengono assegnati a `UShort` valori.</span><span class="sxs-lookup"><span data-stu-id="3dce7-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="3dce7-111">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="3dce7-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="3dce7-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="3dce7-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="3dce7-113">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="3dce7-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="3dce7-114">Valori letterali numerici possono includere anche il `US` o `us` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `UShort` il tipo di dati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3dce7-114">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H035826us
```

## <a name="programming-tips"></a><span data-ttu-id="3dce7-115">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="3dce7-115">Programming tips</span></span>
  
-   <span data-ttu-id="3dce7-116">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="3dce7-116">**Negative Numbers.**</span></span> <span data-ttu-id="3dce7-117">Poiché `UShort` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="3dce7-117">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="3dce7-118">Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `UShort`, Visual Basic converte l'espressione `Integer` prima.</span><span class="sxs-lookup"><span data-stu-id="3dce7-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="3dce7-119">**Conformità a CLS.**</span><span class="sxs-lookup"><span data-stu-id="3dce7-119">**CLS Compliance.**</span></span> <span data-ttu-id="3dce7-120">Il `UShort` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.</span><span class="sxs-lookup"><span data-stu-id="3dce7-120">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="3dce7-121">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="3dce7-121">**Widening.**</span></span> <span data-ttu-id="3dce7-122">Il `UShort` può ampliarsi nel tipo di dati `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, e `Double`.</span><span class="sxs-lookup"><span data-stu-id="3dce7-122">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="3dce7-123">È pertanto possibile convertire `UShort` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="3dce7-123">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="3dce7-124">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="3dce7-124">**Type Characters.**</span></span> <span data-ttu-id="3dce7-125">Aggiungendo i caratteri di tipo letterale `US` a un valore letterale indica al sistema di `UShort` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3dce7-125">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="3dce7-126">`UShort`non include alcun carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="3dce7-126">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="3dce7-127">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="3dce7-127">**Framework Type.**</span></span> <span data-ttu-id="3dce7-128">Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt16?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3dce7-128">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dce7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dce7-129">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="3dce7-130">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3dce7-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="3dce7-131">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="3dce7-131">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="3dce7-132">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="3dce7-132">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="3dce7-133">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="3dce7-133">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="3dce7-134">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3dce7-134">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
