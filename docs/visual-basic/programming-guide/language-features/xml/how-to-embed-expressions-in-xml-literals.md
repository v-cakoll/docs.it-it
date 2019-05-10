---
title: 'Procedura: Incorporare espressioni nei valori letterali XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: ca80ac666e8676e4e58a9741b00125c0126570fa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598384"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Procedura: Incorporare espressioni nei valori letterali XML (Visual Basic)
È possibile combinare i valori letterali XML con espressioni incorporate per creare un documento XML, frammento o elemento che contiene contenuto creato in fase di esecuzione. Gli esempi seguenti illustrano come usare espressioni incorporate per popolare i nomi degli elementi, attributi e contenuto di un elemento in fase di esecuzione.  
  
 Sintassi dell'espressione incorporata `<%=` `exp` `%>`, che è la stessa sintassi che [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Usa. Per altre informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 È anche possibile usare la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-insert-text-as-element-content"></a>Per inserire il testo come contenuto dell'elemento  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `contactName` variabile tra gli elementi di nomi di apertura e chiusura.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Per inserire il testo come valore di attributo  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `phoneType` variabile come valore del `type` attributo.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Per inserire il testo per un nome di elemento  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `elementName` variabile come nome di un elemento.  
  
     Quando si creano elementi utilizzando questa tecnica, è necessario chiuderli con la \</ > tag.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [Espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
