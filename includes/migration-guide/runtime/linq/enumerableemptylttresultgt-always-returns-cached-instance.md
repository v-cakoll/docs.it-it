---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235500"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a>Enumerable.Empty\<TResult> restituisce sempre un'istanza memorizzata nella cache

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> restituisce sempre un <xref:System.Collections.Generic.IEnumerable%601> di un'istanza interna memorizzata nella cache. Nelle versioni precedenti, <xref:System.Linq.Enumerable.Empty%60%601> memorizzava nella cache un <xref:System.Collections.Generic.IEnumerable%601> vuoto al momento della chiamata dell'API e questo significa che in alcune condizioni in cui <xref:System.Linq.Enumerable.Empty%60%601> viene chiamato velocemente e in simultanea, possono essere restituite istanze diverse del tipo per chiamate diverse all'API.|
|Suggerimento|Dato che il comportamento precedente è non deterministico, è improbabile che esista codice dipendente. Tuttavia, nel caso improbabile che i tipi enumerabili vuoti vengano usati per confronti prevedendo che talvolta possano essere diversi, è consigliabile creare matrici vuote esplicite (<code>new T[0]</code>) invece di usare <xref:System.Linq.Enumerable.Empty%60%601>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
