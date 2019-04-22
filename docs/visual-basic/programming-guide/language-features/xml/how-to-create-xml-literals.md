---
title: 'Procedura: Creare valori letterali XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836864"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Procedura: Creare valori letterali XML (Visual Basic)
È possibile creare un documento, frammento o elemento XML direttamente nel codice usando un valore letterale XML. Gli esempi in questo argomento illustrano come creare un elemento XML che dispone di tre elementi figlio e come creare un documento XML.  
  
 È anche possibile usare la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Per creare un elemento XML  
  
-   Creare il XML inline usando la sintassi dei valori letterali XML, che corrisponde alla sintassi XML effettivo.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Eseguire il codice. L'output di questo codice è:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Per creare un documento XML  
  
-   Creare il documento XML inline. Il codice seguente crea un documento XML con sintassi del valore letterale, una dichiarazione XML, un'istruzione di elaborazione, un commento e un elemento che contiene un altro elemento.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Eseguire il codice. L'output di questo codice è:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Vedere anche

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
