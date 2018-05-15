---
title: int (Riferimenti per C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f3e82dd195252a8c55e4ba7b18b657b341553047
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="int-c-reference"></a><span data-ttu-id="b0b7e-102">int (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b0b7e-102">int (C# Reference)</span></span>

<span data-ttu-id="b0b7e-103">`int` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="b0b7e-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0b7e-104">Type</span></span>|<span data-ttu-id="b0b7e-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="b0b7e-105">Range</span></span>|<span data-ttu-id="b0b7e-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="b0b7e-106">Size</span></span>|<span data-ttu-id="b0b7e-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b0b7e-107">.NET Framework type</span></span>|<span data-ttu-id="b0b7e-108">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="b0b7e-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="b0b7e-109">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="b0b7e-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="b0b7e-110">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="b0b7e-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="b0b7e-111">0</span><span class="sxs-lookup"><span data-stu-id="b0b7e-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="b0b7e-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="b0b7e-112">Literals</span></span>  
 
<span data-ttu-id="b0b7e-113">È possibile dichiarare e inizializzare una variabile `int` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="b0b7e-114">Se il valore letterale integer è esterno all'intervallo di `int`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="b0b7e-115">Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `int`.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="b0b7e-116">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="b0b7e-117">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="b0b7e-118">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="b0b7e-119">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="b0b7e-120">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="b0b7e-121">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="b0b7e-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="b0b7e-123">I valori letterali integer possono includere anche un suffisso che denoti il tipo, anche se non è disponibile alcun suffisso che denoti il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="b0b7e-124">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="b0b7e-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="b0b7e-125">uint</span><span class="sxs-lookup"><span data-stu-id="b0b7e-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="b0b7e-126">long</span><span class="sxs-lookup"><span data-stu-id="b0b7e-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="b0b7e-127">ulong</span><span class="sxs-lookup"><span data-stu-id="b0b7e-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="b0b7e-128">In questi esempi il valore letterale 90946 è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="b0b7e-129">Conversioni</span><span class="sxs-lookup"><span data-stu-id="b0b7e-129">Conversions</span></span>  
 <span data-ttu-id="b0b7e-130">Si verifica una conversione implicita predefinita da `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="b0b7e-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="b0b7e-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0b7e-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="b0b7e-132">Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="b0b7e-133">L'istruzione di assegnazione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast:</span><span class="sxs-lookup"><span data-stu-id="b0b7e-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="b0b7e-134">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `int`.</span><span class="sxs-lookup"><span data-stu-id="b0b7e-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="b0b7e-135">L'istruzione seguente, ad esempio, genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="b0b7e-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="b0b7e-136">Per altre informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="b0b7e-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b0b7e-137">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b0b7e-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b7e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0b7e-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="b0b7e-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b0b7e-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b0b7e-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b0b7e-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0b7e-141">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b0b7e-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b0b7e-142">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="b0b7e-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="b0b7e-143">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="b0b7e-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="b0b7e-144">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="b0b7e-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="b0b7e-145">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="b0b7e-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
