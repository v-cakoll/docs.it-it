---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620521"
---
### <a name="xslt-style-sheet-exception-message-changed"></a>Modificato il messaggio di eccezione del foglio di stile XSLT

#### <a name="details"></a>Dettagli

Nel .NET Framework 4,5, il testo del messaggio di errore quando un file XSLT è troppo complesso è &quot; il foglio di stile è troppo complesso. &quot; Nelle versioni precedenti il messaggio di errore era &quot; errore di compilazione XSLT. &quot; Il codice dell'applicazione che dipende dal testo del messaggio di errore non funzionerà più. Tuttavia, i tipi di eccezione rimangono gli stessi e pertanto questa modifica non dovrebbe avere un impatto reale.

#### <a name="suggestion"></a>Suggerimento

Aggiornare il codice dell'app che dipende dal messaggio di eccezione da questa condizione di errore in modo che preveda il nuovo messaggio oppure, ancora meglio, aggiornare il codice in modo che dipenda solo dal tipo di eccezione (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), che non è stato modificato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
