---
title: Espressioni incorporate in XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: ef8ac62d9d969ce4463931d69b0302376ca0ccc4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881538"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Espressioni incorporate in XML (Visual Basic)
Le espressioni incorporate consentono di creare valori letterali XML che contengono espressioni valutate in fase di esecuzione. Sintassi dell'espressione incorporata `<%=` `expression` `%>`, che è la stessa sintassi usata in ASP.NET.  
  
 Ad esempio, è possibile creare un elemento XML letterale, se si combinano espressioni incorporate con contenuto di testo letterale.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Se `isbnNumber` contiene l'intero 12345 e `modifiedDate` contiene la data 3 o 5/2006, quando viene eseguito questo codice, il valore di `book` è:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Convalida e la posizione di espressione incorporata  
 Le espressioni incorporate possono apparire solo in alcune posizioni all'interno di espressioni letterali XML. Può restituire la posizione nell'espressione controlla quali tipi di espressione e in che modo `Nothing` viene gestita. Nella tabella seguente descrive le posizioni consentite e tipi di espressioni incorporate.  
  
|Posizione nel valore letterale|Tipo di espressione|È possibile gestire `Nothing`|  
|---|---|---|  
|Nome dell'elemento XML|<xref:System.Xml.Linq.XName>|Error|  
|Contenuto dell'elemento XML|`Object` o una matrice di `Object`|Ignorato|  
|Nome attributo dell'elemento XML|<xref:System.Xml.Linq.XName>|Errore, a meno che non è anche il valore dell'attributo `Nothing`|  
|Valore di attributo dell'elemento XML|`Object`|Dichiarazione di attributo ignorato|  
|Attributo dell'elemento XML|<xref:System.Xml.Linq.XAttribute> oppure una raccolta di <xref:System.Xml.Linq.XAttribute>|Ignorato|  
|Elemento radice del documento XML|<xref:System.Xml.Linq.XElement> o una raccolta di uno <xref:System.Xml.Linq.XElement> oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> e <xref:System.Xml.Linq.XComment> oggetti|Ignorato|  
  
- Esempio di un'espressione incorporata in un nome di elemento XML:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Esempio di un'espressione incorporata nel contenuto di un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Esempio di un'espressione incorporata in un nome di attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Esempio di un'espressione incorporata in un valore attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Esempio di un'espressione incorporata in un attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Esempio di un'espressione incorporata in un elemento radice del documento XML:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Se si abilita `Option Strict`, il compilatore controlla che il tipo di ogni espressione incorporata può ampliarsi nel tipo richiesto. L'unica eccezione è per l'elemento radice di un documento XML, che viene verificato durante l'esecuzione del codice. Se esegue la compilazione senza `Option Strict`, è possibile incorporare le espressioni di tipo `Object` e il tipo viene verificato in fase di esecuzione.  
  
 In località in cui il contenuto è facoltativo, che contengono espressioni incorporate `Nothing` vengono ignorati. Ciò significa che non è necessario controllare il contenuto dell'elemento, i valori di attributo, e gli elementi della matrice non sono `Nothing` prima di usare un valore letterale XML. Necessari valori, ad esempio nomi di elementi e attributi, non possono essere `Nothing`.  
  
 Per altre informazioni sull'uso di un'espressione incorporata in un particolare tipo di valore letterale, vedere [letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Regole di ambito  
 Il compilatore converte ogni valore letterale XML in una chiamata al costruttore per il tipo di valore letterale appropriato. Il contenuto letterale ed espressioni incorporate in un valore letterale XML vengono passate come argomenti al costruttore. Ciò significa che tutti i Visual Basic elementi di programmazione disponibili per un valore letterale XML sono inoltre disponibili per le espressioni incorporate.  
  
 All'interno di un valore letterale XML, è possibile accedere lo spazio dei nomi XML prefissi dichiarati con la `Imports` istruzione. È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML oppure nascondere un prefisso dello spazio dei nomi XML esistente, in un elemento usando la `xmlns` attributo. Il nuovo spazio dei nomi è disponibile per i nodi figlio di quell'elemento, ma non per i valori letterali XML in espressioni incorporate.  
  
> [!NOTE]
>  Quando si dichiara un prefisso dello spazio dei nomi XML usando la `xmlns` namespace (attributo), il valore dell'attributo deve essere una stringa costante. A questo proposito, utilizzando il `xmlns` attributo è simile all'utilizzo di `Imports` dichiarare uno spazio dei nomi XML dell'istruzione. È possibile usare un'espressione incorporata per specificare il valore dello spazio dei nomi XML.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Valore letterale di documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
