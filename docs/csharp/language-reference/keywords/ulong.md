---
title: ulong (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a><span data-ttu-id="2ed54-102">ulong (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2ed54-102">ulong (C# Reference)</span></span>

<span data-ttu-id="2ed54-103">La parola chiave `ulong` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2ed54-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="2ed54-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="2ed54-104">Type</span></span>|<span data-ttu-id="2ed54-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="2ed54-105">Range</span></span>|<span data-ttu-id="2ed54-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="2ed54-106">Size</span></span>|<span data-ttu-id="2ed54-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ed54-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="2ed54-108">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="2ed54-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="2ed54-109">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2ed54-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="2ed54-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="2ed54-110">Literals</span></span>  

<span data-ttu-id="2ed54-111">È possibile dichiarare e inizializzare una variabile `ulong` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="2ed54-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="2ed54-112">Se il valore letterale integer è esterno all'intervallo di `ulong`, vale a dire se è minore di <xref:System.UInt64.MinValue?displayProperty=fullName> o maggiore di <xref:System.UInt64.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2ed54-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=fullName> or greater than <xref:System.UInt64.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="2ed54-113">Nell'esempio seguente, i valori interi uguali a 7.934.076.125 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `ulong`.</span><span class="sxs-lookup"><span data-stu-id="2ed54-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
<span data-ttu-id="2ed54-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span><span class="sxs-lookup"><span data-stu-id="2ed54-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="2ed54-115">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="2ed54-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="2ed54-116">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="2ed54-116">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="2ed54-117">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2ed54-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="2ed54-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="2ed54-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="2ed54-119">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="2ed54-119">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="2ed54-120">Il suffisso `UL` o `ul` identifica in modo inequivocabile un valore letterale numerico come valore `ulong`.</span><span class="sxs-lookup"><span data-stu-id="2ed54-120">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="2ed54-121">Il suffisso `L` indica `ulong` se il valore letterale supera <xref:System.Int64.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2ed54-121">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="2ed54-122">Il suffisso `U` o `u` indica `ulong` se il valore letterale supera <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2ed54-122">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="2ed54-123">L'esempio seguente usa il suffisso `ul` per indicare un valore long integer:</span><span class="sxs-lookup"><span data-stu-id="2ed54-123">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
<span data-ttu-id="2ed54-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="2ed54-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span></span>

<span data-ttu-id="2ed54-125">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="2ed54-125">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="2ed54-126">int</span><span class="sxs-lookup"><span data-stu-id="2ed54-126">int</span></span>](int.md)
2. [<span data-ttu-id="2ed54-127">uint</span><span class="sxs-lookup"><span data-stu-id="2ed54-127">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="2ed54-128">long</span><span class="sxs-lookup"><span data-stu-id="2ed54-128">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="2ed54-129">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="2ed54-129">Compiler overload resolution</span></span>
  
 <span data-ttu-id="2ed54-130">Il suffisso viene comunemente usato per la chiamata di metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="2ed54-130">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="2ed54-131">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ulong` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="2ed54-131">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="2ed54-132">L'uso del suffisso con il parametro `ulong` garantisce che verrà chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2ed54-132">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="2ed54-133">Conversioni</span><span class="sxs-lookup"><span data-stu-id="2ed54-133">Conversions</span></span>  
 <span data-ttu-id="2ed54-134">Si verifica una conversione implicita predefinita da `ulong` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="2ed54-134">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="2ed54-135">Non viene eseguita alcuna conversione implicita da `ulong` a qualsiasi tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="2ed54-135">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="2ed54-136">L'istruzione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="2ed54-136">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="2ed54-137">Viene eseguita una conversione implicita predefinita da [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="2ed54-137">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="2ed54-138">Non viene eseguita alcuna conversione implicita dai tipi a virgola mobile a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="2ed54-138">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="2ed54-139">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="2ed54-139">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="2ed54-140">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="2ed54-140">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="2ed54-141">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="2ed54-141">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2ed54-142">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2ed54-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ed54-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ed54-143">See Also</span></span>  
 <span data-ttu-id="2ed54-144"><xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="2ed54-144"><xref:System.UInt64></span></span>   
 <span data-ttu-id="2ed54-145">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-145">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2ed54-146">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-146">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2ed54-147">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-147">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2ed54-148">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-148">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="2ed54-149">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-149">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="2ed54-150">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="2ed54-150">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="2ed54-151">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="2ed54-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

