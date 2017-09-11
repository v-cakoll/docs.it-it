---
title: ushort (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
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
ms.openlocfilehash: 2b067a2ffd0fbffe06dc5c9f2a9910c9563eec4b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ushort-c-reference"></a><span data-ttu-id="148a0-102">ushort (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="148a0-102">ushort (C# Reference)</span></span>

<span data-ttu-id="148a0-103">La parola chiave `ushort` indica un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="148a0-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="148a0-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="148a0-104">Type</span></span>|<span data-ttu-id="148a0-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="148a0-105">Range</span></span>|<span data-ttu-id="148a0-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="148a0-106">Size</span></span>|<span data-ttu-id="148a0-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="148a0-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="148a0-108">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="148a0-108">0 to 65,535</span></span>|<span data-ttu-id="148a0-109">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="148a0-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="148a0-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="148a0-110">Literals</span></span>  

<span data-ttu-id="148a0-111">È possibile dichiarare e inizializzare una variabile `ushort` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="148a0-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="148a0-112">Se il valore letterale integer è esterno all'intervallo di `ushort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=fullName> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="148a0-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=fullName> or greater than <xref:System.UInt16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="148a0-113">Nell'esempio seguente, i valori interi uguali a 65,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `ushort`.</span><span class="sxs-lookup"><span data-stu-id="148a0-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
<span data-ttu-id="148a0-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span><span class="sxs-lookup"><span data-stu-id="148a0-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="148a0-115">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="148a0-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="148a0-116">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="148a0-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="148a0-117">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="148a0-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="148a0-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span><span class="sxs-lookup"><span data-stu-id="148a0-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="148a0-119">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="148a0-119">Compiler overload resolution</span></span>
  
 <span data-ttu-id="148a0-120">Quando si chiamano metodi di overload, è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="148a0-120">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="148a0-121">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ushort` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="148a0-121">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="148a0-122">L'uso del cast `ushort` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="148a0-122">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="148a0-123">Conversioni</span><span class="sxs-lookup"><span data-stu-id="148a0-123">Conversions</span></span>  
 <span data-ttu-id="148a0-124">Viene eseguita una conversione implicita da `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="148a0-124">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="148a0-125">Viene eseguita una conversione implicita predefinita da [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="148a0-125">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="148a0-126">In caso contrario è necessario usare un cast per eseguire una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="148a0-126">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="148a0-127">Considerare, ad esempio, le due variabili `ushort` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="148a0-127">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="148a0-128">L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="148a0-128">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="148a0-129">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="148a0-129">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="148a0-130">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="148a0-130">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="148a0-131">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="148a0-131">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="148a0-132">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="148a0-132">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="148a0-133">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="148a0-133">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="148a0-134">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="148a0-134">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="148a0-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="148a0-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="148a0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="148a0-136">See Also</span></span>  
 <span data-ttu-id="148a0-137"><xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="148a0-137"><xref:System.UInt16></span></span>   
 <span data-ttu-id="148a0-138">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="148a0-139">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="148a0-140">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="148a0-141">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="148a0-142">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="148a0-143">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="148a0-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="148a0-144">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="148a0-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

