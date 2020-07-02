---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620509"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>L'espansione XmlTextReader dell'entità DTD è limitata a 10.000.000 di caratteri

#### <a name="details"></a>Dettagli

L'espansione dell'entità DTD è ora limitata a 10.000.000 di caratteri. Il caricamento di file XML senza espansione o con espansione limitata dell'entità DTD non è interessato dall'operazione. I file con entità DTD che si espandono oltre 10.000.000 di caratteri non vengono caricati e generano un'eccezione.

#### <a name="suggestion"></a>Suggerimento

Se il limite di espansione dell'entità DTD di 10.000.000 è troppo basso, il valore può essere sostituito con la proprietà <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>. Un oggetto <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> con il valore <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> appropriato può essere passato a <code>XmlReader.Create</code> che accetta <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ad esempio <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
