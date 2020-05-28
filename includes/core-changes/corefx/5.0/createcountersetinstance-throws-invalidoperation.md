---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144481"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>Il contatore. CreateCounterSetInstance genera ora InvalidOperationException se l'istanza esiste già

A partire da .NET 5,0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> genera un'eccezione <xref:System.InvalidOperationException> anziché un'eccezione <xref:System.ArgumentException> se l'insieme di contatori esiste già.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework e .NET Core 1,0 a 3,1 è possibile creare un'istanza dell'insieme di contatori chiamando <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> . Tuttavia, se l'insieme di contatori esiste già, il metodo genera un' <xref:System.ArgumentException> eccezione.

In .NET 5,0 e versioni successive, quando si chiama <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> e l'insieme di contatori esiste, <xref:System.InvalidOperationException> viene generata un'eccezione.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Preview 5

#### <a name="recommended-action"></a>Azione consigliata

Se si rilevano <xref:System.ArgumentException> eccezioni nell'app durante la chiamata a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> , è consigliabile rilevare anche le <xref:System.InvalidOperationException> eccezioni.

> [!NOTE]
> <xref:System.ArgumentException>Non è consigliabile intercettare le eccezioni.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
