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
ms.openlocfilehash: 63f8871926e8c279678c59a2256bef46b2ff514e
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698783"
---
# <a name="char-c-reference"></a><span data-ttu-id="1ac3e-102">char (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1ac3e-102">char (C# Reference)</span></span>

<span data-ttu-id="1ac3e-103">La parola chiave `char` è usata per dichiarare un'istanza della struttura <xref:System.Char?displayProperty=nameWithType> usata da .NET Framework per rappresentare un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="1ac3e-104">Il valore di un oggetto `Char` è un valore numerico (ordinale) a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="1ac3e-105">I caratteri Unicode vengono usati per rappresentare la maggior parte delle lingue scritte di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="1ac3e-106">Type</span><span class="sxs-lookup"><span data-stu-id="1ac3e-106">Type</span></span>|<span data-ttu-id="1ac3e-107">Intervallo</span><span class="sxs-lookup"><span data-stu-id="1ac3e-107">Range</span></span>|<span data-ttu-id="1ac3e-108">Size</span><span class="sxs-lookup"><span data-stu-id="1ac3e-108">Size</span></span>|<span data-ttu-id="1ac3e-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="1ac3e-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="1ac3e-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="1ac3e-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="1ac3e-111">Carattere Unicode a 16 bit</span><span class="sxs-lookup"><span data-stu-id="1ac3e-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="1ac3e-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="1ac3e-112">Literals</span></span>

<span data-ttu-id="1ac3e-113">Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="1ac3e-114">È anche possibile eseguire il cast dei codici a caratteri integrali.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="1ac3e-115">Nell'esempio seguente i quattro elementi di una matrice di `char` vengono inizializzati con lo stesso carattere `X`:</span><span class="sxs-lookup"><span data-stu-id="1ac3e-115">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="1ac3e-116">Conversioni</span><span class="sxs-lookup"><span data-stu-id="1ac3e-116">Conversions</span></span>

<span data-ttu-id="1ac3e-117">`char` può essere convertito in modo implicito in [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) o [decimal](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ac3e-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="1ac3e-118">Non è tuttavia disponibile nessuna conversione implicita da altri tipi nel tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="1ac3e-119">Il tipo <xref:System.Char?displayProperty=nameWithType> offre diversi metodi statici per usare i valori `char`.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1ac3e-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1ac3e-120">C# language specification</span></span>  

<span data-ttu-id="1ac3e-121">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ac3e-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="1ac3e-122">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="1ac3e-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ac3e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ac3e-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="1ac3e-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1ac3e-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1ac3e-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1ac3e-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1ac3e-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1ac3e-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1ac3e-127">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="1ac3e-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="1ac3e-128">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="1ac3e-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="1ac3e-129">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="1ac3e-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="1ac3e-130">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="1ac3e-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
- [<span data-ttu-id="1ac3e-131">Stringhe</span><span class="sxs-lookup"><span data-stu-id="1ac3e-131">Strings</span></span>](../../programming-guide/strings/index.md)
