---
title: Tipo di dati Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28189ab4ab1a9be9265d1cca020039b5302fb5d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590534"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="dd98c-102">Tipo di dati byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd98c-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="dd98c-103">Contiene interi senza segno a 8 bit (1-byte) in un intervallo compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="dd98c-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd98c-104">Note</span><span class="sxs-lookup"><span data-stu-id="dd98c-104">Remarks</span></span>

<span data-ttu-id="dd98c-105">Utilizzare il `Byte` il tipo di dati per contenere dati binari.</span><span class="sxs-lookup"><span data-stu-id="dd98c-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="dd98c-106">Il valore predefinito di `Byte` è 0.</span><span class="sxs-lookup"><span data-stu-id="dd98c-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="dd98c-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="dd98c-107">Literal assignments</span></span>

<span data-ttu-id="dd98c-108">È possibile dichiarare e inizializzare un `Byte` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="dd98c-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="dd98c-109">Se il valore letterale integrale non rientra nell'intervallo di un `Byte` (ovvero, se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>), si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dd98c-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="dd98c-110">Nell'esempio seguente, i numeri interi uguale a 201 rappresentati come decimali, esadecimali, e valori letterali binari vengono convertiti implicitamente dal [intero](integer-data-type.md) a `byte` valori.</span><span class="sxs-lookup"><span data-stu-id="dd98c-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="dd98c-111">Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="dd98c-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="dd98c-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="dd98c-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="dd98c-113">A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="dd98c-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="dd98c-114">A partire da Visual Basic 15,5, è inoltre possibile utilizzare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre binarie, ottale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="dd98c-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="dd98c-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dd98c-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="dd98c-116">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="dd98c-116">Programming tips</span></span>

-   <span data-ttu-id="dd98c-117">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="dd98c-117">**Negative Numbers.**</span></span> <span data-ttu-id="dd98c-118">Poiché `Byte` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="dd98c-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="dd98c-119">Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `Byte`, Visual Basic converte l'espressione `Short` prima.</span><span class="sxs-lookup"><span data-stu-id="dd98c-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="dd98c-120">**Conversioni di formato.**</span><span class="sxs-lookup"><span data-stu-id="dd98c-120">**Format Conversions.**</span></span> <span data-ttu-id="dd98c-121">Quando legge o scrive i file di Visual Basic o durante la chiamata di DLL, metodi e proprietà, è possibile convertire automaticamente tra formati di dati.</span><span class="sxs-lookup"><span data-stu-id="dd98c-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="dd98c-122">Dati binari archiviati in `Byte` variabili e matrici vengono conservati durante queste conversioni di formato.</span><span class="sxs-lookup"><span data-stu-id="dd98c-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="dd98c-123">Non è consigliabile utilizzare un `String` variabili per i dati binari, perché il relativo contenuto può essere danneggiato durante la conversione tra formati ANSI e Unicode.</span><span class="sxs-lookup"><span data-stu-id="dd98c-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="dd98c-124">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="dd98c-124">**Widening.**</span></span> <span data-ttu-id="dd98c-125">Il `Byte` può ampliarsi nel tipo di dati `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="dd98c-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="dd98c-126">È pertanto possibile convertire `Byte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="dd98c-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="dd98c-127">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="dd98c-127">**Type Characters.**</span></span> <span data-ttu-id="dd98c-128">`Byte` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="dd98c-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="dd98c-129">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="dd98c-129">**Framework Type.**</span></span> <span data-ttu-id="dd98c-130">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd98c-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="dd98c-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd98c-131">Example</span></span>

 <span data-ttu-id="dd98c-132">Nell'esempio seguente, `b` è un `Byte` variabile.</span><span class="sxs-lookup"><span data-stu-id="dd98c-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="dd98c-133">Le istruzioni illustrano l'intervallo della variabile e l'applicazione degli operatori di spostamento di bit a esso.</span><span class="sxs-lookup"><span data-stu-id="dd98c-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="dd98c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd98c-134">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="dd98c-135">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="dd98c-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="dd98c-136">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="dd98c-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="dd98c-137">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="dd98c-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="dd98c-138">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="dd98c-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
