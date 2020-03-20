---
ms.openlocfilehash: 506218195417548880a9d8d10508a570a7769682
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859278"
---
### <a name="long-path-support"></a>Supporto del percorso lungo

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.6.2, i percorsi lunghi (fino a 32 KB di caratteri) sono supportati e il limite di 260 caratteri (o <code>MAX_PATH</code>) per la lunghezza dei percorsi è stato rimosso. Per le app ricompilate con destinazione .NET Framework 4.6.2, i percorsi che in precedenza generavano una <xref:System.IO.PathTooLongException?displayProperty=name> a causa di un percorso più lungo di 260 caratteri genereranno ora una <xref:System.IO.PathTooLongException?displayProperty=name> solo nelle condizioni seguenti:<ul><li>La lunghezza del percorso è maggiore di <xref:System.Int16.MaxValue> (32.767) caratteri.</li><li>Il sistema operativo restituisce <code>COR_E_PATHTOOLONG</code> o equivalente.</li></ul>Per le app destinate a .NET Framework 4.6.1 e versioni precedenti, il runtime genera automaticamente un'eccezione <xref:System.IO.PathTooLongException?displayProperty=name> ogni volta che un percorso supera i 260 caratteri.|
|Suggerimento|Per le app destinate a .NET Framework 4.6.2, è possibile rifiutare esplicitamente il supporto di percorsi lunghi se non opportuno aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.6.2 o versioni successive è possibile acconsentire esplicitamente al supporto dei percorsi lunghi aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Ridestinazione|
