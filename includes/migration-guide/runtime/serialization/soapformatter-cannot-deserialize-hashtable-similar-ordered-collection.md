---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620381"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter non è in grado di deserializzare Hashtable e simili oggetti di raccolta ordinati

#### <a name="details"></a>Dettagli

<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> non garantisce che gli oggetti serializzati nell'ambito di una versione di .NET Framework possano essere deserializzati correttamente in una versione diversa. In particolare, in alcune raccolte ordinate, come <xref:System.Collections.Hashtable?displayProperty=fullName>, sono stati aggiunti membri tra le versioni 4.0 e 4.5 e ne consegue che questi oggetti non possono essere deserializzati con .NET Framework 4.0 se vengono serializzati con .NET Framework 4.5. Si noti che, se i dati serializzati vengono sia serializzati che deserializzati con la stessa versione di .NET Framework, non si verificherà alcun problema.

#### <a name="suggestion"></a>Suggerimento

La serializzazione di <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> deve essere sostituita con la serializzazione di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> o di <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> per essere adattabile alle modifiche di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
