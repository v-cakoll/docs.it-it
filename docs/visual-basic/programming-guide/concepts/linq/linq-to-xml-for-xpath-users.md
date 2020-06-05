---
title: LINQ to XML per gli utenti di XPath
ms.date: 07/20/2015
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
ms.openlocfilehash: 7942d33831644875f390e9128965fe1c36433808
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368790"
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML per gli utenti di XPath (Visual Basic)

In questo set di argomenti vengono illustrate varie espressioni XPath e gli equivalenti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In tutti gli esempi viene usata la funzionalità di XPath in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] resa disponibile dai metodi di estensione in <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. Negli esempi vengono eseguite sia l'espressione XPath che l'espressione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Vengono quindi confrontati i risultati di entrambe le query, verificando che l'espressione XPath sia equivalente dal punto di vista funzionale alla query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Poiché entrambi i tipi di query restituiscono nodi dalla stessa struttura ad albero XML, il confronto dei risultati delle query viene eseguito usando l'identità referenziale.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Confronto tra XPath e LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Viene fornita una panoramica delle analogie e differenze tra XPath e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Procedura: trovare un elemento figlio (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-child-element-xpath-linq-to-xml.md)|Confronta l'asse degli elementi figlio XPath con il [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> metodo.<br /><br /> L'espressione XPath associata è:`"DeliveryNotes"`.|  
|[Procedura: trovare un elenco di elementi figlio (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Confronta l'asse degli elementi figlio XPath con l' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> asse.<br /><br /> L'espressione XPath associata è:`"./*"`.|  
|[Procedura: trovare l'elemento radice (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-root-element-xpath-linq-to-xml.md)|Viene illustrato un confronto su come ottenere l'elemento radice con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"/PurchaseOrders"`.|  
|[Procedura: trovare elementi discendenti (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendant-elements-xpath-linq-to-xml.md)|Viene illustrato un confronto su come ottenere gli elementi discendenti con un determinato nome con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"//Name"`.|  
|[Procedura: filtrare in un attributo (XPath-LINQ to XML) (Visual Basic)](how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Viene illustrato un confronto su come ottenere gli elementi discendenti con un attributo con un valore specificato con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"./Address[@Type='Shipping']"`.|  
|[Procedura: trovare elementi correlati (XPath-LINQ to XML) (Visual Basic)](how-to-find-related-elements-xpath-linq-to-xml.md)|Viene illustrato un confronto su come ottenere un elemento selezionando un attributo cui viene fatto riferimento dal valore di un altro elemento con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"./Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`.|  
|[Procedura: trovare elementi in uno spazio dei nomi (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-in-a-namespace.md)|Viene confrontato l'utilizzo della <xref:System.Xml.XmlNamespaceManager> classe XPath con la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> proprietà della <xref:System.Xml.Linq.XName> classe per l'utilizzo di spazi dei nomi XML.<br /><br /> L'espressione XPath associata è:`"./aw:*"`.|  
|[Procedura: trovare elementi di pari livello precedenti (XPath-LINQ to XML) (Visual Basic)](how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Viene illustrato un confronto tra l'asse `preceding-sibling` XPath e l'asse [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] figlio <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> L'espressione XPath associata è:`"preceding-sibling::*"`.|  
|[Procedura: trovare discendenti di un elemento figlio (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Viene illustrato un confronto su come ottenere gli elementi discendenti di un elemento figlio con un determinato nome con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"./Paragraph//Text/text()"`.|  
|[Procedura: trovare un'Unione di due percorsi di posizione (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-union-of-two-location-paths-xpath.md)|Viene illustrato un confronto tra l'utilizzo dell'operatore di unione, <code>&#124;</code>, in XPath e l'utilizzo dell'operatore di query standard <xref:System.Linq.Enumerable.Concat%2A> in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:<code>"//Category&#124;//Price"</code>.|  
|[Procedura: trovare nodi di pari livello (XPath-LINQ to XML) (Visual Basic)](how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Viene illustrato un confronto su come trovare tutti gli elementi di pari livello di un nodo con un nome specificato con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"../Book"`.|  
|[Procedura: trovare un attributo dell'elemento padre (XPath-LINQ to XML) (Visual Basic)](how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Viene illustrato un confronto su come spostarsi all'elemento padre e trovare un attributo associato con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"../@id"`.|  
|[Procedura: trovare attributi di elementi di pari livello con un nome specifico (XPath-LINQ to XML) (Visual Basic)](how-to-find-attributes-of-siblings-with-a-specific-name.md)|Viene illustrato un confronto su come trovare attributi specifici degli elementi di pari livello del nodo di contesto con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"../Book/@id"`.|  
|[Procedura: trovare elementi con un attributo specifico (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-with-a-specific-attribute.md)|Viene illustrato un confronto su come trovare tutti gli elementi contenenti un attributo specifico con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"./*[@Select]"`.|  
|[Procedura: trovare elementi figlio in base alla posizione (XPath-LINQ to XML) (Visual Basic)](how-to-find-child-elements-based-on-position.md)|Viene illustrato un confronto su come trovare un elemento in base alla posizione relativa con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"Test[position() >= 2 and position() <= 4]"`.|  
|[Procedura: trovare l'elemento di pari livello immediatamente precedente (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Viene illustrato un confronto su come trovare l'elemento di pari livello immediatamente precedente di un nodo con XPath e con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> L'espressione XPath associata è:`"preceding-sibling::*[1]"`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XPath?displayProperty=nameWithType>
- [Esecuzione di query su strutture ad albero XML (Visual Basic)](querying-xml-trees.md)
- [Elaborazione di dati XML con il modello di dati XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
