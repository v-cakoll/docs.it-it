---
ms.openlocfilehash: ed0dde302e30ae0cf3c7a8d0985f2314d91cab66
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760903"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream usa API native per la decompressione

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.2 l'implementazione della decompressione nella classe <code>T:System.IO.Compression.DeflateStream</code> è stata modificata e ora usa le API Windows native per impostazione predefinita. In genere questo comporta un miglioramento significativo delle prestazioni. Tutte le applicazioni .NET destinate a .NET Framework 4.7.2 o versioni successive usano l'implementazione nativa. Questa modifica potrebbe causare alcune variazioni di comportamento, tra cui le seguenti:<ul><li>I messaggi di eccezione potrebbero essere diversi. Tuttavia il tipo di eccezione generato rimane invariato.</li><li>È possibile che alcuni casi speciali, ad esempio il caso in cui la memoria non è sufficiente per completare un'operazione, vengano gestiti in modo diverso.</li><li>Esistono differenze note per l'analisi dell'intestazione gzip (Nota: è interessata solo <code>GZipStream</code> impostata per la decompressione):</li><li>Le eccezioni durante l'analisi delle intestazioni non valide possono essere attivate in momenti diversi.</li><li>L'implementazione nativa impone che i valori di alcuni flag riservati nell'intestazione gzip (ad esempio [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) vengano impostati in base alla specifica. Ciò può causare un'eccezione nei punti in cui i valori in precedenza non validi venivano ignorati.</li></ul>|
|Suggerimento|Se la decompressione con API native compromette il comportamento dell'app, è possibile rifiutare esplicitamente questa funzionalità aggiungendo l'opzione <code>Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression</code> alla sezione <code>runtime</code> del file app.config e impostandola su <code>true</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot; ?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType></li><li><xref:System.IO.Compression.GZipStream?displayProperty=nameWithType></li></ul>|

