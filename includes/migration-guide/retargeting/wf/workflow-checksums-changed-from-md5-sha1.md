---
ms.openlocfilehash: 0b42e320ba439a4cfc196471fc6dd4b3c15cd9d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859066"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Checksum del flusso di lavoro modificati da MD5 a SHA1

|   |   |
|---|---|
|Dettagli|Per supportare il debug con Visual Studio, il runtime del flusso di lavoro genera un checksum per un'istanza del flusso di lavoro usando un algoritmo hash. In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS. A partire da .NET Framework 4.7 l'algoritmo è SHA1. Se il codice ha mantenuto i checksum, questi non saranno compatibili.|
|Suggerimento|Se il codice non riesce a caricare le istanze del flusso di lavoro a causa di un errore di checksum, provare a impostare lo switch <code>AppContext</code>&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; su true. Nel codice:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot;, true);&#13;&#10;</code></pre>O nella configurazione:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseMD5ForWFDebugger=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7|
|Type|Ridestinazione|
