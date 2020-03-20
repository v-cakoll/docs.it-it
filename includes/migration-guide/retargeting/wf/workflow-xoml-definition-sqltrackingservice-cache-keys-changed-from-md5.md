---
ms.openlocfilehash: 4254cceab0048341b32fe5babf53b5ea3e5a52d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72846995"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>La definizione XOML del flusso di lavoro e le chiavi della cache di SqlTrackingService sono state modificate da MD5 a SHA256

|   |   |
|---|---|
|Dettagli|Nel runtime di Workflow viene archiviata una cache di definizioni del flusso di lavoro definite in XOML. Anche in SqlTrackingService viene archiviata una cache con chiavi specificate da stringhe. Queste cache vengono codificate con chiavi in base ai valori che includono un valore hash di checksum. In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.8, l'algoritmo utilizzato è SHA256. Non dovrebbe esserci un problema di compatibilità con questa modifica perché i valori vengono ricalcolati ogni volta che viene avviato il Runtime del flusso di lavoro e SqlTrackingService.There shouldt be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started. Tuttavia, sono state specificate modalità non standard per consentire ai clienti di ripristinare l'uso dell'algoritmo hash legacy, in caso di necessità.|
|Suggerimento|Se questa modifica crea problemi durante l'esecuzione dei flussi di lavoro, provare a impostare una o entrambe le opzioni <code>AppContext</code>:<ul><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; su true.</li><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; su true.</li></ul>Nel codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>O nel file di configurazione (deve essere il file di configurazione per l'applicazione con cui si sta creando l'oggetto <xref:System.Workflow.Runtime.WorkflowRuntime>):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.8|
|Type|Ridestinazione|
