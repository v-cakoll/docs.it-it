---
title: Interpolazione di stringhe in C#
description: Informazioni su come includere risultati di espressione formattati in una stringa di risultato in C# con interpolazione.
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: ef4358ff61cde43998fc0dc4ba174dc0f06bc2bd
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222493"
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="2fd99-103">Interpolazione di stringhe in C#</span><span class="sxs-lookup"><span data-stu-id="2fd99-103">String interpolation in C#</span></span> #

<span data-ttu-id="2fd99-104">Questa esercitazione illustra come usare l'[interpolazione di stringhe](../language-reference/tokens/interpolated.md) per formattare e includere risultati di espressione in una stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="2fd99-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="2fd99-105">Gli esempi presuppongono una buona familiarità con i concetti di base del linguaggio C# e con la formattazione dei tipi in .NET.</span><span class="sxs-lookup"><span data-stu-id="2fd99-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="2fd99-106">Se non si ha familiarità con l'interpolazione di stringhe o con la formattazione dei tipi in .NET, vedere prima l'[esercitazione interattiva sull'interpolazione di stringhe](../tutorials/intro-to-csharp/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="2fd99-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation tutorial](../tutorials/intro-to-csharp/interpolated-strings.yml) first.</span></span> <span data-ttu-id="2fd99-107">Per altre informazioni sulla formattazione dei tipi in .NET, vedere l'argomento [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="2fd99-108">Introduzione</span><span class="sxs-lookup"><span data-stu-id="2fd99-108">Introduction</span></span>

<span data-ttu-id="2fd99-109">La funzionalità di [interpolazione di stringhe](../language-reference/tokens/interpolated.md), basata sulla funzionalità di [formattazione composita](../../standard/base-types/composite-formatting.md), offre una sintassi più leggibile e pratica per includere risultati di espressione formattati in una stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="2fd99-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="2fd99-110">Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`.</span><span class="sxs-lookup"><span data-stu-id="2fd99-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="2fd99-111">È possibile incorporare in una stringa interpolata qualsiasi espressione C# valida che restituisca un valore.</span><span class="sxs-lookup"><span data-stu-id="2fd99-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="2fd99-112">Nell'esempio seguente, non appena un'espressione viene valutata, il suo risultato viene convertito in una stringa e incluso in una stringa di risultato:</span><span class="sxs-lookup"><span data-stu-id="2fd99-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="2fd99-113">Come illustrato nell'esempio, per includere un'espressione in una stringa interpolata è necessario racchiuderla tra parentesi graffe:</span><span class="sxs-lookup"><span data-stu-id="2fd99-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```
{<interpolatedExpression>}
```

<span data-ttu-id="2fd99-114">In fase di compilazione, una stringa interpolata viene in genere trasformata in una chiamata al metodo <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fd99-114">At compile time, an interpolated string is typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="2fd99-115">In questo modo tutte le caratteristiche della funzionalità di [formattazione composita delle stringhe](../../standard/base-types/composite-formatting.md) sono disponibili per l'uso anche con le stringhe interpolate.</span><span class="sxs-lookup"><span data-stu-id="2fd99-115">That makes all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature available to you to use with interpolated strings as well.</span></span>

<span data-ttu-id="2fd99-116">Il compilatore può sostituire <xref:System.String.Format%2A?displayProperty=nameWithType> con <xref:System.String.Concat%2A?displayProperty=nameWithType> se il comportamento analizzato è equivalente alla concatenazione.</span><span class="sxs-lookup"><span data-stu-id="2fd99-116">The compiler may substitute a <xref:System.String.Format%2A?displayProperty=nameWithType> for <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a><span data-ttu-id="2fd99-117">Come specificare una stringa di formato per un'espressione interpolata</span><span class="sxs-lookup"><span data-stu-id="2fd99-117">How to specify a format string for an interpolated expression</span></span>

<span data-ttu-id="2fd99-118">Per specificare una stringa di formato supportata dal tipo del risultato dell'espressione, far seguire all'espressione interpolata i due punti (":") e la stringa di formato da usare:</span><span class="sxs-lookup"><span data-stu-id="2fd99-118">You specify a format string that is supported by the type of the expression result by following the interpolated expression with a colon (":") and the format string:</span></span>

```
{<interpolatedExpression>:<formatString>}
```

<span data-ttu-id="2fd99-119">L'esempio seguente illustra come specificare stringhe di formato standard e personalizzate per espressioni che producono risultati di tipo data e ora o numerici:</span><span class="sxs-lookup"><span data-stu-id="2fd99-119">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="2fd99-120">Per altre informazioni, vedere la sezione [Componente della stringa di formato](../../standard/base-types/composite-formatting.md#format-string-component) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-120">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="2fd99-121">Questa sezione mette a disposizione i collegamenti agli argomenti che descrivono le stringhe di formato standard e personalizzate supportate dai tipi di base .NET.</span><span class="sxs-lookup"><span data-stu-id="2fd99-121">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a><span data-ttu-id="2fd99-122">Come controllare la larghezza del campo e l'allineamento delle espressioni interpolate formattate</span><span class="sxs-lookup"><span data-stu-id="2fd99-122">How to control the field width and alignment of the formatted interpolated expression</span></span>

<span data-ttu-id="2fd99-123">È possibile specificare la larghezza minima del campo e l'allineamento del risultato dell'espressione formattata facendo seguire l'espressione interpolata da una virgola (",") e dall'espressione costante:</span><span class="sxs-lookup"><span data-stu-id="2fd99-123">You specify the minimum field width and the alignment of the formatted expression result by following the interpolated expression with a comma (",") and the constant expression:</span></span>

```
{<interpolatedExpression>,<alignment>}
```

<span data-ttu-id="2fd99-124">Se il valore *alignment* è positivo, il risultato dell'espressione formattata è allineato a destra, mentre se è negativo è allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="2fd99-124">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="2fd99-125">Se è necessario specificare sia l'allineamento che una stringa di formato, iniziare con l'allineamento:</span><span class="sxs-lookup"><span data-stu-id="2fd99-125">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="2fd99-126">L'esempio seguente illustra come specificare l'allineamento e usa caratteri barra verticale ("|") per delimitare i campi di testo:</span><span class="sxs-lookup"><span data-stu-id="2fd99-126">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="2fd99-127">Come illustrato nell'esempio di output, se la lunghezza del risultato dell'espressione formattata supera la larghezza del campo specificata, il valore *alignment* viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2fd99-127">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="2fd99-128">Per altre informazioni, vedere la sezione [Componente di allineamento](../../standard/base-types/composite-formatting.md#alignment-component) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-128">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="2fd99-129">Come usare sequenze di escape in una stringa interpolata</span><span class="sxs-lookup"><span data-stu-id="2fd99-129">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="2fd99-130">Le stringhe interpolate supportano tutte le sequenze di escape che è possibile usare all'interno di valori letterali stringa normali.</span><span class="sxs-lookup"><span data-stu-id="2fd99-130">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="2fd99-131">Per altre informazioni, vedere [Sequenze di escape delle stringhe](../programming-guide/strings/index.md#string-escape-sequences).</span><span class="sxs-lookup"><span data-stu-id="2fd99-131">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="2fd99-132">Per interpretare le sequenze di escape letteralmente, usare un valore letterale stringa [verbatim](../language-reference/tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-132">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="2fd99-133">Una stringa interpolata verbatim inizia con il carattere `$` seguito dal carattere `@`.</span><span class="sxs-lookup"><span data-stu-id="2fd99-133">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span>

<span data-ttu-id="2fd99-134">Per includere una parentesi graffa, "{" o "}", in una stringa di risultato, usare due parentesi graffe, "{{" o "}}".</span><span class="sxs-lookup"><span data-stu-id="2fd99-134">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="2fd99-135">Per altre informazioni, vedere la sezione [Sequenze di escape delle parentesi graffe](../../standard/base-types/composite-formatting.md#escaping-braces) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-135">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="2fd99-136">L'esempio seguente illustra come includere parentesi graffe in una stringa di risultato e costruire una stringa interpolata verbatim:</span><span class="sxs-lookup"><span data-stu-id="2fd99-136">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a><span data-ttu-id="2fd99-137">Come usare un operatore condizionale ternario `?:` in un'espressione interpolata</span><span class="sxs-lookup"><span data-stu-id="2fd99-137">How to use a ternary conditional operator `?:` in an interpolated expression</span></span>

<span data-ttu-id="2fd99-138">Dato che i due punti (":") hanno un significato speciale in un elemento con un'espressione interpolata, per usare un [operatore condizionale](../language-reference/operators/conditional-operator.md) in un'espressione, racchiudere l'espressione tra parentesi, come illustrato dall'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2fd99-138">As the colon (":") has special meaning in an item with an interpolated expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="2fd99-139">Come creare una stringa di risultato specifica delle impostazioni cultura con interpolazione</span><span class="sxs-lookup"><span data-stu-id="2fd99-139">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="2fd99-140">Per impostazione predefinita, una stringa interpolata usa le impostazioni cultura correnti definite dalla proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> per tutte le operazioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="2fd99-140">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="2fd99-141">Usare la conversione implicita di una stringa interpolata in un'istanza di <xref:System.FormattableString?displayProperty=nameWithType> e chiamare il relativo metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> per creare una stringa di risultato specifica delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="2fd99-141">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="2fd99-142">L'esempio seguente illustra come eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="2fd99-142">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="2fd99-143">Come illustrato nell'esempio, è possibile usare un'istanza di <xref:System.FormattableString> per generare più stringhe di risultato per diverse impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="2fd99-143">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="2fd99-144">Come creare una stringa di risultato usando le impostazioni cultura inglese non dipendenti da paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="2fd99-144">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="2fd99-145">Insieme al metodo <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> è possibile usare il metodo statico <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> per risolvere una stringa interpolata in una stringa di risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>.</span><span class="sxs-lookup"><span data-stu-id="2fd99-145">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="2fd99-146">L'esempio seguente illustra come eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="2fd99-146">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="2fd99-147">Conclusione</span><span class="sxs-lookup"><span data-stu-id="2fd99-147">Conclusion</span></span>

<span data-ttu-id="2fd99-148">Questa esercitazione descrive scenari comuni di utilizzo dell'interpolazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="2fd99-148">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="2fd99-149">Per altre informazioni sull'interpolazione di stringhe, vedere l'argomento [Interpolazione di stringhe](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-149">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="2fd99-150">Per altre informazioni sulla formattazione dei tipi in .NET, vedere gli argomenti [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md) e [Formattazione composita](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2fd99-150">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fd99-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fd99-151">See Also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>  
- <xref:System.FormattableString?displayProperty=nameWithType>  
- <xref:System.IFormattable?displayProperty=nameWithType>  
- [<span data-ttu-id="2fd99-152">Stringhe</span><span class="sxs-lookup"><span data-stu-id="2fd99-152">Strings</span></span>](../programming-guide/strings/index.md)  
