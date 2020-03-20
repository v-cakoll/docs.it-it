---
ms.openlocfilehash: 2c532bf3778b940f68db859420dd12826e9da388
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77465947"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>La serializzazione dei caratteri di controllo con DataContractJsonSerializer è ora compatibile con ECMAScript V6 e V8

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> versioni precedenti, l'oggetto non veniva serializzato con alcuni caratteri di controllo speciali, ad esempio gli standard ECMAScript V6 e V8. A partire da .NET Framework 4.7.NET Framework 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.|
|Suggerimento|Questa funzionalità è abilitata per impostazione predefinita per le app destinate a .NET Framework 4.7. Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.7|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li></ul>|
