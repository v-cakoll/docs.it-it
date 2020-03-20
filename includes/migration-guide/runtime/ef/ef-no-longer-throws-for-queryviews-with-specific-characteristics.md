---
ms.openlocfilehash: 705e1a22b8a5791c1103dd374a8bab19356cadfb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803196"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>Entity Framework non genera più eccezioni per QueryView con caratteristiche specifiche

|   |   |
|---|---|
|Dettagli|Entity Framework non genera più un'eccezione <xref:System.StackOverflowException?displayProperty=name> quando un'app esegue una query che coinvolge un elemento QueryView con una proprietà di navigazione 0..1 che tenta di includere le entità correlate nella query. Ad esempio, chiamando <code>.Include(e =&gt; e.RelatedNavProp)</code>.|
|Suggerimento|Questa modifica riguarda solo il codice che usa elementi QueryView con relazioni 1-0..1 in caso di esecuzione di query che chiamano .Include. Migliora l'affidabilità e dovrebbe essere trasparente a quasi tutte le app. Se tuttavia questa modifica causa un comportamento imprevisto, è possibile disabilitarla aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.5.2|
|Type|Runtime|
