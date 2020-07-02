---
ms.openlocfilehash: 483902ff2ec54d58bfb00dd8ee7fd78868f70ab4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620361"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter potrebbe non trovare il tipo dal contesto LoadFrom

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, diverse modifiche di <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> potrebbero causare differenze nella deserializzazione quando si usa <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> per deserializzare tipi caricati nel contesto LoadFrom. Queste modifiche sono dovute ai nuovi modi con cui <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> ora carica un tipo che determina un comportamento diverso quando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> tenta di eseguire la deserializzazione per quel tipo in un secondo momento. Il binder di serializzazione predefinito non esegue automaticamente la ricerca del contesto LoadFrom, anche se in alcuni casi potrebbe aver funzionato in base al comportamento precedente di XmlSerializer. A causa delle modifiche, quando un tipo viene caricato da un assembly caricato in un contesto diverso potrebbe essere generato <xref:System.IO.FileNotFoundException?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Se si verifica questa eccezione, la proprietà <code>Binder</code> di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> può essere impostata su un binder personalizzato che troverà il tipo corretto.<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>Binder personalizzato:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
