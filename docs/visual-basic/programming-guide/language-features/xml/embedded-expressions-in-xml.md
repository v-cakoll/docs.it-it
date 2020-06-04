---
title: Espressioni incorporate in XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: d4ff9442aa82a3eb46d56500159562174646ea58
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410257"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Espressioni incorporate in XML (Visual Basic)
Le espressioni incorporate consentono di creare valori letterali XML contenenti espressioni che vengono valutate in fase di esecuzione. La sintassi per un'espressione incorporata è `<%=` `expression` `%>` , che corrisponde alla sintassi utilizzata in ASP.NET.  
  
 È ad esempio possibile creare un valore letterale elemento XML, combinando espressioni incorporate con contenuto di testo letterale.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Se `isbnNumber` contiene l'intero 12345 e `modifiedDate` contiene la data 3/5/2006, quando viene eseguito questo codice, il valore di `book` è:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Posizione e convalida dell'espressione incorporata  
 Le espressioni incorporate possono essere visualizzate solo in determinate posizioni all'interno di espressioni letterali XML. Il percorso dell'espressione controlla i tipi che l'espressione può restituire e il modo in cui `Nothing` viene gestito. Nella tabella seguente vengono descritti i percorsi e i tipi di espressioni incorporate consentiti.  
  
|Posizione nel valore letterale|Tipo di espressione|Gestione di`Nothing`|  
|---|---|---|  
|Nome elemento XML|<xref:System.Xml.Linq.XName>|Errore|  
|Contenuto elemento XML|`Object`o matrice di`Object`|Ignorato|  
|Nome attributo elemento XML|<xref:System.Xml.Linq.XName>|Errore, a meno che anche il valore dell'attributo non sia`Nothing`|  
|Valore dell'attributo dell'elemento XML|`Object`|Dichiarazione di attributo ignorata|  
|Attributo elemento XML|<xref:System.Xml.Linq.XAttribute>o una raccolta di<xref:System.Xml.Linq.XAttribute>|Ignorato|  
|Elemento radice del documento XML|<xref:System.Xml.Linq.XElement>o una raccolta di un <xref:System.Xml.Linq.XElement> oggetto e un numero arbitrario di <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> oggetti e|Ignorato|  
  
- Esempio di espressione incorporata in un nome di elemento XML:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Esempio di espressione incorporata nel contenuto di un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Esempio di espressione incorporata in un nome di attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Esempio di espressione incorporata in un valore di attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Esempio di espressione incorporata in un attributo dell'elemento XML:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Esempio di espressione incorporata in un elemento radice di un documento XML:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Se si abilita `Option Strict` , il compilatore verifica che il tipo di ogni espressione incorporata venga ampliato al tipo richiesto. L'unica eccezione riguarda l'elemento radice di un documento XML, che viene verificato quando viene eseguito il codice. Se si compila senza `Option Strict` , è possibile incorporare espressioni di tipo `Object` e il relativo tipo viene verificato in fase di esecuzione.  
  
 Nelle posizioni in cui il contenuto è facoltativo, le espressioni incorporate che contengono `Nothing` vengono ignorate. Ciò significa che non è necessario verificare che il contenuto dell'elemento, i valori di attributo e gli elementi della matrice non siano `Nothing` prima di usare un valore letterale XML. I valori obbligatori, ad esempio i nomi degli elementi e degli attributi, non possono essere `Nothing` .  
  
 Per ulteriori informazioni sull'utilizzo di un'espressione incorporata in un particolare tipo di valore letterale, vedere valore letterale [documento XML](../../../language-reference/xml-literals/xml-document-literal.md), [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Regole di ambito  
 Il compilatore converte ogni valore letterale XML in una chiamata del costruttore per il tipo di valore letterale appropriato. Il contenuto letterale e le espressioni incorporate in un valore letterale XML vengono passati come argomenti al costruttore. Ciò significa che tutte le Visual Basic gli elementi di programmazione disponibili per un valore letterale XML sono disponibili anche per le espressioni incorporate.  
  
 All'interno di un valore letterale XML è possibile accedere ai prefissi degli spazi dei nomi XML dichiarati con l' `Imports` istruzione. È possibile dichiarare un nuovo prefisso dello spazio dei nomi XML o ombreggiare un prefisso dello spazio dei nomi XML esistente in un elemento usando l' `xmlns` attributo. Il nuovo spazio dei nomi è disponibile per i nodi figlio dell'elemento, ma non per i valori letterali XML nelle espressioni incorporate.  
  
> [!NOTE]
> Quando si dichiara un prefisso dello spazio dei nomi XML usando l' `xmlns` attributo Namespace, il valore dell'attributo deve essere una stringa costante. In questo senso, l'utilizzo dell' `xmlns` attributo è simile all'utilizzo dell' `Imports` istruzione per dichiarare uno spazio dei nomi XML. Non è possibile usare un'espressione incorporata per specificare il valore dello spazio dei nomi XML.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](creating-xml.md)
- [Valore letterale di documento XML](../../../language-reference/xml-literals/xml-document-literal.md)
- [Valore letterale di elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Cenni preliminari sui valori letterali XML](xml-literals-overview.md)
