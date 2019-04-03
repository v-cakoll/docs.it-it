---
title: Valore letterale di documento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814627"
---
# <a name="xml-document-literal-visual-basic"></a>Valore letterale di documento XML (Visual Basic)
Un valore letterale che rappresenta un <xref:System.Xml.Linq.XDocument> oggetto.  
  
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
|`encoding`|Facoltativo. Usa testo letterale che dichiara la codifica del documento.|  
|`standalone`|Facoltativo. Testo letterale. Deve essere "yes" o "no".|  
|`piCommentList`|Facoltativo. Elenco di istruzioni di elaborazione XML e commenti in formato XML. Assume il formato seguente:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Ogni `piComment` può essere uno dei seguenti:<br /><br /> -   [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [Valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Obbligatorio. Elemento radice del documento. Il formato è uno dei seguenti:<br /><br /> <ul><li>[Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Espressione del form incorporata `<%=` `elementExp` `%>`. Il `elementExp` restituisce uno dei seguenti:<br /><br /> <ul><li>Oggetto <xref:System.Xml.Linq.XElement>.</li><li>Una raccolta che contiene un <xref:System.Xml.Linq.XElement> oggetto e un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti.</li></ul></li></ul><br /> Per altre informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Note  
 Un valore letterale documento XML viene identificato dalla dichiarazione XML all'inizio del valore letterale. Anche se ogni valore letterale documento XML deve avere esattamente un elemento XML radice, può avere un numero qualsiasi di istruzioni di elaborazione XML e commenti in formato XML.  
  
 Un valore letterale documento XML non può trovarsi in un elemento XML.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga. In questo modo è possibile copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.  
  
 Il compilatore Visual Basic converte il valore letterale documento XML in chiamate per il <xref:System.Xml.Linq.XDocument.%23ctor%2A> e <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> costruttori.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un documento XML che dispone di una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [Valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [Valore letterale di commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [Valore letterale elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
