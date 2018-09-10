---
title: short (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: f402b9d2d62bcc3ba265755d59a657b88c197482
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855790"
---
# <a name="short-c-reference"></a><span data-ttu-id="97f92-102">short (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="97f92-102">short (C# Reference)</span></span>

<span data-ttu-id="97f92-103">`short` denota un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="97f92-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="97f92-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="97f92-104">Type</span></span>|<span data-ttu-id="97f92-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="97f92-105">Range</span></span>|<span data-ttu-id="97f92-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="97f92-106">Size</span></span>|<span data-ttu-id="97f92-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="97f92-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="97f92-108">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="97f92-108">-32,768 to 32,767</span></span>|<span data-ttu-id="97f92-109">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="97f92-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="97f92-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="97f92-110">Literals</span></span>  

<span data-ttu-id="97f92-111">È possibile dichiarare e inizializzare una variabile `short` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="97f92-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="97f92-112">Se il valore letterale integer è esterno all'intervallo di `short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="97f92-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="97f92-113">Nell'esempio seguente, i valori interi uguali a 1,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `short`.</span><span class="sxs-lookup"><span data-stu-id="97f92-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> <span data-ttu-id="97f92-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="97f92-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="97f92-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="97f92-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="97f92-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="97f92-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="97f92-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="97f92-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="97f92-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="97f92-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="97f92-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="97f92-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="97f92-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="97f92-120">Some examples are shown below.</span></span>

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="97f92-121">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="97f92-121">Compiler overload resolution</span></span>

 <span data-ttu-id="97f92-122">È necessario usare un cast quando si chiamano metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="97f92-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="97f92-123">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `short` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="97f92-123">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="97f92-124">L'uso del cast `short` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97f92-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="97f92-125">Conversioni</span><span class="sxs-lookup"><span data-stu-id="97f92-125">Conversions</span></span>  

 <span data-ttu-id="97f92-126">Si verifica una conversione implicita predefinita da `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="97f92-126">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="97f92-127">Non è possibile convertire in modo implicito tipi numerici non letterali che necessitano di maggiore spazio in memoria in `short`. Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="97f92-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="97f92-128">Considerare, ad esempio, le due variabili `short` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="97f92-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="97f92-129">L'istruzione di assegnazione seguente genera un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce [int](../../../csharp/language-reference/keywords/int.md) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="97f92-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="97f92-130">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="97f92-130">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="97f92-131">È anche possibile usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="97f92-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="97f92-132">Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `short`.</span><span class="sxs-lookup"><span data-stu-id="97f92-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="97f92-133">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="97f92-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="97f92-134">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="97f92-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="97f92-135">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="97f92-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="97f92-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="97f92-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97f92-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f92-137">See Also</span></span>

- <xref:System.Int16>  
- [<span data-ttu-id="97f92-138">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="97f92-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="97f92-139">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="97f92-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="97f92-140">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="97f92-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="97f92-141">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="97f92-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="97f92-142">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="97f92-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="97f92-143">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="97f92-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="97f92-144">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="97f92-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
