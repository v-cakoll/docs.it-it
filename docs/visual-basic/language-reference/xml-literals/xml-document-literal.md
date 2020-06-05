---
title: Valore letterale di documento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 3a2182d2937827bc8dc45e22307a3668420261a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400202"
---
# <a name="xml-document-literal-visual-basic"></a>Valore letterale di documento XML (Visual Basic)
Valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`encoding`|Facoltativa. Testo letterale che dichiara la codifica utilizzata dal documento.|  
|`standalone`|Facoltativa. Testo letterale. Deve essere "Yes" o "No".|  
|`piCommentList`|Facoltativa. Elenco di istruzioni di elaborazione XML e commenti XML. Accetta il formato seguente:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Ognuno `piComment` può essere uno dei seguenti:<br /><br /> -   [Valore letterale istruzione di elaborazione XML](xml-processing-instruction-literal.md).<br />-   [Valore letterale del commento XML](xml-comment-literal.md).|  
|`rootElement`|Obbligatorio. Elemento radice del documento. Il formato è uno dei seguenti:<br /><br /> <ul><li>[Valore letterale elemento XML](xml-element-literal.md).</li><li>Espressione incorporata del form `<%=` `elementExp` `%>` . `elementExp`Restituisce uno dei seguenti elementi:<br /><br /> <ul><li>Oggetto <xref:System.Xml.Linq.XElement>.</li><li>Raccolta che contiene un <xref:System.Xml.Linq.XElement> oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> oggetti e.</li></ul></li></ul><br /> Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Commenti  
 Un valore letterale di documento XML viene identificato dalla dichiarazione XML all'inizio del valore letterale. Sebbene ogni valore letterale del documento XML debba contenere esattamente un elemento XML radice, può includere un numero qualsiasi di istruzioni di elaborazione XML e commenti XML.  
  
 Un valore letterale di documento XML non può essere incluso in un elemento XML.  
  
> [!NOTE]
> Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale del documento XML in chiamate ai <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> costruttori e.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un documento XML con una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [Valore letterale di istruzione di elaborazione XML](xml-processing-instruction-literal.md)
- [Valore letterale di commento XML](xml-comment-literal.md)
- [Valore letterale di elemento XML](xml-element-literal.md)
- [Valori letterali XML](index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
