---
title: 'Procedura: Caricare il documento XML da un File, stringa o Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 36a7f23eed7f47e8c33958f96e8e3694fb958d11
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977695"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Procedura: Caricare il documento XML da un File, stringa o Stream (Visual Basic)
È possibile creare [valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) e popolarli con i contenuti da un'origine esterna, ad esempio un file, una stringa o un flusso usando diversi metodi. Questi metodi sono illustrati negli esempi seguenti.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Caricare il documento XML da un file  
  
-   Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> oggetto da un file, usare il `Load` (metodo). Questo metodo può accettare un percorso del file, flusso di testo o flusso XML come input.  
  
     Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XDocument.Load%28System.String%29> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da un file di testo.  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a>Caricare il documento XML da una stringa  
  
-   Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> dell'oggetto da una stringa, è possibile usare il `Parse` (metodo).  
  
     Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da una stringa.  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a>Caricare il documento XML da un flusso  
  
-   Per popolare un valore letterale, ad esempio XML un' <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> dell'oggetto da un flusso, è possibile utilizzare il `Load` metodo o il <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> (metodo).  
  
 Esempio di codice seguente viene illustrato l'utilizzo dei <xref:System.Xml.Linq.XNode.ReadFrom%2A> metodo per popolare un <xref:System.Xml.Linq.XDocument> oggetto con il codice XML da un flusso XML.  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
