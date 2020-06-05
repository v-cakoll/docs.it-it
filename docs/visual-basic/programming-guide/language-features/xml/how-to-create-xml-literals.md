---
title: 'Procedura: creare valori letterali XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 61b138c0851c747ed30eedc10cb882cc3b03c4d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392610"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Procedura: creare valori letterali XML (Visual Basic)
È possibile creare un documento, un frammento o un elemento XML direttamente nel codice usando un valore letterale XML. Negli esempi di questo argomento viene illustrato come creare un elemento XML con tre elementi figlio e come creare un documento XML.  
  
 È anche possibile usare le [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Per creare un elemento XML  
  
- Creare l'XML inline usando la sintassi del valore letterale XML, che corrisponde alla sintassi XML effettiva.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Eseguire il codice. L'output di questo codice è:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Per creare un documento XML  
  
- Creare il documento XML inline. Il codice seguente crea un documento XML con sintassi letterale, una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Eseguire il codice. L'output di questo codice è:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Vedere anche

- [XML](index.md)
- [Creazione di XML in Visual Basic](creating-xml.md)
- [Valore letterale di elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)
- [Valore letterale di documento XML](../../../language-reference/xml-literals/xml-document-literal.md)
