---
title: parola chiave char C# -riferimento
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771792"
---
# <a name="char-c-reference"></a><span data-ttu-id="0b41b-102">char (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="0b41b-102">char (C# reference)</span></span>

<span data-ttu-id="0b41b-103">La parola chiave `char` Type è un alias per il tipo di struttura <xref:System.Char?displayProperty=nameWithType> .NET che rappresenta un carattere Unicode UTF-16:</span><span class="sxs-lookup"><span data-stu-id="0b41b-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="0b41b-104">Digitare</span><span class="sxs-lookup"><span data-stu-id="0b41b-104">Type</span></span>|<span data-ttu-id="0b41b-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="0b41b-105">Range</span></span>|<span data-ttu-id="0b41b-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="0b41b-106">Size</span></span>|<span data-ttu-id="0b41b-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="0b41b-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="0b41b-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="0b41b-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="0b41b-109">16 bit</span><span class="sxs-lookup"><span data-stu-id="0b41b-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="0b41b-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="0b41b-110">Literals</span></span>

<span data-ttu-id="0b41b-111">Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode.</span><span class="sxs-lookup"><span data-stu-id="0b41b-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="0b41b-112">È anche possibile eseguire il cast di un codice carattere integrale nel valore `char` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0b41b-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="0b41b-113">Nell'esempio seguente i quattro elementi di una matrice di `char` vengono inizializzati con lo stesso carattere `X`:</span><span class="sxs-lookup"><span data-stu-id="0b41b-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="0b41b-114">Conversioni</span><span class="sxs-lookup"><span data-stu-id="0b41b-114">Conversions</span></span>

<span data-ttu-id="0b41b-115">Il tipo di `char` è convertibile in modo implicito nei tipi [integrali](../builtin-types/integral-numeric-types.md) seguenti: `ushort`, `int`, `uint`, `long` e `ulong`.</span><span class="sxs-lookup"><span data-stu-id="0b41b-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="0b41b-116">È anche convertibile in modo implicito nei tipi numerici a [virgola mobile](../builtin-types/floating-point-numeric-types.md) predefiniti: `float`, `double` e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0b41b-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="0b41b-117">È convertibile in modo esplicito in `sbyte`, `byte` e `short` i tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="0b41b-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="0b41b-118">Non esistono conversioni implicite da altri tipi al tipo di `char`.</span><span class="sxs-lookup"><span data-stu-id="0b41b-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="0b41b-119">Tuttavia, qualsiasi tipo numerico [integrale](../builtin-types/integral-numeric-types.md) o a [virgola mobile](../builtin-types/floating-point-numeric-types.md) è convertibile in modo esplicito in `char`.</span><span class="sxs-lookup"><span data-stu-id="0b41b-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b41b-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0b41b-120">C# language specification</span></span>

<span data-ttu-id="0b41b-121">Per ulteriori informazioni, vedere la sezione [tipi integrali](~/_csharplang/spec/types.md#integral-types) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b41b-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b41b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b41b-122">See also</span></span>

- [<span data-ttu-id="0b41b-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0b41b-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0b41b-124">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="0b41b-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="0b41b-125">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="0b41b-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="0b41b-126">Stringhe</span><span class="sxs-lookup"><span data-stu-id="0b41b-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
