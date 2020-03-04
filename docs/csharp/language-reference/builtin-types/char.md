---
title: tipo char- C# riferimento
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: a5aca12e4037d517c3bcfb403c990605a052d48f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239846"
---
# <a name="char-c-reference"></a><span data-ttu-id="3f4c0-102">char (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="3f4c0-102">char (C# reference)</span></span>

<span data-ttu-id="3f4c0-103">La parola chiave `char` Type è un alias per il tipo di struttura <xref:System.Char?displayProperty=nameWithType> .NET che rappresenta un carattere Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="3f4c0-104">Type</span><span class="sxs-lookup"><span data-stu-id="3f4c0-104">Type</span></span>|<span data-ttu-id="3f4c0-105">Range</span><span class="sxs-lookup"><span data-stu-id="3f4c0-105">Range</span></span>|<span data-ttu-id="3f4c0-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="3f4c0-106">Size</span></span>|<span data-ttu-id="3f4c0-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="3f4c0-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="3f4c0-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="3f4c0-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="3f4c0-109">16 bit</span><span class="sxs-lookup"><span data-stu-id="3f4c0-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="3f4c0-110">Il valore predefinito del tipo di `char` è `\0`, ovvero U + 0000.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="3f4c0-111">Il tipo [stringa](reference-types.md#the-string-type) rappresenta il testo come sequenza di valori `char`.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="3f4c0-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="3f4c0-112">Literals</span></span>

<span data-ttu-id="3f4c0-113">È possibile specificare un valore `char` con:</span><span class="sxs-lookup"><span data-stu-id="3f4c0-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="3f4c0-114">valore letterale carattere.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-114">a character literal.</span></span>
- <span data-ttu-id="3f4c0-115">sequenza di escape Unicode, che è `\u` seguita dalla rappresentazione esadecimale a quattro simboli di un codice carattere.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="3f4c0-116">sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice carattere.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/snippets/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="3f4c0-117">Come illustrato nell'esempio precedente, è anche possibile eseguire il cast del valore di un codice carattere nel valore `char` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="3f4c0-118">Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="3f4c0-119">Ovvero, `\u006A` è una sequenza di escape valida, mentre `\u06A` e `\u6A` non sono validi.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="3f4c0-120">Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="3f4c0-121">Ovvero le sequenze di escape `\x006A`, `\x06A`e `\x6A` sono valide e corrispondono allo stesso carattere.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="3f4c0-122">Conversioni</span><span class="sxs-lookup"><span data-stu-id="3f4c0-122">Conversions</span></span>

<span data-ttu-id="3f4c0-123">Il tipo di `char` è convertibile in modo implicito nei tipi [integrali](integral-numeric-types.md) seguenti: `ushort`, `int`, `uint`, `long`e `ulong`.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="3f4c0-124">È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](floating-point-numeric-types.md) predefiniti: `float`, `double`e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="3f4c0-125">È convertibile in modo esplicito in `sbyte`, `byte`e `short` i tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="3f4c0-126">Non esistono conversioni implicite da altri tipi al tipo di `char`.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="3f4c0-127">Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o a [virgola mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in `char`.</span><span class="sxs-lookup"><span data-stu-id="3f4c0-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3f4c0-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3f4c0-128">C# language specification</span></span>

<span data-ttu-id="3f4c0-129">Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3f4c0-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f4c0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f4c0-130">See also</span></span>

- [<span data-ttu-id="3f4c0-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3f4c0-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3f4c0-132">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="3f4c0-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="3f4c0-133">Stringhe</span><span class="sxs-lookup"><span data-stu-id="3f4c0-133">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
