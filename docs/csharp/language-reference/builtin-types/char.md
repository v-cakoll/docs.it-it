---
title: Tipo di char - Riferimenti per C
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: c4e29e6437edfe549b36a04a2050f63caa0d3d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846522"
---
# <a name="char-c-reference"></a><span data-ttu-id="e992c-102">char (riferimenti per C</span><span class="sxs-lookup"><span data-stu-id="e992c-102">char (C# reference)</span></span>

<span data-ttu-id="e992c-103">La `char` parola chiave type è <xref:System.Char?displayProperty=nameWithType> un alias per il tipo di struttura .NET che rappresenta un carattere Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="e992c-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="e992c-104">Type</span><span class="sxs-lookup"><span data-stu-id="e992c-104">Type</span></span>|<span data-ttu-id="e992c-105">Range</span><span class="sxs-lookup"><span data-stu-id="e992c-105">Range</span></span>|<span data-ttu-id="e992c-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="e992c-106">Size</span></span>|<span data-ttu-id="e992c-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="e992c-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="e992c-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="e992c-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="e992c-109">16 bit</span><span class="sxs-lookup"><span data-stu-id="e992c-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="e992c-110">Il valore predefinito `char` del `\0`tipo è , ovvero U.</span><span class="sxs-lookup"><span data-stu-id="e992c-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="e992c-111">Il tipo [string](reference-types.md#the-string-type) rappresenta il `char` testo come una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="e992c-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="e992c-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="e992c-112">Literals</span></span>

<span data-ttu-id="e992c-113">È possibile `char` specificare un valore con:You can specify a value with:</span><span class="sxs-lookup"><span data-stu-id="e992c-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="e992c-114">un valore letterale carattere.</span><span class="sxs-lookup"><span data-stu-id="e992c-114">a character literal.</span></span>
- <span data-ttu-id="e992c-115">una sequenza di `\u` escape Unicode, seguita dalla rappresentazione esadecimale a quattro simboli di un codice di carattere.</span><span class="sxs-lookup"><span data-stu-id="e992c-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="e992c-116">una sequenza di escape esadecimale, `\x` seguita dalla rappresentazione esadecimale di un codice di carattere.</span><span class="sxs-lookup"><span data-stu-id="e992c-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="e992c-117">Come illustrato nell'esempio precedente, è anche possibile eseguire il `char` cast del valore di un codice carattere nel valore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e992c-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="e992c-118">Nel caso di una sequenza di escape Unicode, è necessario specificare tutte e quattro le cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="e992c-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="e992c-119">Ovvero, `\u006A` è una sequenza `\u06A` di `\u6A` escape valida, mentre e non sono validi.</span><span class="sxs-lookup"><span data-stu-id="e992c-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="e992c-120">Nel caso di una sequenza di escape esadecimale, è possibile omettere gli zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="e992c-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="e992c-121">Ovvero, le `\x006A` `\x06A`sequenze `\x6A` , e escape sono valide e corrispondono allo stesso carattere.</span><span class="sxs-lookup"><span data-stu-id="e992c-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="e992c-122">Conversioni</span><span class="sxs-lookup"><span data-stu-id="e992c-122">Conversions</span></span>

<span data-ttu-id="e992c-123">Il `char` tipo è convertibile in modo implicito `uint` `long`nei `ulong`seguenti tipi [integrali:](integral-numeric-types.md) `ushort`, `int`, , , e .</span><span class="sxs-lookup"><span data-stu-id="e992c-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="e992c-124">È inoltre convertibile in modo implicito nei tipi numerici `double`a `decimal` [virgola mobile](floating-point-numeric-types.md) incorporati: `float`, , e .</span><span class="sxs-lookup"><span data-stu-id="e992c-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="e992c-125">È convertibile in `sbyte`modo `byte`esplicito in tipi , e `short` integrali.</span><span class="sxs-lookup"><span data-stu-id="e992c-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="e992c-126">Non esistono conversioni implicite da `char` altri tipi al tipo.</span><span class="sxs-lookup"><span data-stu-id="e992c-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="e992c-127">Tuttavia, qualsiasi tipo numerico [integrale](integral-numeric-types.md) o `char`a virgola [mobile](floating-point-numeric-types.md) è convertibile in modo esplicito in .</span><span class="sxs-lookup"><span data-stu-id="e992c-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e992c-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e992c-128">C# language specification</span></span>

<span data-ttu-id="e992c-129">Per ulteriori informazioni, vedere la sezione [relativa ai tipi integrali](~/_csharplang/spec/types.md#integral-types) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)</span><span class="sxs-lookup"><span data-stu-id="e992c-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e992c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e992c-130">See also</span></span>

- [<span data-ttu-id="e992c-131">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="e992c-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e992c-132">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="e992c-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="e992c-133">Stringhe</span><span class="sxs-lookup"><span data-stu-id="e992c-133">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
