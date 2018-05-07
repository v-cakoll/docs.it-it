---
title: 'Procedura: caricare XML da un file, da una stringa o da un flusso (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 241f6552e46d7689b42a409ba44bc747984773ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Procedura: caricare XML da un file, da una stringa o da un flusso (Visual Basic)
È possibile creare [valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) e popolarli con il contenuto da un'origine esterna, ad esempio un file, una stringa o un flusso, utilizzando diversi metodi. Questi metodi sono illustrati negli esempi seguenti.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Caricare il documento XML da un file  
  
-   Per popolare un valore letterale XML come un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oggetto da un file, usare il `Load` metodo. Questo metodo può richiedere un percorso di file, il flusso di testo o flusso XML come input.  
  
     Esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Load%28System.String%29> metodo per inserire un <xref:System.Xml.Linq.XDocument> oggetto con XML da un file di testo.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Caricare il documento XML da una stringa  
  
-   Per popolare un valore letterale XML come un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> dell'oggetto da una stringa, è possibile utilizzare il `Parse` metodo.  
  
     Esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> metodo per inserire un <xref:System.Xml.Linq.XDocument> oggetto XML da una stringa.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Caricare il documento XML da un flusso  
  
-   Per popolare un valore letterale XML come un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> dell'oggetto da un flusso, è possibile utilizzare il `Load` metodo o <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> metodo.  
  
 Esempio di codice seguente viene illustrato l'utilizzo del <xref:System.Xml.Linq.XNode.ReadFrom%2A> metodo per inserire un <xref:System.Xml.Linq.XDocument> oggetto XML da un flusso XML.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
