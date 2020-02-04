---
title: $-String Interpolation C# -Reference
description: L'interpolazione di stringhe offro una sintassi più leggibile e pratica per la formattazione dell'output di tipo stringa rispetto alla formattazione composita tradizionale.
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: 97bc606569b83bd14cd3b32495deb8e529747e9c
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980119"
---
# <a name="---string-interpolation-c-reference"></a>interpolazione di $-C# String (riferimento)

Il carattere speciale `$` identifica una stringa letterale come *stringa interpolata*. Una stringa interpolata è un valore letterale stringa che può contenere *espressioni di interpolazione*. Quando una stringa interpolata viene risolta in una stringa di risultato, gli elementi con espressioni di interpolazione vengono sostituiti dalle rappresentazioni stringa dei risultati dell'espressione. Questa funzionalità è disponibile a partire C# da 6.

L'interpolazione di stringhe offre una sintassi più leggibile e pratica per creare stringhe formattate rispetto alla funzionalità di [formattazione composita delle stringhe](../../../standard/base-types/composite-formatting.md). L'esempio seguente usa entrambe le funzionalità per produrre lo stesso output:

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Struttura di una stringa interpolata

Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`. Tra `$` e il simbolo `"` all'inizio del valore letterale stringa non possono essere presenti spazi vuoti,

La struttura di un elemento con un'espressione di interpolazione è la seguente:

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

Gli elementi tra parentesi quadre sono facoltativi. La tabella seguente descrive i singoli elementi:

|Elemento|Descrizione|
|-------------|-----------------|
|`interpolationExpression`|Espressione che produce un risultato da formattare. La rappresentazione di stringa di `null` è <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Espressione costante il cui valore definisce il numero minimo di caratteri nella rappresentazione di stringa del risultato dell'espressione. Se è positivo, la rappresentazione stringa è allineata a destra; se è negativo la rappresentazione stringa è allineata a sinistra. Per altre informazioni, vedere [Componente di allineamento](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Stringa di formato supportata dal tipo di risultato dell'espressione. Per altre informazioni, vedere [Componente della stringa di formato](../../../standard/base-types/composite-formatting.md#format-string-component).|

L'esempio seguente usa i componenti di formattazione facoltativi descritti in precedenza:

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Caratteri speciali

Per includere una parentesi graffa, "{" o "}", nel testo prodotto da una stringa interpolata, digitare due parentesi graffe, ovvero "{{" o "}}". Per altre informazioni, vedere [Sequenze di escape delle parentesi graffe](../../../standard/base-types/composite-formatting.md#escaping-braces).

Dato che i due punti (":") hanno un significato speciale in un elemento espressione di interpolazione, se si vuole usare un [operatore condizionale](../operators/conditional-operator.md) in un'espressione di interpolazione, racchiudere l'espressione tra parentesi.

L'esempio seguente illustra come includere una parentesi graffa in una stringa di risultato e come usare un operatore condizionale in un'espressione di interpolazione:

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Una stringa Verbatim interpolata inizia con il carattere `$` seguito dal carattere di `@`. Per altre informazioni sulle stringhe verbatim, vedere gli argomenti relativi a [string](../builtin-types/reference-types.md) e all'[identificatore verbatim](verbatim.md).

> [!NOTE]
> A partire C# da 8,0, è possibile usare i token di `$` e di `@` in qualsiasi ordine: sia `$@"..."` che `@$"..."` sono stringhe verbatim interpolate valide. Nelle versioni C# precedenti, il token di `$` deve essere visualizzato prima del token di `@`.

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a>Conversioni implicite e come specificare l'implementazione di `IFormatProvider`

Da una stringa interpolata vengono effettuate tre conversioni implicite:

1. Conversione di una stringa interpolata in un'istanza <xref:System.String> che rappresenta il risultato della risoluzione della stringa interpolata, dove gli elementi dell'espressione di interpolazione vengono sostituiti con le rappresentazioni stringa dei risultati, formattate correttamente. Questa conversione usa il <xref:System.Globalization.CultureInfo.CurrentCulture> per formattare i risultati dell'espressione.

1. Conversione di una stringa interpolata in un'istanza di <xref:System.FormattableString> che rappresenta una stringa di formato composito e i risultati dell'espressione da formattare. Questa opzione consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.FormattableString>. A tale scopo, chiamare uno dei metodi seguenti:

      - Un overload <xref:System.FormattableString.ToString> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Un metodo <xref:System.FormattableString.Invariant%2A> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Un metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> che produce una stringa risultato per impostazioni cultura specifiche.

    È anche possibile usare il metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> per fornire un'implementazione definita dall'utente dell'interfaccia <xref:System.IFormatProvider> che supporta la formattazione personalizzata. Per altre informazioni, vedere la sezione [formattazione personalizzata con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) nell'articolo [formattazione di tipi in .NET](../../../standard/base-types/formatting-types.md) .

1. Conversione di una stringa interpolata in un'istanza di <xref:System.IFormattable> che consente anche di creare più stringhe risultato con contenuto associato a impostazioni cultura specifiche da una singola istanza di <xref:System.IFormattable>.

L'esempio seguente usa la conversione implicita a <xref:System.FormattableString> per creare stringhe di risultato con impostazioni cultura specifiche:

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Risorse aggiuntive

Se non si ha familiarità con l'interpolazione di stringhe, vedere l'esercitazione interattiva [Interpolazione di stringhe in C#](../../tutorials/exploration/interpolated-strings.yml). È anche possibile verificare un'altra esercitazione di [interpolazione di stringhe in C#](../../tutorials/string-interpolation.md) che illustra come usare le stringhe interpolate per produrre stringhe formattate.

## <a name="compilation-of-interpolated-strings"></a>Compilazione di stringhe interpolate

Se una stringa interpolata è di tipo `string`, viene in genere trasformata in una chiamata al metodo <xref:System.String.Format%2A?displayProperty=nameWithType>. Il compilatore può sostituire <xref:System.String.Format%2A?displayProperty=nameWithType> con <xref:System.String.Concat%2A?displayProperty=nameWithType> se il comportamento analizzato è equivalente alla concatenazione.

Se una stringa interpolata dispone del tipo <xref:System.IFormattable> o <xref:System.FormattableString>, il compilatore genera una chiamata al metodo <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Stringhe interpolate](~/_csharplang/spec/expressions.md#interpolated-strings) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Caratteri speciali di C#](index.md)
- [Stringhe](../../programming-guide/strings/index.md)
- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
- [Formattazione composita](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
