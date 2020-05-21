---
ms.openlocfilehash: 935d9b2368ea4a0eeca7943dcbd584d24d2a6633
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721479"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a>Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException

I metodi di analisi a virgola mobile non generano più un'espressione <xref:System.OverflowException> o restituiscono `false` quando analizzano una stringa il cui valore numerico non è compreso nell'intervallo del <xref:System.Single> tipo a <xref:System.Double> virgola mobile o.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, i <xref:System.Double.Parse%2A?displayProperty=nameWithType> <xref:System.Single.Parse%2A?displayProperty=nameWithType> metodi e generano un <xref:System.OverflowException> per i valori che non rientrano nell'intervallo del rispettivo tipo. I <xref:System.Double.TryParse%2A?displayProperty=nameWithType> <xref:System.Single.TryParse%2A?displayProperty=nameWithType> metodi e restituiscono `false` per le rappresentazioni di stringa di valori numerici fuori intervallo.

A partire da .NET Core 3,0, <xref:System.Double.Parse%2A?displayProperty=nameWithType> i <xref:System.Double.TryParse%2A?displayProperty=nameWithType> metodi,, <xref:System.Single.Parse%2A?displayProperty=nameWithType> e non hanno <xref:System.Single.TryParse%2A?displayProperty=nameWithType> più esito negativo durante l'analisi di stringhe numeriche fuori intervallo. Al contrario, i <xref:System.Double> metodi di analisi restituiscono <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Double.MaxValue?displayProperty=nameWithType> e restituiscono <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> per valori minori di <xref:System.Double.MinValue?displayProperty=nameWithType> . Analogamente, i <xref:System.Single> metodi di analisi restituiscono <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Single.MaxValue?displayProperty=nameWithType> e restituiscono <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> per valori minori di <xref:System.Single.MinValue?displayProperty=nameWithType> .

Questa modifica è stata apportata per una conformità IEEE 754:2008 migliorata.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica può influire sul codice in uno dei due modi seguenti:

- Il codice dipende dal gestore dell'oggetto <xref:System.OverflowException> da eseguire quando si verifica un overflow. In tal caso, è necessario rimuovere l' `catch` istruzione e inserire qualsiasi codice necessario in un' `If` istruzione che verifica se <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> o <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> è `true` .

- Il codice presuppone che i valori a virgola mobile non lo siano `Infinity` . In questo caso, è necessario aggiungere il codice necessario per verificare la presenza di valori a virgola mobile `PositiveInfinity` e `NegativeInfinity` .

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
