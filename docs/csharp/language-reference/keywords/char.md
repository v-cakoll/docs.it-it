---
title: Parola chiave char - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 0b4f04a1ba6244373e36cc6a6188edabe33ec453
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424348"
---
# <a name="char-c-reference"></a><span data-ttu-id="0bb02-102">char (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0bb02-102">char (C# Reference)</span></span>

<span data-ttu-id="0bb02-103">La parola chiave `char` è usata per dichiarare un'istanza della struttura <xref:System.Char?displayProperty=nameWithType> usata da .NET Framework per rappresentare un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="0bb02-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="0bb02-104">Il valore di un oggetto `Char` è un valore numerico (ordinale) a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="0bb02-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="0bb02-105">I caratteri Unicode vengono usati per rappresentare la maggior parte delle lingue scritte di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="0bb02-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="0bb02-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bb02-106">Type</span></span>|<span data-ttu-id="0bb02-107">Intervallo</span><span class="sxs-lookup"><span data-stu-id="0bb02-107">Range</span></span>|<span data-ttu-id="0bb02-108">Dimensione</span><span class="sxs-lookup"><span data-stu-id="0bb02-108">Size</span></span>|<span data-ttu-id="0bb02-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="0bb02-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="0bb02-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="0bb02-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="0bb02-111">Carattere Unicode a 16 bit</span><span class="sxs-lookup"><span data-stu-id="0bb02-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="0bb02-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="0bb02-112">Literals</span></span>

<span data-ttu-id="0bb02-113">Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode.</span><span class="sxs-lookup"><span data-stu-id="0bb02-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="0bb02-114">È anche possibile eseguire il cast dei codici a caratteri integrali.</span><span class="sxs-lookup"><span data-stu-id="0bb02-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="0bb02-115">Nell'esempio seguente vengono inizializzate quattro variabili `char` con lo stesso carattere `X`:</span><span class="sxs-lookup"><span data-stu-id="0bb02-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="0bb02-116">Conversioni</span><span class="sxs-lookup"><span data-stu-id="0bb02-116">Conversions</span></span>

<span data-ttu-id="0bb02-117">`char` può essere convertito in modo implicito in [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="0bb02-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="0bb02-118">Non è tuttavia disponibile nessuna conversione implicita da altri tipi nel tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="0bb02-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="0bb02-119">Il tipo <xref:System.Char?displayProperty=nameWithType> offre diversi metodi statici per usare i valori `char`.</span><span class="sxs-lookup"><span data-stu-id="0bb02-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0bb02-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0bb02-120">C# language specification</span></span>  

<span data-ttu-id="0bb02-121">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0bb02-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="0bb02-122">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="0bb02-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bb02-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bb02-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="0bb02-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0bb02-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="0bb02-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0bb02-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0bb02-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="0bb02-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="0bb02-127">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="0bb02-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="0bb02-128">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="0bb02-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="0bb02-129">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="0bb02-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="0bb02-130">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="0bb02-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="0bb02-131">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="0bb02-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
- [<span data-ttu-id="0bb02-132">Stringhe</span><span class="sxs-lookup"><span data-stu-id="0bb02-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
