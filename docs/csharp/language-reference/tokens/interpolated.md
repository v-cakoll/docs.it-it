---
title: $ - interpolazione di stringhe (Riferimenti per C#)
description: L'interpolazione di stringhe offro una sintassi più leggibile e pratica per la formattazione dell'output di tipo stringa rispetto alla formattazione composita tradizionale.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cabb40c9c449780c8c2a504aad3e53938e2ed957
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="89554-103">$ - interpolazione di stringhe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="89554-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="89554-104">Il carattere speciale `$` identifica una stringa letterale come *stringa interpolata*.</span><span class="sxs-lookup"><span data-stu-id="89554-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="89554-105">Una stringa interpolata è simile a una stringa di modello che contiene *espressioni interpolate*.</span><span class="sxs-lookup"><span data-stu-id="89554-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="89554-106">Quando la stringa interpolata viene risolta nella stringa di risultato, gli elementi con espressioni interpolate vengono sostituiti dalle rappresentazioni stringa dei risultati dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="89554-106">When the interpolated string is resolved to the result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="89554-107">Questa funzionalità è disponibile in C# 6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="89554-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="89554-108">L'interpolazione di stringhe offre una sintassi più leggibile e pratica per creare stringhe formattate rispetto alla funzionalità di [formattazione composita delle stringhe](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="89554-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="89554-109">L'esempio seguente usa entrambe le funzionalità per produrre lo stesso output:</span><span class="sxs-lookup"><span data-stu-id="89554-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="89554-110">Tra `$` e il simbolo `"` all'inizio della stringa non possono essere presenti spazi vuoti,</span><span class="sxs-lookup"><span data-stu-id="89554-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="89554-111">altrimenti si genera un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89554-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="89554-112">La struttura di un elemento con un'espressione interpolata è la seguente:</span><span class="sxs-lookup"><span data-stu-id="89554-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="89554-113">Gli elementi tra parentesi quadre sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="89554-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="89554-114">La tabella seguente descrive i singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="89554-114">The following table describes each element.</span></span>

|<span data-ttu-id="89554-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="89554-115">Element</span></span>|<span data-ttu-id="89554-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89554-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="89554-117">Espressione da valutare per ottenere il risultato da formattare.</span><span class="sxs-lookup"><span data-stu-id="89554-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="89554-118">La rappresentazione stringa del risultato `null` è <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89554-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="89554-119">Espressione costante il cui valore definisce il numero minimo di caratteri della rappresentazione stringa del risultato dell'espressione interpolata.</span><span class="sxs-lookup"><span data-stu-id="89554-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="89554-120">Se è positivo, la rappresentazione stringa è allineata a destra; se è negativo la rappresentazione stringa è allineata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="89554-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="89554-121">Per altre informazioni, vedere [Componente di allineamento](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="89554-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="89554-122">Stringa con formato standard o personalizzato supportato dal tipo di risultato dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="89554-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="89554-123">Per altre informazioni, vedere [Componente della stringa di formato](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="89554-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="89554-124">L'esempio seguente usa i componenti di formattazione facoltativi descritti in precedenza:</span><span class="sxs-lookup"><span data-stu-id="89554-124">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="89554-125">Per includere una parentesi graffa ("{" o "}") nel testo prodotto da una stringa interpolata, digitare due parentesi graffe, ovvero "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="89554-125">To include a brace ("{" or "}") in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="89554-126">Per altre informazioni, vedere [Sequenze di escape delle parentesi graffe](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="89554-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="89554-127">Dato che i due punti (:) hanno un significato speciale in un elemento espressione interpolata, se si vuole usare un [operatore condizionale](../operators/conditional-operator.md) in un'espressione interpolata, racchiudere l'espressione tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="89554-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="89554-128">L'esempio seguente illustra come includere una parentesi graffa nella stringa del risultato e come usare un operatore condizionale in un'espressione interpolata:</span><span class="sxs-lookup"><span data-stu-id="89554-128">The following example shows how to include a brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="89554-129">Le stringe interpolate verbatim usano il carattere `$` seguito dal carattere `@`.</span><span class="sxs-lookup"><span data-stu-id="89554-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="89554-130">Per altre informazioni sulle stringhe verbatim, vedere l'argomento relativo a [string](../keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="89554-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="89554-131">Il token `$` deve precedere il token `@` in una stringa interpolata verbatim.</span><span class="sxs-lookup"><span data-stu-id="89554-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

<span data-ttu-id="89554-132">Da una stringa interpolata vengono effettuate tre conversioni implicite:</span><span class="sxs-lookup"><span data-stu-id="89554-132">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="89554-133">Conversione di una stringa interpolata in un'istanza <xref:System.String> che rappresenta il risultato della risoluzione della stringa interpolata, dove gli elementi dell'espressione interpolata vengono sostituiti con le rappresentazioni stringa dei risultati, formattate correttamente.</span><span class="sxs-lookup"><span data-stu-id="89554-133">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="89554-134">Questa conversione usa le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="89554-134">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="89554-135">Conversione di una stringa interpolata in un'istanza di <xref:System.FormattableString> che rappresenta una stringa di formato composito e i risultati dell'espressione da formattare.</span><span class="sxs-lookup"><span data-stu-id="89554-135">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="89554-136">Questa opzione consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="89554-136">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="89554-137">A tale scopo, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="89554-137">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="89554-138">Un overload <xref:System.FormattableString.ToString> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.CurrentCulture>.</span><span class="sxs-lookup"><span data-stu-id="89554-138">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="89554-139">Un metodo <xref:System.FormattableString.Invariant%2A> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="89554-139">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="89554-140">Un metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> che produce una stringa risultato per impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="89554-140">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="89554-141">Conversione di una stringa interpolata in un'istanza di <xref:System.IFormattable> che consente anche di creare più stringhe risultato con contenuto associato a impostazioni cultura specifiche da una singola istanza di <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="89554-141">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="89554-142">L'esempio seguente usa la conversione implicita a <xref:System.FormattableString> per creare stringhe di risultato con impostazioni cultura specifiche:</span><span class="sxs-lookup"><span data-stu-id="89554-142">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

<span data-ttu-id="89554-143">Se non si ha familiarità con l'interpolazione di stringhe, vedere la guida introduttiva [Interpolazione di stringhe in C#](../../quick-starts/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="89554-143">If you are new to the string interpolation, check the [String interpolation in C#](../../quick-starts/interpolated-strings.yml) quickstart.</span></span> <span data-ttu-id="89554-144">Per altri esempi, vedere l'[esercitazione sull'interpolazione di stringhe](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="89554-144">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89554-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89554-145">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="89554-146">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="89554-146">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="89554-147">Stringhe</span><span class="sxs-lookup"><span data-stu-id="89554-147">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="89554-148">Caratteri speciali di C#</span><span class="sxs-lookup"><span data-stu-id="89554-148">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="89554-149">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="89554-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="89554-150">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="89554-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  