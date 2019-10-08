---
ms.openlocfilehash: 192873aa5069aa4f96a18716afb066c80b223e29
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002461"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a>Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException

I metodi di analisi a virgola mobile non generano più un'<xref:System.OverflowException> o restituiscono `false` quando analizzano una stringa il cui valore numerico non è compreso nell'intervallo del tipo a virgola mobile <xref:System.Single> o <xref:System.Double>.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti i metodi <xref:System.Double.Parse%2A?displayProperty=nameWithType> e <xref:System.Single.Parse%2A?displayProperty=nameWithType> generano un <xref:System.OverflowException> per i valori che non rientrano nell'intervallo del rispettivo tipo. I metodi <xref:System.Double.TryParse%2A?displayProperty=nameWithType> e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> restituiscono `false` per le rappresentazioni di stringa di valori numerici fuori intervallo.

A partire da .NET Core 3,0, i metodi <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> non hanno più esito negativo durante l'analisi di stringhe numeriche non comprese nell'intervallo. Al contrario, i metodi di analisi <xref:System.Double> restituiscono <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Double.MaxValue?displayProperty=nameWithType> e restituiscono <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> per i valori minori di <xref:System.Double.MinValue?displayProperty=nameWithType>. Analogamente, i metodi di analisi <xref:System.Single> restituiscono <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Single.MaxValue?displayProperty=nameWithType> e restituiscono <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> per i valori minori di <xref:System.Single.MinValue?displayProperty=nameWithType>.

Questa modifica è stata apportata per una conformità IEEE 754:2008 migliorata. 

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica può influire sul codice in uno dei due modi seguenti:

- Il codice dipende dal gestore per l'esecuzione <xref:System.OverflowException> quando si verifica un overflow. In tal caso, è necessario rimuovere l'istruzione `catch` e inserire il codice necessario in un'istruzione `If` che verifica se <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> o <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> è `true`.

- Il codice presuppone che i valori a virgola mobile non siano `Infinity`. In questo caso, è necessario aggiungere il codice necessario per verificare la presenza di valori a virgola mobile pari a `PositiveInfinity` e `NegativeInfinity`.

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
