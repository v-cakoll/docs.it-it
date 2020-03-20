---
ms.openlocfilehash: 1ef31202d7c072ca27c21fc22db102aafa6b8de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858608"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>Gli EventListener ETW non acquisiscono gli eventi dai provider con parole chiave esplicite (come il provider TPL)

|   |   |
|---|---|
|Dettagli|Gli EventListener ETW con una maschera di parole chiave vuota non acquisiscono correttamente gli eventi dai provider con parole chiave esplicite. In .NET Framework 4.5, il provider TPL ha iniziato a fornire parole chiave esplicite e ha causato questo problema. In .NET Framework 4.6, gli EventListener sono stati aggiornati e non presentano più questo problema.|
|Suggerimento|Per risolvere questo problema, sostituire le chiamate a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> con chiamate all'overload EnableEvents che specifica in modo esplicito la maschera &quot;qualsiasi parola chiave&quot; da usare: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Scope|Microsoft Edge|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
