---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804487"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>I nomi di eventi ETW non possono essere diversi solo per il suffisso "Start" o "Stop"

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 e 4.6.1 il runtime genera una <xref:System.ArgumentException> quando due nomi di eventi ETW (Event Tracing for Windows) sono diversi solo per il suffisso &quot;Start&quot; o &quot;Stop&quot;, ad esempio quando un evento è denominato <code>LogUser</code> e un altro <code>LogUserStart</code>. In questo caso, il runtime non può creare l'origine dell'evento, quindi non viene generata alcuna registrazione.|
|Suggerimento|Per evitare l'eccezione, assicurarsi che non siano presenti nomi di evento che differiscono solo per il suffisso &quot;Start&quot; oppure &quot;Stop&quot;. Questo requisito è stato rimosso a rimosso a partire da .NET Framework 4.6.2 e il runtime può risolvere l'ambiguità di nomi di evento che differiscono solo per il suffisso &quot;Start&quot; e &quot;Stop&quot;.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Ridestinazione|
