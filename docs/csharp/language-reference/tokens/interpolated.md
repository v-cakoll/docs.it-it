---
title: $ - interpolazione di stringhe - Riferimenti per C#
ms.custom: seodec18
description: L'interpolazione di stringhe offro una sintassi più leggibile e pratica per la formattazione dell'output di tipo stringa rispetto alla formattazione composita tradizionale.
ms.date: 03/26/2018
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
ms.openlocfilehash: 64728182fe0b758f8da668d19761305e2001f1a5
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920896"
---
# <a name="---string-interpolation-c-reference"></a>$ - interpolazione di stringhe (Riferimenti per C#)

Il carattere speciale `$` identifica una stringa letterale come *stringa interpolata*. Una stringa interpolata è un valore letterale stringa che può contenere *espressioni interpolate*. Quando una stringa interpolata viene risolta in una stringa di risultato, gli elementi con espressioni interpolate vengono sostituiti dalle rappresentazioni stringa dei risultati dell'espressione. Questa funzionalità è disponibile in C# 6 e versioni successive del linguaggio.

L'interpolazione di stringhe offre una sintassi più leggibile e pratica per creare stringhe formattate rispetto alla funzionalità di [formattazione composita delle stringhe](../../../standard/base-types/composite-formatting.md). L'esempio seguente usa entrambe le funzionalità per produrre lo stesso output:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Struttura di una stringa interpolata

Per identificare un valore letterale stringa come stringa interpolata, anteporre a questa il simbolo `$`. Tra `$` e il simbolo `"` all'inizio del valore letterale stringa non possono essere presenti spazi vuoti, altrimenti si genera un errore in fase di compilazione.

La struttura di un elemento con un'espressione interpolata è la seguente:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Gli elementi tra parentesi quadre sono facoltativi. La tabella seguente descrive i singoli elementi:

|Elemento|Description|
|-------------|-----------------|
|`interpolatedExpression`|Espressione che produce un risultato da formattare. La rappresentazione stringa del risultato `null` è <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Espressione costante il cui valore definisce il numero minimo di caratteri della rappresentazione stringa del risultato dell'espressione interpolata. Se è positivo, la rappresentazione stringa è allineata a destra; se è negativo la rappresentazione stringa è allineata a sinistra. Per altre informazioni, vedere [Componente di allineamento](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Stringa di formato supportata dal tipo di risultato dell'espressione. Per altre informazioni, vedere [Componente della stringa di formato](../../../standard/base-types/composite-formatting.md#format-string-component).|

L'esempio seguente usa i componenti di formattazione facoltativi descritti in precedenza:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Caratteri speciali

Per includere una parentesi graffa, "{" o "}", nel testo prodotto da una stringa interpolata, digitare due parentesi graffe, ovvero "{{" o "}}". Per altre informazioni, vedere [Sequenze di escape delle parentesi graffe](../../../standard/base-types/composite-formatting.md#escaping-braces).

Dato che i due punti (":") hanno un significato speciale in un elemento espressione interpolata, se si vuole usare un [operatore condizionale](../operators/conditional-operator.md) in un'espressione interpolata, racchiudere l'espressione tra parentesi.

L'esempio seguente illustra come includere una parentesi graffa in una stringa di risultato e come usare un operatore condizionale in un'espressione interpolata:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Una stringa interpolata verbatim inizia con il carattere `$` seguito dal carattere `@`. Per altre informazioni sulle stringhe verbatim, vedere gli argomenti relativi a [string](../keywords/string.md) e all'[identificatore verbatim](verbatim.md).

> [!NOTE]
> Il token `$` deve precedere il token `@` in una stringa interpolata verbatim.

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a>Conversioni implicite e indicazione dell'implementazione di `IFormatProvider`

Da una stringa interpolata vengono effettuate tre conversioni implicite:

1. Conversione di una stringa interpolata in un'istanza <xref:System.String> che rappresenta il risultato della risoluzione della stringa interpolata, dove gli elementi dell'espressione interpolata vengono sostituiti con le rappresentazioni stringa dei risultati, formattate correttamente. Questa conversione usa le impostazioni cultura correnti.

1. Conversione di una stringa interpolata in un'istanza di <xref:System.FormattableString> che rappresenta una stringa di formato composito e i risultati dell'espressione da formattare. Questa opzione consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.FormattableString>. A tale scopo, usare uno dei metodi seguenti:

      - Un overload <xref:System.FormattableString.ToString> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Un metodo <xref:System.FormattableString.Invariant%2A> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Un metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> che produce una stringa risultato per impostazioni cultura specifiche.

    È anche possibile usare il metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> per fornire un'implementazione definita dall'utente dell'interfaccia <xref:System.IFormatProvider> che supporta la formattazione personalizzata. Per altre informazioni, vedere [Formattazione personalizzata con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).

1. Conversione di una stringa interpolata in un'istanza di <xref:System.IFormattable> che consente anche di creare più stringhe risultato con contenuto associato a impostazioni cultura specifiche da una singola istanza di <xref:System.IFormattable>.

L'esempio seguente usa la conversione implicita a <xref:System.FormattableString> per creare stringhe di risultato con impostazioni cultura specifiche:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Risorse aggiuntive

Se non si ha familiarità con l'interpolazione di stringhe, vedere l'esercitazione interattiva [Interpolazione di stringhe in C#](../../tutorials/exploration/interpolated-strings.yml). In alternativa, è possibile provare l'esercitazione [interpolazione di stringhe in C#](../../tutorials/string-interpolation.md) in locale nel computer.

## <a name="see-also"></a>Vedere anche

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [Formattazione composita](../../../standard/base-types/composite-formatting.md)
- [Tabella di formattazione dei risultati numerici](../keywords/formatting-numeric-results-table.md)
- [Stringhe](../../programming-guide/strings/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Caratteri speciali di C#](index.md)
- [Riferimenti per C#](../index.md)
