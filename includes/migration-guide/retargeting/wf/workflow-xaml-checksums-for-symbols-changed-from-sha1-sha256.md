---
ms.openlocfilehash: 9c54572b8dcedaa103db8503cfc1155b4698c3ed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803504"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Checksum di Workflow XAML per i simboli modificati da SHA1 in SHA256

|   |   |
|---|---|
|Dettagli|Per supportare il debug con Visual Studio, il runtime di Workflow genera un checksum per un file Workflow XAML usando un algoritmo hash. In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.7, l'algoritmo predefinito è stato modificato in SHA1. A partire da .NET Framework 4.8, l'algoritmo predefinito è stato modificato in SHA256.|
|Suggerimento|Se il codice non riesce a caricare le istanze del flusso di lavoro o a trovare i simboli appropriati a causa di un errore di checksum, provare a impostare l'opzione <code>AppContext</code> &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; su true. Nel codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>O nella configurazione:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.8|
|Tipo|Ridestinazione|

