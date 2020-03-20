---
ms.openlocfilehash: f4a5911787fa5f72be1dcd15c67b3f132c3f1110
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804447"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap converte correttamente le icone con frame PNG in oggetti Bitmap

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.6, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> converte correttamente le icone con frame PNG in oggetti Bitmap.<p/>Nelle app destinate a .NET Framework 4.5.2 e alle versioni precedenti, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.ArgumentOutOfRangeException> se l'oggetto Icon presenta frame PNG.<p/>Questa modifica influisce sulle app che vengono ricompilate per essere destinate a .NET Framework 4.6 e che implementano una gestione speciale per l'eccezione <xref:System.ArgumentOutOfRangeException> generata quando un oggetto Icon presenta frame PNG. Quando è in esecuzione su .NET Framework 4.6, la conversione viene completata correttamente, non viene più generata un'eccezione <xref:System.ArgumentOutOfRangeException> e quindi non viene più richiamato il gestore di eccezioni.|
|Suggerimento|Se questo comportamento è indesiderato, è possibile conservare il comportamento precedente aggiungendo l'elemento seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>Se il file app.config contiene già l'elemento <code>AppContextSwitchOverrides</code>, il nuovo valore deve essere unito con l'attributo value come nell'esempio seguente:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.6|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|
