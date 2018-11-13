---
title: byte (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: d952f56df62aa3a53e3889baa65c491e1a0fc81e
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "43505095"
---
# <a name="byte-c-reference"></a><span data-ttu-id="dd94a-102">byte (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dd94a-102">byte (C# Reference)</span></span>

<span data-ttu-id="dd94a-103">`byte` identifica un tipo integrale che archivia valori come indicato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dd94a-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="dd94a-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="dd94a-104">Type</span></span>|<span data-ttu-id="dd94a-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="dd94a-105">Range</span></span>|<span data-ttu-id="dd94a-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="dd94a-106">Size</span></span>|<span data-ttu-id="dd94a-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="dd94a-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="dd94a-108">Da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="dd94a-108">0 to 255</span></span>|<span data-ttu-id="dd94a-109">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="dd94a-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="dd94a-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="dd94a-110">Literals</span></span>  

 <span data-ttu-id="dd94a-111">È possibile dichiarare e inizializzare una variabile `byte` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="dd94a-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="dd94a-112">Se il valore letterale integer è esterno all'intervallo di `byte`, vale a dire se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dd94a-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="dd94a-113">Nell'esempio seguente, i valori interi uguali a 201 rappresentati some valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `byte`.</span><span class="sxs-lookup"><span data-stu-id="dd94a-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="dd94a-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="dd94a-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="dd94a-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="dd94a-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="dd94a-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="dd94a-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="dd94a-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="dd94a-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="dd94a-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="dd94a-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="dd94a-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="dd94a-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="dd94a-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="dd94a-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="dd94a-121">Conversioni</span><span class="sxs-lookup"><span data-stu-id="dd94a-121">Conversions</span></span>  
 <span data-ttu-id="dd94a-122">È disponibile una conversione implicita predefinita da `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="dd94a-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="dd94a-123">Non è possibile convertire in modo implicito i tipi numerici non letterali di dimensioni di archiviazione maggiori di `byte`.</span><span class="sxs-lookup"><span data-stu-id="dd94a-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="dd94a-124">Per altre informazioni sulle dimensioni di archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="dd94a-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="dd94a-125">Considerare, ad esempio, le due variabili `byte` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="dd94a-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="dd94a-126">L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dd94a-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="dd94a-127">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="dd94a-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="dd94a-128">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha dimensioni uguali o superiori di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="dd94a-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="dd94a-129">Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `byte`.</span><span class="sxs-lookup"><span data-stu-id="dd94a-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="dd94a-130">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="dd94a-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="dd94a-131">Quando si chiamano metodi di overload, è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="dd94a-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="dd94a-132">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `byte` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="dd94a-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="dd94a-133">L'uso del cast `byte` garantisce che verrà chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dd94a-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="dd94a-134">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="dd94a-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="dd94a-135">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="dd94a-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd94a-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="dd94a-136">C# Language Specification</span></span>  

<span data-ttu-id="dd94a-137">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd94a-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="dd94a-138">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="dd94a-138">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd94a-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd94a-139">See Also</span></span>  

- <xref:System.Byte>  
- [<span data-ttu-id="dd94a-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="dd94a-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="dd94a-141">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="dd94a-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dd94a-142">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="dd94a-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="dd94a-143">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="dd94a-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="dd94a-144">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="dd94a-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="dd94a-145">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="dd94a-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="dd94a-146">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="dd94a-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
