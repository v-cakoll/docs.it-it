---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620334"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Enumerable.Empty&lt;TResult&gt; restituisce sempre un'istanza memorizzata nella cache

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> restituisce sempre un <xref:System.Collections.Generic.IEnumerable%601> di un'istanza interna memorizzata nella cache. Nelle versioni precedenti, <xref:System.Linq.Enumerable.Empty%60%601> memorizzava nella cache un <xref:System.Collections.Generic.IEnumerable%601> vuoto al momento della chiamata dell'API e questo significa che in alcune condizioni in cui <xref:System.Linq.Enumerable.Empty%60%601> viene chiamato velocemente e in simultanea, possono essere restituite istanze diverse del tipo per chiamate diverse all'API.

#### <a name="suggestion"></a>Suggerimento

Dato che il comportamento precedente è non deterministico, è improbabile che esista codice dipendente. Tuttavia, nel caso improbabile che i tipi enumerabili vuoti vengano usati per confronti prevedendo che talvolta possano essere diversi, è consigliabile creare matrici vuote esplicite (<code>new T[0]</code>) invece di usare <xref:System.Linq.Enumerable.Empty%60%601>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
