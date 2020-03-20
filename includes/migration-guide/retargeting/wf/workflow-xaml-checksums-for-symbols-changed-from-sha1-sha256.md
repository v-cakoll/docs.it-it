---
ms.openlocfilehash: f814703e187726d3988787fac52e5049988fd4d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803504"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Checksum di Workflow XAML per i simboli modificati da SHA1 in SHA256

|   |   |
|---|---|
|Dettagli|Per supportare il debug con Visual Studio, il runtime di Workflow genera un checksum per un file Workflow XAML usando un algoritmo hash. In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.7, l'algoritmo predefinito è stato modificato in SHA1. A partire da .NET Framework 4.8, l'algoritmo predefinito è stato modificato in SHA256.|
|Suggerimento|Se il codice non riesce a caricare le istanze del flusso di lavoro o a trovare i simboli appropriati a causa di un errore di checksum, provare a impostare l'opzione <code>AppContext</code>&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; su true. Nel codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>O nella configurazione:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.8|
|Type|Ridestinazione|
