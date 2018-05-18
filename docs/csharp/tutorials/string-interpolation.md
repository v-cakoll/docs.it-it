---
title: Interpolazione di stringhe in C#
description: Informazioni su come includere risultati di espressione formattati in una stringa di risultato in C# con interpolazione.
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: 447e87cd4aae49896f0efbb8ece6097181079266
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2018
---
# <a name="string-interpolation-in-c"></a>Interpolazione di stringhe in C# #

Questa esercitazione illustra come usare l'[interpolazione di stringhe](../language-reference/tokens/interpolated.md) per formattare e includere risultati di espressione in una stringa di risultato. Gli esempi presuppongono una buona familiarità con i concetti di base del linguaggio C# e con la formattazione dei tipi in .NET. Se non si ha familiarità con l'interpolazione di stringhe o con la formattazione dei tipi in .NET, vedere prima la [guida introduttiva interattiva all'interpolazione di stringhe](../quick-starts/interpolated-strings.yml). Per altre informazioni sulla formattazione dei tipi in .NET, vedere l'argomento [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a>Introduzione

La funzionalità di [interpolazione di stringhe](../language-reference/tokens/interpolated.md), basata sulla funzionalità di [formattazione composita](../../standard/base-types/composite-formatting.md), offre una sintassi più leggibile e pratica per includere risultati di espressione formattati in una stringa di risultato.

Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`. È possibile incorporare in una stringa interpolata qualsiasi espressione C# valida che restituisca un valore. Nell'esempio seguente, non appena un'espressione viene valutata, il suo risultato viene convertito in una stringa e incluso in una stringa di risultato:

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

Come illustrato nell'esempio, per includere un'espressione in una stringa interpolata è necessario racchiuderla tra parentesi graffe:

```
{<interpolatedExpression>}
```

In fase di compilazione, una stringa interpolata viene in genere trasformata in una chiamata al metodo <xref:System.String.Format%2A?displayProperty=nameWithType>. In questo modo tutte le caratteristiche della funzionalità di [formattazione composita delle stringhe](../../standard/base-types/composite-formatting.md) sono disponibili per l'uso anche con le stringhe interpolate.

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a>Come specificare una stringa di formato per un'espressione interpolata

Per specificare una stringa di formato supportata dal tipo del risultato dell'espressione, far seguire all'espressione interpolata i due punti (":") e la stringa di formato da usare:

```
{<interpolatedExpression>:<formatString>}
```

L'esempio seguente illustra come specificare stringhe di formato standard e personalizzate per espressioni che producono risultati di tipo data e ora o numerici:

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

Per altre informazioni, vedere la sezione [Componente della stringa di formato](../../standard/base-types/composite-formatting.md#format-string-component) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md). Questa sezione mette a disposizione i collegamenti agli argomenti che descrivono le stringhe di formato standard e personalizzate supportate dai tipi di base .NET.

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a>Come controllare la larghezza del campo e l'allineamento delle espressioni interpolate formattate

È possibile specificare la larghezza minima del campo e l'allineamento del risultato dell'espressione formattata facendo seguire l'espressione interpolata da una virgola (",") e dall'espressione costante:

```
{<interpolatedExpression>,<alignment>}
```

Se il valore *alignment* è positivo, il risultato dell'espressione formattata è allineato a destra, mentre se è negativo è allineato a sinistra.

Se è necessario specificare sia l'allineamento che una stringa di formato, iniziare con l'allineamento:

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

L'esempio seguente illustra come specificare l'allineamento e usa caratteri barra verticale ("|") per delimitare i campi di testo:

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

Come illustrato nell'esempio di output, se la lunghezza del risultato dell'espressione formattata supera la larghezza del campo specificata, il valore *alignment* viene ignorato.

Per altre informazioni, vedere la sezione [Componente di allineamento](../../standard/base-types/composite-formatting.md#alignment-component) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md).

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a>Come usare sequenze di escape in una stringa interpolata

Le stringhe interpolate supportano tutte le sequenze di escape che è possibile usare all'interno di valori letterali stringa normali. Per altre informazioni, vedere [Sequenze di escape delle stringhe](../programming-guide/strings/index.md#string-escape-sequences).

Per interpretare le sequenze di escape letteralmente, usare un valore letterale stringa [verbatim](../language-reference/tokens/verbatim.md). Una stringa interpolata verbatim inizia con il carattere `$` seguito dal carattere `@`.

Per includere una parentesi graffa, "{" o "}", in una stringa di risultato, usare due parentesi graffe, "{{" o "}}". Per altre informazioni, vedere la sezione [Sequenze di escape delle parentesi graffe](../../standard/base-types/composite-formatting.md#escaping-braces) dell'argomento [Formattazione composita](../../standard/base-types/composite-formatting.md).

L'esempio seguente illustra come includere parentesi graffe in una stringa di risultato e costruire una stringa interpolata verbatim:

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a>Come usare un operatore condizionale ternario `?:` in un'espressione interpolata

Dato che i due punti (":") hanno un significato speciale in un elemento con un'espressione interpolata, per usare un [operatore condizionale](../language-reference/operators/conditional-operator.md) in un'espressione, racchiudere l'espressione tra parentesi, come illustrato dall'esempio seguente:

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a>Come creare una stringa di risultato specifica delle impostazioni cultura con interpolazione

Per impostazione predefinita, una stringa interpolata usa le impostazioni cultura correnti definite dalla proprietà <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> per tutte le operazioni di formattazione. Usare la conversione implicita di una stringa interpolata in un'istanza di <xref:System.FormattableString?displayProperty=nameWithType> e chiamare il relativo metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> per creare una stringa di risultato specifica delle impostazioni cultura. L'esempio seguente illustra come eseguire questa operazione:

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

Come illustrato nell'esempio, è possibile usare un'istanza di <xref:System.FormattableString> per generare più stringhe di risultato per diverse impostazioni cultura.

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a>Come creare una stringa di risultato usando le impostazioni cultura inglese non dipendenti da paese/area geografica

Insieme al metodo <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> è possibile usare il metodo statico <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> per risolvere una stringa interpolata in una stringa di risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>. L'esempio seguente illustra come eseguire questa operazione:

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a>Conclusione

Questa esercitazione descrive scenari comuni di utilizzo dell'interpolazione di stringhe. Per altre informazioni sull'interpolazione di stringhe, vedere l'argomento [Interpolazione di stringhe](../language-reference/tokens/interpolated.md). Per altre informazioni sulla formattazione dei tipi in .NET, vedere gli argomenti [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md) e [Formattazione composita](../../standard/base-types/composite-formatting.md).

## <a name="see-also"></a>Vedere anche

<xref:System.String.Format%2A?displayProperty=nameWithType>  
<xref:System.FormattableString?displayProperty=nameWithType>  
<xref:System.IFormattable?displayProperty=nameWithType>  
[Stringhe](../programming-guide/strings/index.md)  
