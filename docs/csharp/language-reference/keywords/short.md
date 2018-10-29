---
title: short (Riferimenti per C#)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 0d90f31da49b94eee490e95f0cdf1d582bb0b059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184153"
---
# <a name="short-c-reference"></a><span data-ttu-id="21748-102">short (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="21748-102">short (C# Reference)</span></span>

<span data-ttu-id="21748-103">`short` denota un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="21748-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="21748-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="21748-104">Type</span></span>|<span data-ttu-id="21748-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="21748-105">Range</span></span>|<span data-ttu-id="21748-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="21748-106">Size</span></span>|<span data-ttu-id="21748-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="21748-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`short`|<span data-ttu-id="21748-108">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="21748-108">-32,768 to 32,767</span></span>|<span data-ttu-id="21748-109">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="21748-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="21748-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="21748-110">Literals</span></span>

<span data-ttu-id="21748-111">È possibile dichiarare e inizializzare una variabile `short` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="21748-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="21748-112">Se il valore letterale integer è esterno all'intervallo di `short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="21748-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="21748-113">Nell'esempio seguente, i valori interi uguali a 1,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](int.md) a valori `short`.</span><span class="sxs-lookup"><span data-stu-id="21748-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `short` values.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]

> [!NOTE]
> <span data-ttu-id="21748-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="21748-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="21748-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="21748-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="21748-116">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="21748-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>

- <span data-ttu-id="21748-117">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="21748-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="21748-118">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="21748-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="21748-119">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="21748-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="21748-120">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="21748-120">Some examples are shown below.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="21748-121">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="21748-121">Compiler overload resolution</span></span>

<span data-ttu-id="21748-122">È necessario usare un cast quando si chiamano metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="21748-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="21748-123">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `short` e [int](int.md):</span><span class="sxs-lookup"><span data-stu-id="21748-123">Consider, for example, the following overloaded methods that use `short` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(short s) {}
```

<span data-ttu-id="21748-124">L'uso del cast `short` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="21748-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);         // Calling the method with the int parameter
SampleMethod((short)5);  // Calling the method with the short parameter
```

## <a name="conversions"></a><span data-ttu-id="21748-125">Conversioni</span><span class="sxs-lookup"><span data-stu-id="21748-125">Conversions</span></span>

<span data-ttu-id="21748-126">Si verifica una conversione implicita predefinita da `short` a [int](int.md), [long](long.md), [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="21748-126">There is a predefined implicit conversion from `short` to [int](int.md), [long](long.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="21748-127">Non è possibile convertire in modo implicito tipi numerici non letterali che necessitano di maggiore spazio in memoria in `short`. Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="21748-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="21748-128">Considerare, ad esempio, le due variabili `short` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="21748-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>

```csharp
short x = 5, y = 12;
```

<span data-ttu-id="21748-129">L'istruzione di assegnazione seguente genera un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce [int](int.md) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="21748-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](int.md) by default.</span></span>

```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

<span data-ttu-id="21748-130">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="21748-130">To fix this problem, use a cast:</span></span>

```csharp
short z  = (short)(x + y);   // Explicit conversion
```

<span data-ttu-id="21748-131">È anche possibile usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="21748-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="21748-132">Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `short`.</span><span class="sxs-lookup"><span data-stu-id="21748-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="21748-133">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="21748-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
short x = 3.0;          // Error: no implicit conversion from double
short y = (short)3.0;   // OK: explicit conversion
```

<span data-ttu-id="21748-134">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="21748-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="21748-135">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="21748-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="21748-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="21748-136">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="21748-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21748-137">See also</span></span>

- <xref:System.Int16>
- [<span data-ttu-id="21748-138">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="21748-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21748-139">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="21748-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21748-140">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="21748-140">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="21748-141">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="21748-141">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="21748-142">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="21748-142">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="21748-143">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="21748-143">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="21748-144">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="21748-144">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)