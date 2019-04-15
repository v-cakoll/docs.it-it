---
ms.openlocfilehash: 0642b184d85306a453d429f247dad95a259cb012
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236510"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>La serializzazione dei caratteri di controllo con DataContractJsonSerializer è ora compatibile con ECMAScript V6 e V8

|   |   |
|---|---|
|Dettagli|In .NET framework 4.6.2 e versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> non serializza alcuni caratteri di controllo speciali, ad esempio \b, \f e \t, in modo compatibile con gli standard ECMAScript V6 e V8. A partire da .NET Framework 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.|
|Suggerimento|Questa funzionalità è abilitata per impostazione predefinita per le app destinate a .NET Framework 4.7. Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li></ul>|
