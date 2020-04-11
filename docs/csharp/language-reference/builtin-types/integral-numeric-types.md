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
ms.openlocfilehash: 4b2506f48c3e72ff838a07087c8c5d9ea63bb46c
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121464"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="bb01f-103">Tipi numerici integrali (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bb01f-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="bb01f-104">I *tipi numerici integrali* rappresentano numeri interi.</span><span class="sxs-lookup"><span data-stu-id="bb01f-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="bb01f-105">Tutti i tipi numerici integrali sono [tipi di valore](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="bb01f-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="bb01f-106">Sono anche [tipi semplici](value-types.md#built-in-value-types) e possono essere inizializzati con valori [letterali](#integer-literals).</span><span class="sxs-lookup"><span data-stu-id="bb01f-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="bb01f-107">Tutti i tipi numerici integrali supportano gli operatori [aritmetici,](../operators/arithmetic-operators.md) [logici bit per bit](../operators/bitwise-and-shift-operators.md), [di confronto](../operators/comparison-operators.md)e [di uguaglianza.](../operators/equality-operators.md)</span><span class="sxs-lookup"><span data-stu-id="bb01f-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="bb01f-108">Caratteristiche dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="bb01f-108">Characteristics of the integral types</span></span>

<span data-ttu-id="bb01f-109">C# supporta i tipi integrali predefiniti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb01f-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="bb01f-110">Tipo/parola chiave C#</span><span class="sxs-lookup"><span data-stu-id="bb01f-110">C# type/keyword</span></span>|<span data-ttu-id="bb01f-111">Range</span><span class="sxs-lookup"><span data-stu-id="bb01f-111">Range</span></span>|<span data-ttu-id="bb01f-112">Dimensione</span><span class="sxs-lookup"><span data-stu-id="bb01f-112">Size</span></span>|<span data-ttu-id="bb01f-113">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="bb01f-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="bb01f-114">Da -128 a 127</span><span class="sxs-lookup"><span data-stu-id="bb01f-114">-128 to 127</span></span>|<span data-ttu-id="bb01f-115">Valore intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="bb01f-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="bb01f-116">da 0 a 255</span><span class="sxs-lookup"><span data-stu-id="bb01f-116">0 to 255</span></span>|<span data-ttu-id="bb01f-117">Intero senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="bb01f-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="bb01f-118">Da -32.768 a 32.767</span><span class="sxs-lookup"><span data-stu-id="bb01f-118">-32,768 to 32,767</span></span>|<span data-ttu-id="bb01f-119">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="bb01f-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="bb01f-120">Da 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="bb01f-120">0 to 65,535</span></span>|<span data-ttu-id="bb01f-121">Intero senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="bb01f-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="bb01f-122">Da -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="bb01f-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="bb01f-123">Valore intero a 32 bit con segno</span><span class="sxs-lookup"><span data-stu-id="bb01f-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="bb01f-124">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="bb01f-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="bb01f-125">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="bb01f-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="bb01f-126">Da -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="bb01f-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="bb01f-127">Valore intero a 64 bit con segno</span><span class="sxs-lookup"><span data-stu-id="bb01f-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="bb01f-128">Da 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="bb01f-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="bb01f-129">Intero senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="bb01f-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="bb01f-130">Nella tabella precedente ogni tipo/parola chiave C# nella colonna più a sinistra è un alias per il tipo .NET corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bb01f-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="bb01f-131">Sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="bb01f-131">They are interchangeable.</span></span> <span data-ttu-id="bb01f-132">Ad esempio, le dichiarazioni seguenti dichiarano variabili dello stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="bb01f-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="bb01f-133">Il valore predefinito di ogni tipo integrale è zero `0`.</span><span class="sxs-lookup"><span data-stu-id="bb01f-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="bb01f-134">Ogni tipo integrale ha costanti `MinValue` e `MaxValue` che specificano il valore minimo e massimo del tipo.</span><span class="sxs-lookup"><span data-stu-id="bb01f-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="bb01f-135">Usare la struttura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> per rappresentare un intero con segno senza limiti inferiori o superiori.</span><span class="sxs-lookup"><span data-stu-id="bb01f-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="bb01f-136">Valori letterali Integer</span><span class="sxs-lookup"><span data-stu-id="bb01f-136">Integer literals</span></span>

<span data-ttu-id="bb01f-137">I valori letterali integer possono essere</span><span class="sxs-lookup"><span data-stu-id="bb01f-137">Integer literals can be</span></span>

- <span data-ttu-id="bb01f-138">*decimal*: senza prefisso</span><span class="sxs-lookup"><span data-stu-id="bb01f-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="bb01f-139">*esadecimale*: con `0x` il `0X` prefisso o</span><span class="sxs-lookup"><span data-stu-id="bb01f-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="bb01f-140">*binary*: `0b` con `0B` il prefisso o (disponibile in C , 7.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="bb01f-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="bb01f-141">Il codice seguente illustra un esempio di ogni codice:The following code demonstrates an example of each:</span><span class="sxs-lookup"><span data-stu-id="bb01f-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="bb01f-142">Nell'esempio precedente viene illustrato `_` anche l'utilizzo di come separatore di *cifre*, che è supportato a partire da C .</span><span class="sxs-lookup"><span data-stu-id="bb01f-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="bb01f-143">È possibile utilizzare il separatore di cifre con tutti i tipi di valori letterali numerici.</span><span class="sxs-lookup"><span data-stu-id="bb01f-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="bb01f-144">Il tipo di un valore letterale integer è determinato dal relativo suffisso come segue:</span><span class="sxs-lookup"><span data-stu-id="bb01f-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="bb01f-145">Se il valore letterale non ha alcun suffisso, il tipo è `int` `uint`il `long` `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , , , .</span><span class="sxs-lookup"><span data-stu-id="bb01f-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="bb01f-146">Se il valore `U` letterale `u`è suffisso da o , il tipo è `uint`il `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , .</span><span class="sxs-lookup"><span data-stu-id="bb01f-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="bb01f-147">Se il valore `L` letterale `l`è suffisso da o , il tipo è `long`il `ulong`primo dei seguenti tipi in cui il relativo valore può essere rappresentato: , .</span><span class="sxs-lookup"><span data-stu-id="bb01f-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bb01f-148">È possibile utilizzare la `l` lettera minuscola come suffisso.</span><span class="sxs-lookup"><span data-stu-id="bb01f-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="bb01f-149">Tuttavia, questo genera un `l` avviso del compilatore `1`perché la lettera può essere confusa con la cifra .</span><span class="sxs-lookup"><span data-stu-id="bb01f-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="bb01f-150">Utilizzare `L` per chiarezza.</span><span class="sxs-lookup"><span data-stu-id="bb01f-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="bb01f-151">Se il valore letterale `uL`è `ul` `LU`suffisso `lU`da `lu` `UL`, `Ul`, `ulong`, , , `Lu`, o , il tipo è .</span><span class="sxs-lookup"><span data-stu-id="bb01f-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="bb01f-152">Se il valore rappresentato da un valore letterale Integer supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="bb01f-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="bb01f-153">Se il tipo determinato di `int` un valore letterale integer è e il valore rappresentato dal valore `sbyte` `byte`letterale è compreso nell'intervallo del tipo di destinazione, il valore può essere convertito in modo implicito `short`in , , `ushort`, , `uint`o `ulong`:</span><span class="sxs-lookup"><span data-stu-id="bb01f-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="bb01f-154">Come illustrato nell'esempio precedente, se il valore letterale non è compreso nell'intervallo del tipo di destinazione, si verifica un errore del compilatore [CS0031.](../../misc/cs0031.md)</span><span class="sxs-lookup"><span data-stu-id="bb01f-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="bb01f-155">È inoltre possibile utilizzare un cast per convertire il valore rappresentato da un valore letterale integer nel tipo diverso dal tipo determinato del valore letterale:</span><span class="sxs-lookup"><span data-stu-id="bb01f-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="bb01f-156">Conversioni</span><span class="sxs-lookup"><span data-stu-id="bb01f-156">Conversions</span></span>

<span data-ttu-id="bb01f-157">È possibile convertire qualsiasi tipo numerico integrale in qualsiasi altro tipo numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="bb01f-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="bb01f-158">Se il tipo di destinazione può archiviare tutti i valori del tipo di origine, la conversione è implicita.</span><span class="sxs-lookup"><span data-stu-id="bb01f-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="bb01f-159">In caso contrario, è necessario utilizzare [un'espressione cast](../operators/type-testing-and-cast.md#cast-expression) per eseguire una conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="bb01f-159">Otherwise, you need to use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span> <span data-ttu-id="bb01f-160">Per ulteriori informazioni, consultate [Conversioni numeriche predefinite.](numeric-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="bb01f-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb01f-161">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bb01f-161">C# language specification</span></span>

<span data-ttu-id="bb01f-162">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bb01f-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bb01f-163">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="bb01f-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="bb01f-164">Valori letterali Integer</span><span class="sxs-lookup"><span data-stu-id="bb01f-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="bb01f-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb01f-165">See also</span></span>

- [<span data-ttu-id="bb01f-166">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="bb01f-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bb01f-167">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="bb01f-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="bb01f-168">Tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="bb01f-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="bb01f-169">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="bb01f-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="bb01f-170">Valori numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="bb01f-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
