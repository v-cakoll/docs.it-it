---
title: $ - interpolazione di stringhe - Riferimenti per C#
ms.custom: seodec18
description: L'interpolazione di stringhe offro una sintassi più leggibile e pratica per la formattazione dell'output di tipo stringa rispetto alla formattazione composita tradizionale.
ms.date: 04/29/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 716f6ee2c9eb09abcbd4ada16954315ed4a56c02
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210434"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="230bf-103">$ - interpolazione di stringhe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="230bf-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="230bf-104">Il carattere speciale `$` identifica una stringa letterale come *stringa interpolata*.</span><span class="sxs-lookup"><span data-stu-id="230bf-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="230bf-105">Una stringa interpolata è un valore letterale stringa che può contenere *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="230bf-105">An interpolated string is a string literal that might contain *interpolated expressions*.</span></span> <span data-ttu-id="230bf-106">Quando una stringa interpolata viene risolta in una stringa di risultato, gli elementi con espressioni interpolate vengono sostituiti dalle rappresentazioni stringa dei risultati dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="230bf-106">When an interpolated string is resolved to a result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="230bf-107">Questa funzionalità è disponibile in C# 6 e versioni successive del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="230bf-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="230bf-108">L'interpolazione di stringhe offre una sintassi più leggibile e pratica per creare stringhe formattate rispetto alla funzionalità di [formattazione composita delle stringhe](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="230bf-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="230bf-109">L'esempio seguente usa entrambe le funzionalità per produrre lo stesso output:</span><span class="sxs-lookup"><span data-stu-id="230bf-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="230bf-110">Struttura di una stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="230bf-110">Structure of an interpolated string</span></span>

