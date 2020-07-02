---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620251"
---
### <a name="listsort-algorithm-changed"></a>L'algoritmo List.Sort è stato modificato

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, l'algoritmo di ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=fullName> è stato modificato in ordinamento introspettivo anziché ordinamento rapido. L'ordinamento di <xref:System.Collections.Generic.List%601?displayProperty=fullName> non è mai stato stabile, ma questa modifica potrebbe determinare un ordinamento instabile in scenari diversi. Ciò significa semplicemente che l'ordinamento di elementi equivalenti potrebbe risultare diverso nelle successive chiamate dell'API.

#### <a name="suggestion"></a>Suggerimento

Poiché anche l'algoritmo di ordinamento precedente era instabile, anche se in modi leggermente diversi, nessun codice deve dipendere da elementi equivalenti sempre ordinati in un particolare ordine. In presenza di istanze di codice con questo tipo di dipendenza che funzionano correttamente con il vecchio comportamento, è necessario aggiornare il codice in modo che usi un operatore di confronto che ordinerà gli elementi in modo deterministico nell'ordine desiderato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Modalità trasparente|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
