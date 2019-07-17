---
ms.openlocfilehash: 19e0524f4d40517f3e305b2397e628e0478da8f9
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803537"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>Checksum del file XOML del flusso di lavoro modificati da MD5 a SHA256

|   |   |
|---|---|
|Dettagli|Per supportare il debug dei flussi di lavoro basati su XOML con Visual Studio, quando vengono compilati progetti di flusso di lavoro contenenti file XOML, viene inserito nel codice generato un checksum del contenuto del file XOML come valore <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>. In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.8, viene usato l'algoritmo SHA256. Per ragioni di compatibilità con WorkflowMarkupSourceAttribute.MD5Digest, vengono usati solo i primi 16 byte del checksum generato. Ciò potrebbe causare problemi durante il debug. Potrebbe essere necessario ricompilare il progetto.|
|Suggerimento|Se la ricompilazione del progetto non risolve il problema, provare a impostare l'opzione <code>AppContext</code> &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; su true. Nel codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>Oppure in un file di configurazione (che deve trovarsi in MSBuild.exe.config per il file MSBuild.exe in uso):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.8|
|Tipo|Ridestinazione|

