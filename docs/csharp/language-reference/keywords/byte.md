---
title: byte (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ef7494e2a8a1463d37cff77d1dacebec8182b66
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="byte-c-reference"></a><span data-ttu-id="bf7fc-102">byte (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bf7fc-102">byte (C# Reference)</span></span>

<span data-ttu-id="bf7fc-103">`byte` identifica un tipo integrale che archivia valori come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="bf7fc-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf7fc-104">Type</span></span>|<span data-ttu-id="bf7fc-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="bf7fc-105">Range</span></span>|<span data-ttu-id="bf7fc-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="bf7fc-106">Size</span></span>|<span data-ttu-id="bf7fc-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf7fc-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="bf7fc-108">Da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="bf7fc-108">0 to 255</span></span>|<span data-ttu-id="bf7fc-109">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="bf7fc-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="bf7fc-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="bf7fc-110">Literals</span></span>  

 <span data-ttu-id="bf7fc-111">È possibile dichiarare e inizializzare una variabile `byte` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="bf7fc-112">Se il valore letterale integer è esterno all'intervallo di `byte`, vale a dire se è minore di <xref:System.Byte.MinValue?displayProperty=fullName> o maggiore di <xref:System.Byte.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=fullName> or greater than <xref:System.Byte.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="bf7fc-113">Nell'esempio seguente, i valori interi uguali a 201 rappresentati some valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `byte`.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
<span data-ttu-id="bf7fc-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span><span class="sxs-lookup"><span data-stu-id="bf7fc-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="bf7fc-115">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="bf7fc-116">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bf7fc-117">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="bf7fc-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span><span class="sxs-lookup"><span data-stu-id="bf7fc-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span></span>  
 
## <a name="conversions"></a><span data-ttu-id="bf7fc-119">Conversioni</span><span class="sxs-lookup"><span data-stu-id="bf7fc-119">Conversions</span></span>  
 <span data-ttu-id="bf7fc-120">È disponibile una conversione implicita predefinita da `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="bf7fc-120">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="bf7fc-121">Non è possibile convertire in modo implicito i tipi numerici non letterali di dimensioni di archiviazione maggiori di `byte`.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-121">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="bf7fc-122">Per altre informazioni sulle dimensioni di archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="bf7fc-122">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="bf7fc-123">Considerare, ad esempio, le due variabili `byte` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="bf7fc-123">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="bf7fc-124">L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-124">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="bf7fc-125">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="bf7fc-125">To fix this problem, use a cast:</span></span>  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="bf7fc-126">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha dimensioni uguali o superiori di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="bf7fc-126">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="bf7fc-127">Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `byte`.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-127">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="bf7fc-128">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="bf7fc-128">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="bf7fc-129">Quando si chiamano metodi di overload, è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="bf7fc-129">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="bf7fc-130">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `byte` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="bf7fc-130">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="bf7fc-131">L'uso del cast `byte` garantisce che verrà chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf7fc-131">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="bf7fc-132">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="bf7fc-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="bf7fc-133">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="bf7fc-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bf7fc-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bf7fc-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bf7fc-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf7fc-135">See Also</span></span>  
 <span data-ttu-id="bf7fc-136"><xref:System.Byte></span><span class="sxs-lookup"><span data-stu-id="bf7fc-136"><xref:System.Byte></span></span>   
 <span data-ttu-id="bf7fc-137">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bf7fc-138">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bf7fc-139">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bf7fc-140">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="bf7fc-141">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="bf7fc-142">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="bf7fc-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="bf7fc-143">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="bf7fc-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

