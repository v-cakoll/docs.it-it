---
ms.openlocfilehash: 6ed7438a7f6e7710fcce03c8260a1360143f8d93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235489"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter non è in grado di deserializzare Hashtable e simili oggetti di raccolta ordinati

|   |   |
|---|---|
|Dettagli|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> non garantisce che gli oggetti serializzati nell'ambito di una versione di .NET Framework possano essere deserializzati correttamente in una versione diversa. In particolare, in alcune raccolte ordinate, come <xref:System.Collections.Hashtable?displayProperty=name>, sono stati aggiunti membri tra le versioni 4.0 e 4.5 e ne consegue che questi oggetti non possono essere deserializzati con .NET Framework 4.0 se vengono serializzati con .NET Framework 4.5. Si noti che, se i dati serializzati vengono sia serializzati che deserializzati con la stessa versione di .NET Framework, non si verificherà alcun problema.|
|Suggerimento|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> La serializzazione di SoapFormatter deve essere sostituita con la serializzazione di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> o di <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> per essere adattabile alle modifiche di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
