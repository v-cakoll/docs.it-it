---
title: sbyte (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
dev_langs:
- CSharp
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
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
ms.openlocfilehash: 69741a5b9556c769156687584041667312550c17
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="sbyte-c-reference"></a><span data-ttu-id="e4f4c-102">sbyte (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e4f4c-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="e4f4c-103">`sbyte` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="e4f4c-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="e4f4c-104">Type</span></span>|<span data-ttu-id="e4f4c-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="e4f4c-105">Range</span></span>|<span data-ttu-id="e4f4c-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="e4f4c-106">Size</span></span>|<span data-ttu-id="e4f4c-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e4f4c-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="e4f4c-108">Da -128 a 127</span><span class="sxs-lookup"><span data-stu-id="e4f4c-108">-128 to 127</span></span>|<span data-ttu-id="e4f4c-109">Valore intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="e4f4c-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="e4f4c-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="e4f4c-110">Literals</span></span>  

<span data-ttu-id="e4f4c-111">È possibile dichiarare e inizializzare una variabile `sbyte` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="e4f4c-112">Nell'esempio seguente, i valori interi uguali a 102 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
<span data-ttu-id="e4f4c-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span><span class="sxs-lookup"><span data-stu-id="e4f4c-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="e4f4c-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="e4f4c-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="e4f4c-116">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="e4f4c-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span><span class="sxs-lookup"><span data-stu-id="e4f4c-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span></span>  

<span data-ttu-id="e4f4c-118">Se il valore letterale integer è esterno all'intervallo di `sbyte`, vale a dire se è minore di <xref:System.SByte.MinValue?displayProperty=fullName> o maggiore di <xref:System.SByte.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-118">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=fullName> or greater than <xref:System.SByte.MaxValue?displayProperty=fullName>, a compilation error occurs.</span></span> <span data-ttu-id="e4f4c-119">Quando un valore letterale integer non ha alcun suffisso, il tipo è il primo di questi tipi in cui può essere rappresentato il relativo valore: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-119">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="e4f4c-120">Ciò significa che, in questo esempio, i valori letterali numerici `0x9A` e `0b10011010` vengono interpretati come interi con segno a 32 bit con un valore corrispondente a 156, che supera <xref:System.SByte.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-120">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="e4f4c-121">Per questo motivo, è necessario l'operatore di cast e l'assegnazione deve trovarsi in un contesto [unchecked](unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-121">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="e4f4c-122">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="e4f4c-122">Compiler overload resolution</span></span>

 <span data-ttu-id="e4f4c-123">È necessario usare un cast quando si chiamano metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-123">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="e4f4c-124">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `sbyte` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="e4f4c-124">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="e4f4c-125">L'uso del cast `sbyte` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-125">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="e4f4c-126">Conversioni</span><span class="sxs-lookup"><span data-stu-id="e4f4c-126">Conversions</span></span>  
 <span data-ttu-id="e4f4c-127">Si verifica una conversione implicita predefinita da `sbyte` a [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-127">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="e4f4c-128">Non è possibile convertire in modo implicito tipi numerici non letterali che necessitano di maggiore spazio in memoria in `sbyte`. Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-128">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="e4f4c-129">Considerare, ad esempio, le due variabili `sbyte` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-129">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="e4f4c-130">L'istruzione di assegnazione che segue provocherà un errore di compilazione poiché, per impostazione predefinita, l'espressione aritmetica a destra dell'operatore di assegnazione restituisce [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="e4f4c-131">Per risolvere il problema, eseguire il cast dell'espressione come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-131">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="e4f4c-132">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="e4f4c-133">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="e4f4c-133">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="e4f4c-134">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="e4f4c-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="e4f4c-135">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="e4f4c-136">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="e4f4c-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e4f4c-137">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e4f4c-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4f4c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4f4c-138">See Also</span></span>  
 <span data-ttu-id="e4f4c-139"><xref:System.SByte></span><span class="sxs-lookup"><span data-stu-id="e4f4c-139"><xref:System.SByte></span></span>   
 <span data-ttu-id="e4f4c-140">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e4f4c-141">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e4f4c-142">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e4f4c-143">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-143">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="e4f4c-144">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-144">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="e4f4c-145">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="e4f4c-145">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="e4f4c-146">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="e4f4c-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

