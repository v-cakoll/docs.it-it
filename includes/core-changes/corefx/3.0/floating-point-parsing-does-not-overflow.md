---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568204"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a>Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano un'eccezione OverflowException

I metodi di analisi a virgola <xref:System.OverflowException> mobile `false` non generano più un o restituito quando <xref:System.Single> <xref:System.Double> analizzano una stringa il cui valore numerico non è compreso nell'intervallo del tipo o a virgola mobile.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e <xref:System.Double.Parse%2A?displayProperty=nameWithType> <xref:System.Single.Parse%2A?displayProperty=nameWithType> versioni precedenti, i metodi e generano un <xref:System.OverflowException> for valori che non rientrano nell'intervallo del rispettivo tipo. I <xref:System.Double.TryParse%2A?displayProperty=nameWithType> <xref:System.Single.TryParse%2A?displayProperty=nameWithType> metodi `false` e restituiscono per le rappresentazioni di stringa di valori numerici non compresi nell'intervallo.

A partire da .NET Core <xref:System.Double.Parse%2A?displayProperty=nameWithType> <xref:System.Double.TryParse%2A?displayProperty=nameWithType>3.0, i metodi , , <xref:System.Single.Parse%2A?displayProperty=nameWithType>e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> non hanno più esito negativo durante l'analisi di stringhe numeriche non di intervallo. Al contrario, <xref:System.Double> i <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> metodi di <xref:System.Double.MaxValue?displayProperty=nameWithType>analisi restituiscono <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> valori che superano e restituiscono valori minori di <xref:System.Double.MinValue?displayProperty=nameWithType>. Analogamente, <xref:System.Single> i metodi <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> di analisi <xref:System.Single.MaxValue?displayProperty=nameWithType>restituiscono valori <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> che superano <xref:System.Single.MinValue?displayProperty=nameWithType>e restituiscono valori minori di .

Questa modifica è stata apportata per migliorare la conformità IEEE 754:2008.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica può influire sul codice in due modi:This change can affect your code in either of two ways:

- Il codice dipende dal <xref:System.OverflowException> gestore per l'esecuzione quando si verifica un overflow. In questo caso, è `catch` necessario rimuovere l'istruzione `If` e inserire <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> il `true`codice necessario in un'istruzione che verifica se o è .

- Il codice presuppone che i valori `Infinity`a virgola mobile non siano . In questo caso, è necessario aggiungere il codice necessario `PositiveInfinity` `NegativeInfinity`per verificare la presenza di valori a virgola mobile di e .

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
