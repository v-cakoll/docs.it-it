---
title: Tipi numerici integrali - Riferimenti per C#
description: Informazioni sull'intervallo, le dimensioni di archiviazione e gli usi dei singoli tipi numerici integrali.
ms.date: 10/22/2019
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
ms.openlocfilehash: 2fb4d7185ac85b29f2cc2d2e7a29e192f91a0868
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980145"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="266f7-103">Tipi numerici integrali (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="266f7-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="266f7-104">I **tipi numerici integrali** sono un subset dei **tipi semplici** e possono essere inizializzati con [*valori letterali*](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="266f7-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="266f7-105">Tutti i tipi integrali sono anche tipi valore.</span><span class="sxs-lookup"><span data-stu-id="266f7-105">All integral types are also value types.</span></span> <span data-ttu-id="266f7-106">Tutti i tipi numerici integrali supportano gli operatori [aritmetici](../operators/arithmetic-operators.md), [logici bit per bit](../operators/bitwise-and-shift-operators.md), di [confronto](../operators/comparison-operators.md)e di [uguaglianza](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="266f7-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="266f7-107">Caratteristiche dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="266f7-107">Characteristics of the integral types</span></span>

<span data-ttu-id="266f7-108">C# supporta i tipi integrali predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="266f7-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="266f7-109">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="266f7-109">C# type/keyword</span></span>|<span data-ttu-id="266f7-110">Intervallo</span><span class="sxs-lookup"><span data-stu-id="266f7-110">Range</span></span>|<span data-ttu-id="266f7-111">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="266f7-111">Size</span></span>|<span data-ttu-id="266f7-112">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="266f7-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="266f7-113">Da -128 a 127</span><span class="sxs-lookup"><span data-stu-id="266f7-113">-128 to 127</span></span>|<span data-ttu-id="266f7-114">Valore intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="266f7-115">Da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="266f7-115">0 to 255</span></span>|<span data-ttu-id="266f7-116">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="266f7-117">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="266f7-117">-32,768 to 32,767</span></span>|<span data-ttu-id="266f7-118">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="266f7-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="266f7-119">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="266f7-119">0 to 65,535</span></span>|<span data-ttu-id="266f7-120">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="266f7-121">da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="266f7-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="266f7-122">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="266f7-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="266f7-123">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="266f7-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="266f7-124">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="266f7-125">Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="266f7-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="266f7-126">Numero intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="266f7-127">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="266f7-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="266f7-128">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="266f7-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="266f7-129">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="266f7-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="266f7-130">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="266f7-130">They are interchangeable.</span></span> <span data-ttu-id="266f7-131">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="266f7-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="266f7-132">Il valore predefinito di ogni tipo integrale è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="266f7-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="266f7-133">Ogni tipo integrale ha costanti `MinValue` e `MaxValue` che specificano il valore minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="266f7-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="266f7-134">Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.</span><span class="sxs-lookup"><span data-stu-id="266f7-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="266f7-135">Valori letterali Integer</span><span class="sxs-lookup"><span data-stu-id="266f7-135">Integer literals</span></span>

<span data-ttu-id="266f7-136">I valori letterali integer possono essere</span><span class="sxs-lookup"><span data-stu-id="266f7-136">Integer literals can be</span></span>

- <span data-ttu-id="266f7-137">*Decimal*: senza prefisso</span><span class="sxs-lookup"><span data-stu-id="266f7-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="266f7-138">*esadecimale*: con il prefisso `0x` o `0X`</span><span class="sxs-lookup"><span data-stu-id="266f7-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="266f7-139">*Binary*: con il prefisso `0b` o `0B` (disponibile in C# 7,0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="266f7-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="266f7-140">Il codice seguente illustra un esempio di ogni:</span><span class="sxs-lookup"><span data-stu-id="266f7-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="266f7-141">Nell'esempio precedente viene inoltre illustrato l'utilizzo di `_` come *separatore di cifre*, supportato a partire C# da 7,0.</span><span class="sxs-lookup"><span data-stu-id="266f7-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="266f7-142">È possibile usare il separatore di cifre con tutti i tipi di valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="266f7-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="266f7-143">Il tipo di un valore letterale integer è determinato dal suffisso, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="266f7-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="266f7-144">Se il valore letterale non ha alcun suffisso, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `int`, `uint`, `long``ulong`.</span><span class="sxs-lookup"><span data-stu-id="266f7-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="266f7-145">Se il valore letterale è suffisso per `U` o `u`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="266f7-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="266f7-146">Se il valore letterale è suffisso per `L` o `l`, il tipo è il primo dei tipi seguenti in cui è possibile rappresentare il relativo valore: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="266f7-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="266f7-147">È possibile usare la lettera minuscola `l` come suffisso.</span><span class="sxs-lookup"><span data-stu-id="266f7-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="266f7-148">Viene tuttavia generato un avviso del compilatore perché la lettera `l` può essere confusa con la cifra `1`.</span><span class="sxs-lookup"><span data-stu-id="266f7-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="266f7-149">Per maggiore chiarezza, utilizzare `L`.</span><span class="sxs-lookup"><span data-stu-id="266f7-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="266f7-150">Se il valore letterale è suffisso in `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`o `lu`, il tipo è `ulong`.</span><span class="sxs-lookup"><span data-stu-id="266f7-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="266f7-151">Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="266f7-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="266f7-152">Se il tipo determinato di un valore letterale integer è `int` e il valore rappresentato dal valore letterale è compreso nell'intervallo del tipo di destinazione, il valore può essere convertito in modo implicito in `sbyte`, `byte`, `short`, `ushort`, `uint`o `ulong`:</span><span class="sxs-lookup"><span data-stu-id="266f7-152">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="266f7-153">Come illustrato nell'esempio precedente, se il valore del valore letterale non è compreso nell'intervallo del tipo di destinazione, si verifica un errore del compilatore [CS0031](../../misc/cs0031.md) .</span><span class="sxs-lookup"><span data-stu-id="266f7-153">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="266f7-154">È anche possibile usare un cast per convertire il valore rappresentato da un valore letterale integer nel tipo diverso dal tipo determinato del valore letterale:</span><span class="sxs-lookup"><span data-stu-id="266f7-154">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="266f7-155">Conversioni</span><span class="sxs-lookup"><span data-stu-id="266f7-155">Conversions</span></span>

<span data-ttu-id="266f7-156">È possibile convertire qualsiasi tipo numerico integrale in qualsiasi altro tipo numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="266f7-156">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="266f7-157">Se il tipo di destinazione può archiviare tutti i valori del tipo di origine, la conversione è implicita.</span><span class="sxs-lookup"><span data-stu-id="266f7-157">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="266f7-158">In caso contrario, è necessario usare l' [operatore cast `()`](../operators/type-testing-and-cast.md#cast-operator-) per richiamare una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="266f7-158">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="266f7-159">Per altre informazioni, vedere [conversioni numeriche predefinite](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="266f7-159">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="266f7-160">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="266f7-160">C# language specification</span></span>

<span data-ttu-id="266f7-161">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="266f7-161">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="266f7-162">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="266f7-162">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="266f7-163">Valori letterali integer</span><span class="sxs-lookup"><span data-stu-id="266f7-163">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="266f7-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="266f7-164">See also</span></span>

- [<span data-ttu-id="266f7-165">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="266f7-165">C# reference</span></span>](../index.md)
- [<span data-ttu-id="266f7-166">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="266f7-166">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="266f7-167">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="266f7-167">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="266f7-168">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="266f7-168">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="266f7-169">Dati numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="266f7-169">Numerics in .NET</span></span>](../../../standard/numerics.md)
