---
title: int (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: 95ac267bc70d2e7873593c08e0b10cb50fefd8c8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421963"
---
# <a name="int-c-reference"></a><span data-ttu-id="78af8-102">int (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="78af8-102">int (C# Reference)</span></span>

<span data-ttu-id="78af8-103">`int` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="78af8-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="78af8-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="78af8-104">Type</span></span>|<span data-ttu-id="78af8-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="78af8-105">Range</span></span>|<span data-ttu-id="78af8-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="78af8-106">Size</span></span>|<span data-ttu-id="78af8-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="78af8-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`int`|<span data-ttu-id="78af8-108">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="78af8-108">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="78af8-109">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="78af8-109">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="78af8-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="78af8-110">Literals</span></span>  
 
<span data-ttu-id="78af8-111">È possibile dichiarare e inizializzare una variabile `int` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="78af8-111">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="78af8-112">Se il valore letterale integer è esterno all'intervallo di `int`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="78af8-112">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="78af8-113">Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `int`.</span><span class="sxs-lookup"><span data-stu-id="78af8-113">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="78af8-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="78af8-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="78af8-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="78af8-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="78af8-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="78af8-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="78af8-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="78af8-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="78af8-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="78af8-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="78af8-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="78af8-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="78af8-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="78af8-120">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="78af8-121">I valori letterali integer possono includere anche un suffisso che denoti il tipo, anche se non è disponibile alcun suffisso che denoti il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="78af8-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="78af8-122">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="78af8-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="78af8-123">uint</span><span class="sxs-lookup"><span data-stu-id="78af8-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="78af8-124">long</span><span class="sxs-lookup"><span data-stu-id="78af8-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="78af8-125">ulong</span><span class="sxs-lookup"><span data-stu-id="78af8-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="78af8-126">In questi esempi il valore letterale 90946 è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="78af8-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="78af8-127">Conversioni</span><span class="sxs-lookup"><span data-stu-id="78af8-127">Conversions</span></span>  
 <span data-ttu-id="78af8-128">Si verifica una conversione implicita predefinita da `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="78af8-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="78af8-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78af8-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="78af8-130">Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="78af8-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="78af8-131">L'istruzione di assegnazione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast:</span><span class="sxs-lookup"><span data-stu-id="78af8-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="78af8-132">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `int`.</span><span class="sxs-lookup"><span data-stu-id="78af8-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="78af8-133">L'istruzione seguente, ad esempio, genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="78af8-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="78af8-134">Per altre informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="78af8-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="78af8-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="78af8-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78af8-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78af8-136">See Also</span></span>

- <xref:System.Int32>  
- [<span data-ttu-id="78af8-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="78af8-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="78af8-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="78af8-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="78af8-139">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="78af8-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="78af8-140">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="78af8-140">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="78af8-141">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="78af8-141">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="78af8-142">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="78af8-142">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="78af8-143">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="78af8-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
