---
title: Tipo di dati Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400743"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="cf522-102">Byte data type (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf522-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="cf522-103">Contiene interi senza segno a 8 bit (1 byte) compresi in un valore compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="cf522-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf522-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cf522-104">Remarks</span></span>

<span data-ttu-id="cf522-105">Utilizzare `Byte` il tipo di dati per contenere dati binari.</span><span class="sxs-lookup"><span data-stu-id="cf522-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="cf522-106">Il valore predefinito di `Byte` è 0.</span><span class="sxs-lookup"><span data-stu-id="cf522-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="cf522-107">Assegnazioni letterali</span><span class="sxs-lookup"><span data-stu-id="cf522-107">Literal assignments</span></span>

<span data-ttu-id="cf522-108">È possibile dichiarare `Byte` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="cf522-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="cf522-109">Se il valore letterale integrale non è compreso nell'intervallo di un `Byte` oggetto , ovvero se è minore <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cf522-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="cf522-110">Nell'esempio seguente, i numeri interi uguali a 201 rappresentati come valori letterali decimali, esadecimali e binari vengono convertiti in modo implicito da [Integer](integer-data-type.md) a `byte` valori.</span><span class="sxs-lookup"><span data-stu-id="cf522-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="cf522-111">Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale.</span><span class="sxs-lookup"><span data-stu-id="cf522-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="cf522-112">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="cf522-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="cf522-113">A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cf522-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="cf522-114">A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="cf522-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="cf522-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf522-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="cf522-116">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="cf522-116">Programming tips</span></span>

- <span data-ttu-id="cf522-117">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="cf522-117">**Negative Numbers.**</span></span> <span data-ttu-id="cf522-118">Poiché `Byte` è un tipo senza segno, non può rappresentare un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="cf522-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="cf522-119">Se si utilizza l'operatore meno unario (`-` `Byte`) su un'espressione `Short` che restituisce type , Visual Basic converte l'espressione in prima.</span><span class="sxs-lookup"><span data-stu-id="cf522-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="cf522-120">**Conversioni di formato.**</span><span class="sxs-lookup"><span data-stu-id="cf522-120">**Format Conversions.**</span></span> <span data-ttu-id="cf522-121">Quando Visual Basic legge o scrive file o quando chiama DLL, metodi e proprietà, è possibile eseguire automaticamente la conversione tra i formati di dati.</span><span class="sxs-lookup"><span data-stu-id="cf522-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="cf522-122">I dati `Byte` binari archiviati in variabili e matrici vengono mantenuti durante tali conversioni di formato.</span><span class="sxs-lookup"><span data-stu-id="cf522-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="cf522-123">Non utilizzare una `String` variabile per i dati binari, perché il suo contenuto può essere danneggiato durante la conversione tra i formati ANSI e Unicode.</span><span class="sxs-lookup"><span data-stu-id="cf522-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="cf522-124">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="cf522-124">**Widening.**</span></span> <span data-ttu-id="cf522-125">Il `Byte` tipo di `Short`dati `UShort` `Integer`si `UInteger` `Long`allarga a , , , , `ULong`, `Decimal` `Single`, o `Double`.</span><span class="sxs-lookup"><span data-stu-id="cf522-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="cf522-126">Ciò significa `Byte` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.</span><span class="sxs-lookup"><span data-stu-id="cf522-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="cf522-127">**Digitare caratteri.**</span><span class="sxs-lookup"><span data-stu-id="cf522-127">**Type Characters.**</span></span> <span data-ttu-id="cf522-128">`Byte`non dispone di alcun carattere di tipo letterale o tipo di identificatore.</span><span class="sxs-lookup"><span data-stu-id="cf522-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="cf522-129">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="cf522-129">**Framework Type.**</span></span> <span data-ttu-id="cf522-130">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cf522-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="cf522-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf522-131">Example</span></span>

 <span data-ttu-id="cf522-132">Nell'esempio seguente, `b` `Byte` è una variabile.</span><span class="sxs-lookup"><span data-stu-id="cf522-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="cf522-133">Le istruzioni illustrano l'intervallo della variabile e l'applicazione di operatori di spostamento di bit.</span><span class="sxs-lookup"><span data-stu-id="cf522-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="cf522-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf522-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="cf522-135">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="cf522-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cf522-136">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="cf522-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cf522-137">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="cf522-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="cf522-138">Utilizzo efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="cf522-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
