---
title: ushort (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 03638893978779fcfd34544363d935fa5e609481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288824"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="958da-102">ushort (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="958da-102">ushort (C# Reference)</span></span>

<span data-ttu-id="958da-103">La parola chiave `ushort` indica un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="958da-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="958da-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="958da-104">Type</span></span>|<span data-ttu-id="958da-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="958da-105">Range</span></span>|<span data-ttu-id="958da-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="958da-106">Size</span></span>|<span data-ttu-id="958da-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="958da-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="958da-108">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="958da-108">0 to 65,535</span></span>|<span data-ttu-id="958da-109">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="958da-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="958da-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="958da-110">Literals</span></span>  

<span data-ttu-id="958da-111">È possibile dichiarare e inizializzare una variabile `ushort` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="958da-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="958da-112">Se il valore letterale integer è esterno all'intervallo di `ushort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="958da-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="958da-113">Nell'esempio seguente, i valori interi uguali a 65,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `ushort`.</span><span class="sxs-lookup"><span data-stu-id="958da-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="958da-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="958da-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="958da-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="958da-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="958da-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="958da-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="958da-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="958da-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="958da-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="958da-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="958da-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="958da-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="958da-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="958da-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="958da-121">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="958da-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="958da-122">Quando si chiamano metodi di overload, è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="958da-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="958da-123">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `ushort` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="958da-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="958da-124">L'uso del cast `ushort` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="958da-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="958da-125">Conversioni</span><span class="sxs-lookup"><span data-stu-id="958da-125">Conversions</span></span>  
 <span data-ttu-id="958da-126">Viene eseguita una conversione implicita da `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="958da-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="958da-127">Viene eseguita una conversione implicita predefinita da [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="958da-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="958da-128">In caso contrario è necessario usare un cast per eseguire una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="958da-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="958da-129">Considerare, ad esempio, le due variabili `ushort` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="958da-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="958da-130">L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="958da-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="958da-131">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="958da-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="958da-132">È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="958da-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="958da-133">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="958da-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="958da-134">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="958da-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="958da-135">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="958da-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="958da-136">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="958da-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="958da-137">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="958da-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="958da-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="958da-138">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="958da-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="958da-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="958da-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="958da-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="958da-141">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="958da-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="958da-142">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="958da-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="958da-143">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="958da-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="958da-144">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="958da-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="958da-145">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="958da-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
