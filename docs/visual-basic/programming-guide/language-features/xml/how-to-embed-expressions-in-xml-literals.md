---
title: 'Procedura: incorporare espressioni nei valori letterali XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Procedura: incorporare espressioni nei valori letterali XML (Visual Basic)
È possibile combinare i valori letterali XML con espressioni incorporate per creare un documento XML, frammento o elemento che contiene contenuto creato in fase di esecuzione. Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per popolare i nomi degli elementi, attributi e contenuto di un elemento in fase di esecuzione.  
  
 La sintassi di un'espressione incorporata è `<%=` `exp` `%>`, che è la stessa sintassi che [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] utilizza. Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 È inoltre possibile utilizzare il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API per creare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] oggetti. Per altre informazioni, vedere <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-insert-text-as-element-content"></a>Per inserire il testo come contenuto dell'elemento  
  
-   Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `contactName` variabile tra gli elementi di nomi di apertura e chiusura.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Per inserire il testo come valore di attributo  
  
-   Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `phoneType` variabile come valore della `type` attributo.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Per inserire il testo per un nome di elemento  
  
-   Nell'esempio seguente viene illustrato come inserire il testo contenuto nel `elementName` variabile come nome di un elemento.  
  
     Quando si creano elementi utilizzando questa tecnica, è necessario chiuderli con il \</ > tag.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Questo esempio produce il seguente output:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [Espressioni incorporate in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
