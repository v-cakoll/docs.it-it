---
title: Espressioni incorporate in XML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b1cdba0a39a932f143ac98c2514240e1696a8fe0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Espressioni incorporate in XML (Visual Basic)
Espressioni incorporate consentono di creare valori letterali XML che contengono espressioni vengono valutate in fase di esecuzione. La sintassi di un'espressione incorporata è `<%=` `expression` `%>`, che è la stessa sintassi utilizzata in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Ad esempio, è possibile creare un elemento XML letterale, la combinazione di espressioni incorporate con contenuto di testo letterale.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Se `isbnNumber` contiene il numero intero 12345 e `modifiedDate` contiene la data 3/5/2006, quando viene eseguito questo codice, il valore di `book` è:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Convalida e il percorso di espressione incorporata  
 Espressioni incorporate può essere utilizzata solo determinati percorsi all'interno di espressioni valore letterale XML. Può restituire la posizione nell'espressione controlla quali tipi di espressione e come `Nothing` viene gestita. Nella tabella seguente vengono descritti i percorsi consentiti e i tipi di espressioni incorporate.  
  
|Posizione nel valore letterale|Tipo dell'espressione|Gestione di`Nothing`|  
|---|---|---|  
|Nome dell'elemento XML|<xref:System.Xml.Linq.XName>|Errore|  
|Contenuto dell'elemento XML|`Object`o una matrice di`Object`|Ignorato|  
|Nome attributo dell'elemento XML|<xref:System.Xml.Linq.XName>|Errore, a meno che non è il valore dell'attributo`Nothing`|  
|Valore di attributo dell'elemento XML|`Object`|Dichiarazione di attributo ignorata.|  
|Attributo dell'elemento XML|<xref:System.Xml.Linq.XAttribute>o una raccolta di<xref:System.Xml.Linq.XAttribute>|Ignorato|  
|Elemento radice del documento XML|<xref:System.Xml.Linq.XElement>una raccolta di uno o <xref:System.Xml.Linq.XElement> oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti|Ignorato|  
  
-   Esempio di un'espressione incorporata in un nome di un elemento XML:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Esempio di un'espressione incorporata nel contenuto di un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Esempio di un'espressione incorporata in un nome di attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Esempio di un'espressione incorporata in un valore di attributo XML elemento:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Esempio di un'espressione incorporata in un attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Esempio di un'espressione incorporata in un elemento radice del documento XML:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Se si abilita `Option Strict`, il compilatore controlla che il tipo di ogni espressione incorporata può ampliarsi nel tipo richiesto. L'unica eccezione è per l'elemento radice di un documento XML, che viene verificato se il codice viene eseguito. Se esegue la compilazione senza `Option Strict`, è possibile incorporare espressioni di tipo `Object` e il tipo viene verificato in fase di esecuzione.  
  
 In posizioni in cui contenuto è facoltativo, le espressioni che contengono incorporate `Nothing` vengono ignorati. Questo significa che non è necessario controllare il contenuto dell'elemento, i valori di attributo e non sono elementi di matrice `Nothing` prima di utilizzare un valore letterale XML. Richiesta non possono essere valori, ad esempio nomi di elementi e attributi, `Nothing`.  
  
 Per ulteriori informazioni sull'utilizzo di un'espressione incorporata in un particolare tipo di valore letterale, vedere [valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Regole di ambito  
 Il compilatore converte ogni valore letterale XML in una chiamata al costruttore per il tipo di valore letterale appropriato. Le espressioni incorporate in un valore letterale XML contenuto in formato letterale vengono passate come argomenti al costruttore. Ciò significa che tutti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] elementi di programmazione disponibili per un valore letterale XML sono inoltre disponibili per le espressioni incorporate.  
  
 All'interno di un valore letterale XML, è possibile accedere lo spazio dei nomi XML prefissi dichiarati con la `Imports` istruzione. È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML o nascondere un prefisso dello spazio dei nomi XML esistente, in un elemento utilizzando il `xmlns` attributo. Il nuovo spazio dei nomi è disponibile per i nodi figlio di tale elemento, ma non a valori letterali XML in espressioni incorporate.  
  
> [!NOTE]
>  Quando si dichiara un prefisso dello spazio dei nomi XML usando il `xmlns` attributo dello spazio dei nomi, il valore dell'attributo deve essere una stringa costante. In questo senso, utilizzando il `xmlns` attributo è simile all'utilizzo di `Imports` istruzione per dichiarare uno spazio dei nomi XML. È possibile utilizzare un'espressione incorporata per specificare il valore di spazio dei nomi XML.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
