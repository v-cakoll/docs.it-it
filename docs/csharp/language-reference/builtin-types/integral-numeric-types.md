---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 06/25/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 0a1ed01d9e6cb86ea177e8b947627f9dc02eedae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744224"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="e0dc5-103">Tipi numerici integrali (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e0dc5-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="e0dc5-104">I **tipi numerici integrali** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#integral-literals).</span><span class="sxs-lookup"><span data-stu-id="e0dc5-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="e0dc5-105">Tutti i tipi integrali sono anche tipi valore.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-105">All integral types are also value types.</span></span>

<span data-ttu-id="e0dc5-106">Tutti i tipi numerici integrali supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [logici bit per bit](../operators/bitwise-and-shift-operators.md), [di confronto e di uguaglianza](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e0dc5-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="e0dc5-107">Dimensioni e intervalli</span><span class="sxs-lookup"><span data-stu-id="e0dc5-107">Sizes and ranges</span></span>

<span data-ttu-id="e0dc5-108">La tabella seguente elenca le dimensioni e gli intervalli dei tipi integrali:</span><span class="sxs-lookup"><span data-stu-id="e0dc5-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="e0dc5-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="e0dc5-109">Type</span></span>|<span data-ttu-id="e0dc5-110">Intervallo</span><span class="sxs-lookup"><span data-stu-id="e0dc5-110">Range</span></span>|<span data-ttu-id="e0dc5-111">Dimensione</span><span class="sxs-lookup"><span data-stu-id="e0dc5-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="e0dc5-112">Da -128 a 127</span><span class="sxs-lookup"><span data-stu-id="e0dc5-112">-128 to 127</span></span>|<span data-ttu-id="e0dc5-113">Valore intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="e0dc5-114">Da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="e0dc5-114">0 to 255</span></span>|<span data-ttu-id="e0dc5-115">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="e0dc5-116">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="e0dc5-116">-32,768 to 32,767</span></span>|<span data-ttu-id="e0dc5-117">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="e0dc5-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="e0dc5-118">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="e0dc5-118">0 to 65,535</span></span>|<span data-ttu-id="e0dc5-119">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="e0dc5-120">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="e0dc5-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="e0dc5-121">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="e0dc5-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="e0dc5-122">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="e0dc5-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="e0dc5-123">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="e0dc5-124">Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="e0dc5-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="e0dc5-125">Numero intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="e0dc5-126">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="e0dc5-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="e0dc5-127">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="e0dc5-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="e0dc5-128">Il valore predefinito di tutti i tipi integrali è `0`.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="e0dc5-129">Ogni tipo integrale ha costanti denominate `MinValue` e `MaxValue` per il valore minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="e0dc5-130">Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="e0dc5-131">Valori letterali integrali</span><span class="sxs-lookup"><span data-stu-id="e0dc5-131">Integral literals</span></span>

<span data-ttu-id="e0dc5-132">I valori letterali integrali possono essere specificati come *valori letterali decimali*, *valori letterali esadecimali* o *valori letterali binari*.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="e0dc5-133">Di seguito è illustrato un esempio di ognuno:</span><span class="sxs-lookup"><span data-stu-id="e0dc5-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="e0dc5-134">I valori letterali decimali non richiedono alcun prefisso.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="e0dc5-135">Il prefisso `x` o `X` indica un *valore letterale esadecimale*.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="e0dc5-136">Il prefisso `b` o `B` indica un *valore letterale binario*.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="e0dc5-137">La dichiarazione di `binaryLiteral` dimostra l'uso di `_` come *separatore di cifra*.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="e0dc5-138">Il separatore di cifra può essere usato con tutti i valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="e0dc5-139">I valori letterali binari e il separatore di cifra `_` sono supportati a partire da C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="e0dc5-140">Suffissi letterali</span><span class="sxs-lookup"><span data-stu-id="e0dc5-140">Literal suffixes</span></span> 

<span data-ttu-id="e0dc5-141">Il suffisso `l` o `L` specifica che il valore letterale integrale deve essere del tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="e0dc5-142">Il suffisso `ul` o `UL` specifica il tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="e0dc5-143">Se il suffisso `L` viene usato su un valore letterale maggiore di 9.223.372.036.854.775.807 (il valore massimo di `long`), il valore viene convertito nel tipo `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="e0dc5-144">Se il valore rappresentato da un valore letterale integrale supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="e0dc5-144">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0dc5-145">È possibile usare la lettera minuscola "l" come suffisso.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="e0dc5-146">In questo caso, viene tuttavia generato un avviso del compilatore perché la lettera "l" viene facilmente confusa con la cifra "1".</span><span class="sxs-lookup"><span data-stu-id="e0dc5-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="e0dc5-147">Per maggiore chiarezza, usare la lettera "L".</span><span class="sxs-lookup"><span data-stu-id="e0dc5-147">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="e0dc5-148">Tipo di un valore letterale integrale</span><span class="sxs-lookup"><span data-stu-id="e0dc5-148">Type of an integral literal</span></span>

<span data-ttu-id="e0dc5-149">Se un valore letterale integrale non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="e0dc5-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="e0dc5-150">È possibile convertire un valore letterale integrale in un tipo con un intervallo più piccolo rispetto a quello predefinito eseguendo un'assegnazione o un cast:</span><span class="sxs-lookup"><span data-stu-id="e0dc5-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="e0dc5-151">È possibile convertire un valore letterale integrale in un tipo con un intervallo più grande rispetto a quello predefinito eseguendo un'assegnazione, un cast o inserendo un suffisso nel valore letterale:</span><span class="sxs-lookup"><span data-stu-id="e0dc5-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="e0dc5-152">Conversioni</span><span class="sxs-lookup"><span data-stu-id="e0dc5-152">Conversions</span></span>

<span data-ttu-id="e0dc5-153">Viene eseguita una conversione implicita (detta *conversione verso un tipo di dati più grande*) tra due tipi integrali in cui il tipo di destinazione può archiviare tutti i valori del tipo di origine.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="e0dc5-154">Ad esempio, è presente una conversione implicita da `int` a `long` perché l'intervallo di valori `int` è un subset corretto di `long`.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="e0dc5-155">Sono presenti conversioni implicite da un tipo integrale senza segno più piccolo a un tipo integrale con segno più grande.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="e0dc5-156">È presente una conversione implicita anche da qualsiasi tipo integrale a qualsiasi tipo a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="e0dc5-157">Non vi è conversione implicita da qualsiasi tipo integrale con segno a qualsiasi tipo integrale senza segno.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="e0dc5-158">È necessario usare un cast esplicito per convertire un tipo integrale in un altro tipo integrale quando non è definita una conversione implicita dal tipo di origine al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="e0dc5-159">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="e0dc5-160">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="e0dc5-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0dc5-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0dc5-161">See also</span></span>

- [<span data-ttu-id="e0dc5-162">Specifiche del linguaggio C# - Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="e0dc5-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="e0dc5-163">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e0dc5-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e0dc5-164">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="e0dc5-164">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="e0dc5-165">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="e0dc5-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="e0dc5-166">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="e0dc5-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="e0dc5-167">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="e0dc5-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="e0dc5-168">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="e0dc5-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
