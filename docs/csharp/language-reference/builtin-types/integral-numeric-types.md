---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 10/18/2019
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
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579188"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="ce599-103">Tipi numerici integrali (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ce599-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="ce599-104">I **tipi numerici integrali** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="ce599-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="ce599-105">Tutti i tipi integrali sono anche tipi valore.</span><span class="sxs-lookup"><span data-stu-id="ce599-105">All integral types are also value types.</span></span> <span data-ttu-id="ce599-106">Tutti i tipi numerici integrali supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [logici bit per bit](../operators/bitwise-and-shift-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="ce599-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="ce599-107">Caratteristiche dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="ce599-107">Characteristics of the integral types</span></span>

<span data-ttu-id="ce599-108">C# supporta i tipi integrali predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce599-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="ce599-109">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="ce599-109">C# type/keyword</span></span>|<span data-ttu-id="ce599-110">Intervallo</span><span class="sxs-lookup"><span data-stu-id="ce599-110">Range</span></span>|<span data-ttu-id="ce599-111">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="ce599-111">Size</span></span>|<span data-ttu-id="ce599-112">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="ce599-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="ce599-113">Da -128 a 127</span><span class="sxs-lookup"><span data-stu-id="ce599-113">-128 to 127</span></span>|<span data-ttu-id="ce599-114">Valore intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="ce599-115">Da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="ce599-115">0 to 255</span></span>|<span data-ttu-id="ce599-116">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="ce599-117">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="ce599-117">-32,768 to 32,767</span></span>|<span data-ttu-id="ce599-118">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="ce599-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="ce599-119">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="ce599-119">0 to 65,535</span></span>|<span data-ttu-id="ce599-120">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="ce599-121">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="ce599-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="ce599-122">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="ce599-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="ce599-123">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="ce599-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="ce599-124">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="ce599-125">Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="ce599-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="ce599-126">Numero intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="ce599-127">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="ce599-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="ce599-128">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ce599-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="ce599-129">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ce599-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="ce599-130">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="ce599-130">They are interchangeable.</span></span> <span data-ttu-id="ce599-131">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="ce599-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="ce599-132">Il valore predefinito di ogni tipo integrale è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="ce599-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="ce599-133">Ogni tipo integrale ha costanti `MinValue` e `MaxValue` che specificano il valore minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="ce599-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="ce599-134">Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.</span><span class="sxs-lookup"><span data-stu-id="ce599-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="ce599-135">Valori letterali Integer</span><span class="sxs-lookup"><span data-stu-id="ce599-135">Integer literals</span></span>

<span data-ttu-id="ce599-136">I valori letterali integer possono essere</span><span class="sxs-lookup"><span data-stu-id="ce599-136">Integer literals can be</span></span>

- <span data-ttu-id="ce599-137">*Decimal*: senza prefisso</span><span class="sxs-lookup"><span data-stu-id="ce599-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="ce599-138">*esadecimale*: con il prefisso `0x` o `0X`</span><span class="sxs-lookup"><span data-stu-id="ce599-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="ce599-139">*Binary*: con il prefisso `0b` o `0B` (disponibile in C# 7,0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="ce599-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="ce599-140">Il codice seguente illustra un esempio di ogni:</span><span class="sxs-lookup"><span data-stu-id="ce599-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="ce599-141">Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0.</span><span class="sxs-lookup"><span data-stu-id="ce599-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="ce599-142">È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="ce599-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="ce599-143">Il tipo di un valore letterale integer è determinato dal suffisso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ce599-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="ce599-144">Se il valore letterale non ha alcun suffisso, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `int`, `uint`, `long` `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ce599-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="ce599-145">Se il valore letterale è suffisso per `U` o `u`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ce599-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="ce599-146">Se il valore letterale è suffisso per `L` o `l`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ce599-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ce599-147">È possibile usare la lettera minuscola `l` come suffisso.</span><span class="sxs-lookup"><span data-stu-id="ce599-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="ce599-148">Viene tuttavia generato un avviso del compilatore perché la lettera `l` può essere confusa con la cifra `1`.</span><span class="sxs-lookup"><span data-stu-id="ce599-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="ce599-149">Per maggiore chiarezza, utilizzare `L`.</span><span class="sxs-lookup"><span data-stu-id="ce599-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="ce599-150">Se il valore letterale è suffisso in `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` o `lu`, il tipo è `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ce599-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="ce599-151">Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="ce599-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="ce599-152">Il valore rappresentato da un valore letterale integer può essere convertito in modo implicito in un tipo con un intervallo inferiore al tipo determinato del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="ce599-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="ce599-153">Questo è possibile quando il valore è compreso nell'intervallo del tipo di destinazione:</span><span class="sxs-lookup"><span data-stu-id="ce599-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="ce599-154">Come illustrato nell'esempio precedente, se il valore del valore letterale non è compreso nell'intervallo del tipo di destinazione, si verifica un errore del compilatore [CS0031](../../misc/cs0031.md) .</span><span class="sxs-lookup"><span data-stu-id="ce599-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="ce599-155">È anche possibile usare un cast per convertire il valore rappresentato da un valore letterale integer nel tipo diverso dal tipo determinato del valore letterale:</span><span class="sxs-lookup"><span data-stu-id="ce599-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="ce599-156">Conversioni</span><span class="sxs-lookup"><span data-stu-id="ce599-156">Conversions</span></span>

<span data-ttu-id="ce599-157">Viene eseguita una conversione implicita (detta *conversione verso un tipo di dati più grande*) tra due tipi integrali in cui il tipo di destinazione può archiviare tutti i valori del tipo di origine.</span><span class="sxs-lookup"><span data-stu-id="ce599-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="ce599-158">Ad esempio, è presente una conversione implicita da `int` a `long` perché l'intervallo di valori `int` è un subset corretto di `long`.</span><span class="sxs-lookup"><span data-stu-id="ce599-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="ce599-159">Sono presenti conversioni implicite da un tipo integrale senza segno più piccolo a un tipo integrale con segno più grande.</span><span class="sxs-lookup"><span data-stu-id="ce599-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="ce599-160">È presente una conversione implicita anche da qualsiasi tipo integrale a qualsiasi tipo a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="ce599-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="ce599-161">Non vi è conversione implicita da qualsiasi tipo integrale con segno a qualsiasi tipo integrale senza segno.</span><span class="sxs-lookup"><span data-stu-id="ce599-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="ce599-162">È necessario usare un cast esplicito per convertire un tipo integrale in un altro tipo integrale quando non è definita una conversione implicita dal tipo di origine al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce599-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="ce599-163">Questa operazione è definita *conversione verso un tipo di dati più piccolo*.</span><span class="sxs-lookup"><span data-stu-id="ce599-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="ce599-164">Il caso esplicito è necessario perché la conversione può comportare una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="ce599-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ce599-165">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ce599-165">C# language specification</span></span>

<span data-ttu-id="ce599-166">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="ce599-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="ce599-167">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="ce599-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="ce599-168">Valori letterali integer</span><span class="sxs-lookup"><span data-stu-id="ce599-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="ce599-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce599-169">See also</span></span>

- [<span data-ttu-id="ce599-170">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ce599-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ce599-171">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="ce599-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="ce599-172">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="ce599-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="ce599-173">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="ce599-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="ce599-174">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="ce599-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="ce599-175">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="ce599-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
