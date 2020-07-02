---
ms.openlocfilehash: 7d50962b518c15875a5f1a82f5b89ab87a1db02e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620234"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>Gli EventListener ETW non acquisiscono gli eventi dai provider con parole chiave esplicite (come il provider TPL)

#### <a name="details"></a>Dettagli

Gli EventListener ETW con una maschera di parole chiave vuota non acquisiscono correttamente gli eventi dai provider con parole chiave esplicite. In .NET Framework 4.5, il provider TPL ha iniziato a fornire parole chiave esplicite e ha causato questo problema. In .NET Framework 4.6, gli EventListener sono stati aggiornati e non presentano più questo problema.

#### <a name="suggestion"></a>Suggerimento

Per risolvere questo problema, sostituire le chiamate a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> con chiamate all'overload EnableEvents che specifica in modo esplicito la maschera &quot;qualsiasi parola chiave&quot; da usare: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
