---
ms.openlocfilehash: 47aa67096f8dcd250521d9c34dde97cb2eb368d7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803543"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>La definizione XOML del flusso di lavoro e le chiavi della cache di SqlTrackingService sono state modificate da MD5 a SHA256

|   |   |
|---|---|
|Dettagli|Nel runtime di Workflow viene archiviata una cache di definizioni del flusso di lavoro definite in XOML. Anche in SqlTrackingService viene archiviata una cache con chiavi specificate da stringhe. Queste cache vengono codificate con chiavi in base ai valori che includono un valore hash di checksum. In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.8, l'algoritmo usato è SHA256.Non dovrebbero esserci problemi di compatibilità con questa modifica poiché i valori vengono ricalcolati ogni volta che vengono avviati il runtime di Workflow e SqlTrackingService. Tuttavia, sono state specificate modalità non standard per consentire ai clienti di ripristinare l'uso dell'algoritmo hash legacy, in caso di necessità.|
|Suggerimento|Se questa modifica crea problemi durante l'esecuzione dei flussi di lavoro, provare a impostare una o entrambe le opzioni <code>AppContext</code>:<ul><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; su true.</li><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; su true.</li></ul>In codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>O nel file di configurazione (deve essere il file di configurazione per l'applicazione con cui si sta creando l'oggetto <xref:System.Workflow.Runtime.WorkflowRuntime>):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.8|
|Tipo|Ridestinazione|