<span data-ttu-id="230bf-111">Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="230bf-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="230bf-112">Tra `$` e il simbolo `"` all'inizio del valore letterale stringa non possono essere presenti spazi vuoti,</span><span class="sxs-lookup"><span data-stu-id="230bf-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="230bf-113">altrimenti si genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="230bf-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="230bf-114">La struttura di un elemento con un'espressione interpolata è la seguente:</span><span class="sxs-lookup"><span data-stu-id="230bf-114">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="230bf-115">Gli elementi tra parentesi quadre sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="230bf-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="230bf-116">La tabella seguente descrive i singoli elementi:</span><span class="sxs-lookup"><span data-stu-id="230bf-116">The following table describes each element:</span></span>

|<span data-ttu-id="230bf-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="230bf-117">Element</span></span>|<span data-ttu-id="230bf-118">Description</span><span class="sxs-lookup"><span data-stu-id="230bf-118">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="230bf-119">Espressione che produce un risultato da formattare.</span><span class="sxs-lookup"><span data-stu-id="230bf-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="230bf-120">La rappresentazione stringa del risultato `null` è <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="230bf-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="230bf-121">Espressione costante il cui valore definisce il numero minimo di caratteri della rappresentazione stringa del risultato dell'espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="230bf-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="230bf-122">Se è positivo, la rappresentazione stringa è allineata a destra; se è negativo la rappresentazione stringa è allineata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="230bf-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="230bf-123">Per altre informazioni, vedere [Componente di allineamento](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="230bf-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="230bf-124">Stringa di formato supportata dal tipo di risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="230bf-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="230bf-125">Per altre informazioni, vedere [Componente della stringa di formato](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="230bf-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="230bf-126">L'esempio seguente usa i componenti di formattazione facoltativi descritti in precedenza:</span><span class="sxs-lookup"><span data-stu-id="230bf-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="230bf-127">Caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="230bf-127">Special characters</span></span>

<span data-ttu-id="230bf-128">Per includere una parentesi graffa, "{" o "}", nel testo prodotto da una stringa interpolata, digitare due parentesi graffe, ovvero "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="230bf-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="230bf-129">Per altre informazioni, vedere [Sequenze di escape delle parentesi graffe](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="230bf-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="230bf-130">Dato che i due punti (":") hanno un significato speciale in un elemento espressione interpolata, se si vuole usare un [operatore condizionale](../operators/conditional-operator.md) in un'espressione interpolata, racchiudere l'espressione tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="230bf-130">As the colon (":") has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="230bf-131">L'esempio seguente illustra come includere una parentesi graffa in una stringa di risultato e come usare un operatore condizionale in un'espressione interpolata:</span><span class="sxs-lookup"><span data-stu-id="230bf-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="230bf-132">Una stringa interpolata verbatim inizia con il carattere `$` seguito dal carattere `@`.</span><span class="sxs-lookup"><span data-stu-id="230bf-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="230bf-133">Per altre informazioni sulle stringhe verbatim, vedere gli argomenti relativi a [string](../keywords/string.md) e all'[identificatore verbatim](verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="230bf-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="230bf-134">Il token `$` deve precedere il token `@` in una stringa interpolata verbatim.</span><span class="sxs-lookup"><span data-stu-id="230bf-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="230bf-135">Conversioni implicite e indicazione dell'implementazione di `IFormatProvider`</span><span class="sxs-lookup"><span data-stu-id="230bf-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="230bf-136">Da una stringa interpolata vengono effettuate tre conversioni implicite:</span><span class="sxs-lookup"><span data-stu-id="230bf-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="230bf-137">Conversione di una stringa interpolata in un'istanza <xref:System.String> che rappresenta il risultato della risoluzione della stringa interpolata, dove gli elementi dell'espressione interpolata vengono sostituiti con le rappresentazioni stringa dei risultati, formattate correttamente.</span><span class="sxs-lookup"><span data-stu-id="230bf-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="230bf-138">Questa conversione usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="230bf-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="230bf-139">Conversione di una stringa interpolata in un'istanza di <xref:System.FormattableString> che rappresenta una stringa di formato composito e i risultati dell'espressione da formattare.</span><span class="sxs-lookup"><span data-stu-id="230bf-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="230bf-140">Questa opzione consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="230bf-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="230bf-141">A tale scopo, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="230bf-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="230bf-142">Un overload <xref:System.FormattableString.ToString> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="230bf-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="230bf-143">Un metodo <xref:System.FormattableString.Invariant%2A> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="230bf-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="230bf-144">Un metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> che produce una stringa risultato per impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="230bf-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="230bf-145">È anche possibile usare il metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> per fornire un'implementazione definita dall'utente dell'interfaccia <xref:System.IFormatProvider> che supporta la formattazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="230bf-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="230bf-146">Per altre informazioni, vedere [Formattazione personalizzata con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="230bf-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="230bf-147">Conversione di una stringa interpolata in un'istanza di <xref:System.IFormattable> che consente anche di creare più stringhe risultato con contenuto associato a impostazioni cultura specifiche da una singola istanza di <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="230bf-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="230bf-148">L'esempio seguente usa la conversione implicita a <xref:System.FormattableString> per creare stringhe di risultato con impostazioni cultura specifiche:</span><span class="sxs-lookup"><span data-stu-id="230bf-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="230bf-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="230bf-149">Additional resources</span></span>

<span data-ttu-id="230bf-150">Se non si ha familiarità con l'interpolazione di stringhe, vedere l'esercitazione interattiva [Interpolazione di stringhe in C#](../../tutorials/exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="230bf-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="230bf-151">È anche possibile verificare un'altra esercitazione di [interpolazione di stringhe in C#](../../tutorials/string-interpolation.md) che illustra come usare le stringhe interpolate per produrre stringhe formattate.</span><span class="sxs-lookup"><span data-stu-id="230bf-151">You also can check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="230bf-152">Compilazione di stringhe interpolate</span><span class="sxs-lookup"><span data-stu-id="230bf-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="230bf-153">Se una stringa interpolata è di tipo `string`, viene in genere trasformata in una chiamata al metodo <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="230bf-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="230bf-154">Il compilatore può sostituire <xref:System.String.Format%2A?displayProperty=nameWithType> con <xref:System.String.Concat%2A?displayProperty=nameWithType> se il comportamento analizzato è equivalente alla concatenazione.</span><span class="sxs-lookup"><span data-stu-id="230bf-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="230bf-155">Se una stringa interpolata dispone del tipo <xref:System.IFormattable> o <xref:System.FormattableString>, il compilatore genera una chiamata al metodo <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="230bf-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="230bf-156">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="230bf-156">C# language specification</span></span>

<span data-ttu-id="230bf-157">Per altre informazioni, vedere la sezione [Stringhe interpolate](~/_csharplang/spec/expressions.md#interpolated-strings) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="230bf-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="230bf-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="230bf-158">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="230bf-159">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="230bf-159">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="230bf-160">Tabella di formattazione dei risultati numerici</span><span class="sxs-lookup"><span data-stu-id="230bf-160">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="230bf-161">Stringhe</span><span class="sxs-lookup"><span data-stu-id="230bf-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="230bf-162">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="230bf-162">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="230bf-163">Caratteri speciali di C#</span><span class="sxs-lookup"><span data-stu-id="230bf-163">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="230bf-164">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="230bf-164">C# Reference</span></span>](../index.md)
