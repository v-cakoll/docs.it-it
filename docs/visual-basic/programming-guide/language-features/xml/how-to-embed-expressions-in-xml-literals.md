---
title: 'Procedura: incorporare espressioni nei valori letterali XML'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 59ba03be6e132203523427d3b7af5a163b6f05ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392314"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Procedura: incorporare espressioni nei valori letterali XML (Visual Basic)
È possibile combinare valori letterali XML con espressioni incorporate per creare un documento, un frammento o un elemento XML che contiene contenuto creato in fase di esecuzione. Gli esempi seguenti illustrano come usare le espressioni incorporate per popolare il contenuto dell'elemento, gli attributi e i nomi degli elementi in fase di esecuzione.  
  
 La sintassi per un'espressione incorporata è `<%=` `exp` `%>` , ovvero la stessa sintassi utilizzata da ASP.NET. Per ulteriori informazioni, vedere [espressioni incorporate in XML](embedded-expressions-in-xml.md).  
  
 È anche possibile usare le [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-insert-text-as-element-content"></a>Per inserire il testo come contenuto dell'elemento  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `contactName` variabile tra gli elementi del nome di apertura e di chiusura.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     Nell'esempio viene prodotto l'output seguente:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Per inserire il testo come valore di attributo  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `phoneType` variabile come valore dell' `type` attributo.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     Nell'esempio viene prodotto l'output seguente:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Per inserire il testo per il nome di un elemento  
  
- Nell'esempio seguente viene illustrato come inserire il testo contenuto nella `elementName` variabile come nome di un elemento.  
  
     Quando si creano elementi usando questa tecnica, è necessario chiuderli con il \</> tag.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     Nell'esempio viene prodotto l'output seguente:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare valori letterali XML](how-to-create-xml-literals.md)
- [Espressioni incorporate in XML](embedded-expressions-in-xml.md)
- [Creazione di XML in Visual Basic](creating-xml.md)
- [XML](index.md)
