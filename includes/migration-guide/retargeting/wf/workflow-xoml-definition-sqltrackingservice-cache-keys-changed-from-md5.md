---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616263"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>La definizione XOML del flusso di lavoro e le chiavi della cache di SqlTrackingService sono state modificate da MD5 a SHA256

#### <a name="details"></a>Dettagli

Nel runtime di Workflow viene archiviata una cache di definizioni del flusso di lavoro definite in XOML. Anche in SqlTrackingService viene archiviata una cache con chiavi specificate da stringhe. Queste cache vengono codificate con chiavi in base ai valori che includono un valore hash di checksum. In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4,8, l'algoritmo usato è SHA256. Non dovrebbe sussistere un problema di compatibilità con questa modifica perché i valori vengono ricalcolati ogni volta che il runtime del flusso di lavoro e SqlTrackingService viene avviato. Tuttavia, sono state specificate modalità non standard per consentire ai clienti di ripristinare l'uso dell'algoritmo hash legacy, in caso di necessità.

#### <a name="suggestion"></a>Suggerimento

Se questa modifica crea problemi durante l'esecuzione dei flussi di lavoro, provare a impostare una o entrambe le opzioni `AppContext`:

- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; su true.
- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; su true.
Nel codice:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

O nel file di configurazione (deve essere il file di configurazione per l'applicazione con cui si sta creando l'oggetto <xref:System.Workflow.Runtime.WorkflowRuntime>):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.8         |
| Type    | Ridestinazione |
