---
title: tipo char-riferimenti per C#
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: f771626e9777deab30e798559d847615d6124e6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205785"
---
# <a name="char-c-reference"></a><span data-ttu-id="4823e-102">char (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4823e-102">char (C# reference)</span></span>

<span data-ttu-id="4823e-103">La `char` parola chiave Type è un alias per il <xref:System.Char?displayProperty=nameWithType> tipo di struttura .NET che rappresenta un carattere Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4823e-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="4823e-104">Type</span><span class="sxs-lookup"><span data-stu-id="4823e-104">Type</span></span>|<span data-ttu-id="4823e-105">Range</span><span class="sxs-lookup"><span data-stu-id="4823e-105">Range</span></span>|<span data-ttu-id="4823e-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="4823e-106">Size</span></span>|<span data-ttu-id="4823e-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="4823e-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="4823e-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="4823e-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="4823e-109">16 bit</span><span class="sxs-lookup"><span data-stu-id="4823e-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="4823e-110">Il valore predefinito del `char` tipo è `\0` , ovvero U + 0000.</span><span class="sxs-lookup"><span data-stu-id="4823e-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="4823e-111">Il `char` tipo supporta operatori di [confronto](../operators/comparison-operators.md), [uguaglianza](../operators/equality-operators.md), [incremento](../operators/arithmetic-operators.md#increment-operator-)e [decremento](../operators/arithmetic-operators.md#decrement-operator---) .</span><span class="sxs-lookup"><span data-stu-id="4823e-111">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="4823e-112">Inoltre, per gli `char` operandi, gli operatori [logici](../operators/bitwise-and-shift-operators.md) [aritmetici](../operators/arithmetic-operators.md) e bit per bit eseguono un'operazione sui codici carattere corrispondenti e producono il risultato del `int` tipo.</span><span class="sxs-lookup"><span data-stu-id="4823e-112">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="4823e-113">Il tipo [stringa](reference-types.md#the-string-type) rappresenta il testo come una sequenza di `char` valori.</span><span class="sxs-lookup"><span data-stu-id="4823e-113">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="4823e-114">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="4823e-114">Literals</span></span>

<span data-ttu-id="4823e-115">È possibile specificare un `char` valore con:</span><span class="sxs-lookup"><span data-stu-id="4823e-115">You can specify a `char` value with:</span></span>

- <span data-ttu-id="4823e-116">valore letterale carattere.</span><span class="sxs-lookup"><span data-stu-id="4823e-116">a character literal.</span></span>
- <span data-ttu-id="4823e-117">sequenza di escape Unicode, `\u` seguita dalla rappresentazione esadecimale a quattro simboli di un codice carattere.</span><span class="sxs-lookup"><span data-stu-id="4823e-117">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="4823e-118">sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice carattere.</span><span class="sxs-lookup"><span data-stu-id="4823e-118">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="4823e-119">Come illustrato nell'esempio precedente, è anche possibile eseguire il cast del valore di un codice carattere nel `char` valore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4823e-119">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="4823e-120">Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="4823e-120">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="4823e-121">Ovvero, `\u006A` è una sequenza di escape valida, mentre `\u06A` e `\u6A` non sono validi.</span><span class="sxs-lookup"><span data-stu-id="4823e-121">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="4823e-122">Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="4823e-122">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="4823e-123">Ovvero le `\x006A` `\x06A` `\x6A` sequenze di escape, e sono valide e corrispondono allo stesso carattere.</span><span class="sxs-lookup"><span data-stu-id="4823e-123">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="4823e-124">Conversioni</span><span class="sxs-lookup"><span data-stu-id="4823e-124">Conversions</span></span>

<span data-ttu-id="4823e-125">Il `char` tipo è convertibile in modo implicito nei tipi [integrali](integral-numeric-types.md) seguenti: `ushort` ,, `int` `uint` , `long` e `ulong` .</span><span class="sxs-lookup"><span data-stu-id="4823e-125">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="4823e-126">È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](floating-point-numeric-types.md) predefiniti: `float` , `double` e `decimal` .</span><span class="sxs-lookup"><span data-stu-id="4823e-126">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="4823e-127">È convertibile in modo esplicito in `sbyte` `byte` `short` tipi integrali, e.</span><span class="sxs-lookup"><span data-stu-id="4823e-127">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="4823e-128">Non esistono conversioni implicite da altri tipi al `char` tipo.</span><span class="sxs-lookup"><span data-stu-id="4823e-128">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="4823e-129">Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o a [virgola mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in `char` .</span><span class="sxs-lookup"><span data-stu-id="4823e-129">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4823e-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4823e-130">C# language specification</span></span>

<span data-ttu-id="4823e-131">Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4823e-131">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4823e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4823e-132">See also</span></span>

- [<span data-ttu-id="4823e-133">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="4823e-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4823e-134">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="4823e-134">Value types</span></span>](value-types.md)
- [<span data-ttu-id="4823e-135">Stringhe</span><span class="sxs-lookup"><span data-stu-id="4823e-135">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="4823e-136">Codifica dei caratteri in .NET</span><span class="sxs-lookup"><span data-stu-id="4823e-136">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
