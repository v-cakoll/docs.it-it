---
title: int (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
dev_langs:
- CSharp
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 935428cc9442a3e1d15eeb8942176c237bff4e22
ms.openlocfilehash: 6e87893bcd9800b61297e71b782028fec5116479
ms.contentlocale: it-it
ms.lasthandoff: 08/22/2017

---
# <a name="int-c-reference"></a><span data-ttu-id="5db72-102">int (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5db72-102">int (C# Reference)</span></span>

<span data-ttu-id="5db72-103">`int` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5db72-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="5db72-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="5db72-104">Type</span></span>|<span data-ttu-id="5db72-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="5db72-105">Range</span></span>|<span data-ttu-id="5db72-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="5db72-106">Size</span></span>|<span data-ttu-id="5db72-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5db72-107">.NET Framework type</span></span>|<span data-ttu-id="5db72-108">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="5db72-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="5db72-109">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="5db72-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="5db72-110">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="5db72-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=fullName>|<span data-ttu-id="5db72-111">0</span><span class="sxs-lookup"><span data-stu-id="5db72-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="5db72-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="5db72-112">Literals</span></span>  
 
<span data-ttu-id="5db72-113">È possibile dichiarare e inizializzare una variabile `int` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="5db72-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="5db72-114">Se il valore letterale integer è esterno all'intervallo di `int`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=fullName> o maggiore di <xref:System.Int32.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5db72-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=fullName> or greater than <xref:System.Int32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="5db72-115">Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `int`.</span><span class="sxs-lookup"><span data-stu-id="5db72-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
<span data-ttu-id="5db72-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span><span class="sxs-lookup"><span data-stu-id="5db72-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="5db72-117">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="5db72-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="5db72-118">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="5db72-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="5db72-119">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5db72-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="5db72-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span><span class="sxs-lookup"><span data-stu-id="5db72-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span></span>  
 
 <span data-ttu-id="5db72-121">I valori letterali integer possono includere anche un suffisso che denoti il tipo, anche se non è disponibile alcun suffisso che denoti il tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="5db72-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="5db72-122">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="5db72-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="5db72-123">uint</span><span class="sxs-lookup"><span data-stu-id="5db72-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="5db72-124">long</span><span class="sxs-lookup"><span data-stu-id="5db72-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="5db72-125">ulong</span><span class="sxs-lookup"><span data-stu-id="5db72-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="5db72-126">In questi esempi il valore letterale 90946 è di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="5db72-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="5db72-127">Conversioni</span><span class="sxs-lookup"><span data-stu-id="5db72-127">Conversions</span></span>  
 <span data-ttu-id="5db72-128">Si verifica una conversione implicita predefinita da `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="5db72-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="5db72-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5db72-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="5db72-130">Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="5db72-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="5db72-131">L'istruzione di assegnazione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast:</span><span class="sxs-lookup"><span data-stu-id="5db72-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5db72-132">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `int`.</span><span class="sxs-lookup"><span data-stu-id="5db72-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="5db72-133">L'istruzione seguente, ad esempio, genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="5db72-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5db72-134">Per altre informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="5db72-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5db72-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5db72-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5db72-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5db72-136">See Also</span></span>  
 <span data-ttu-id="5db72-137"><xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="5db72-137"><xref:System.Int32></span></span>   
 <span data-ttu-id="5db72-138">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5db72-139">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5db72-140">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5db72-141">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="5db72-142">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="5db72-143">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="5db72-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="5db72-144">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="5db72-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

