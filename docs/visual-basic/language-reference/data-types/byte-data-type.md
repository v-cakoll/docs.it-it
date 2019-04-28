---
title: Tipo di dati Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 217778a21fb9f231f448436ca5a68c42e5837566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797007"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="515b3-102">Tipo di dati byte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="515b3-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="515b3-103">Contiene interi senza segno a 8 bit (a 1 byte) in un intervallo compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="515b3-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="515b3-104">Note</span><span class="sxs-lookup"><span data-stu-id="515b3-104">Remarks</span></span>

<span data-ttu-id="515b3-105">Usare il `Byte` tipo di dati per contenere dati binari.</span><span class="sxs-lookup"><span data-stu-id="515b3-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="515b3-106">Il valore predefinito di `Byte` è 0.</span><span class="sxs-lookup"><span data-stu-id="515b3-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="515b3-107">Assegnazioni di valori letterali</span><span class="sxs-lookup"><span data-stu-id="515b3-107">Literal assignments</span></span>

<span data-ttu-id="515b3-108">È possibile dichiarare e inizializzare un `Byte` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="515b3-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="515b3-109">Se il valore letterale integrale non rientra nell'intervallo di un `Byte` (vale a dire, se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> maggiore o uguale <xref:System.Byte.MaxValue?displayProperty=nameWithType>), si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="515b3-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="515b3-110">Nell'esempio seguente, i valori interi uguali a 201 rappresentati come decimali, esadecimali o valori letterali binari vengono convertiti implicitamente dal [Integer](integer-data-type.md) a `byte` valori.</span><span class="sxs-lookup"><span data-stu-id="515b3-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="515b3-111">Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="515b3-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="515b3-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="515b3-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="515b3-113">A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.</span><span class="sxs-lookup"><span data-stu-id="515b3-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="515b3-114">A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale.</span><span class="sxs-lookup"><span data-stu-id="515b3-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="515b3-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="515b3-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="515b3-116">Suggerimenti sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="515b3-116">Programming tips</span></span>

- <span data-ttu-id="515b3-117">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="515b3-117">**Negative Numbers.**</span></span> <span data-ttu-id="515b3-118">Poiché `Byte` è un tipo unsigned, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="515b3-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="515b3-119">Se si usa l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce il tipo `Byte`, Visual Basic consente di convertire l'espressione da `Short` prima.</span><span class="sxs-lookup"><span data-stu-id="515b3-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="515b3-120">**Conversioni di formato.**</span><span class="sxs-lookup"><span data-stu-id="515b3-120">**Format Conversions.**</span></span> <span data-ttu-id="515b3-121">Quando legge o scrive i file di Visual Basic o quando viene chiamato DLL, metodi e proprietà, è possibile convertire automaticamente tra formati di dati.</span><span class="sxs-lookup"><span data-stu-id="515b3-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="515b3-122">Dati binari archiviati in `Byte` variabili e matrici vengono conservati durante le conversioni di formato.</span><span class="sxs-lookup"><span data-stu-id="515b3-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="515b3-123">È consigliabile non usare un `String` variabili per i dati binari, perché il relativo contenuto può essere danneggiato durante la conversione tra formati ANSI e Unicode.</span><span class="sxs-lookup"><span data-stu-id="515b3-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="515b3-124">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="515b3-124">**Widening.**</span></span> <span data-ttu-id="515b3-125">Il `Byte` può ampliarsi nel tipo di dati `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="515b3-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="515b3-126">Ciò significa che è possibile convertire `Byte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="515b3-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="515b3-127">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="515b3-127">**Type Characters.**</span></span> <span data-ttu-id="515b3-128">`Byte` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="515b3-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="515b3-129">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="515b3-129">**Framework Type.**</span></span> <span data-ttu-id="515b3-130">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="515b3-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="515b3-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="515b3-131">Example</span></span>

 <span data-ttu-id="515b3-132">Nell'esempio riportato di seguito `b` è un `Byte` variabile.</span><span class="sxs-lookup"><span data-stu-id="515b3-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="515b3-133">Le istruzioni illustrano l'intervallo della variabile e l'applicazione di operatori di spostamento di bit nello stesso.</span><span class="sxs-lookup"><span data-stu-id="515b3-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="515b3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="515b3-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="515b3-135">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="515b3-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="515b3-136">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="515b3-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="515b3-137">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="515b3-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="515b3-138">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="515b3-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
