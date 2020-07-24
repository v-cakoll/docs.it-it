---
title: Aggiunta di elementi, attributi e nodi a un albero XML (C#)
description: Informazioni sui metodi per aggiungere contenuto come elementi, attributi, commenti, istruzioni di elaborazione e testo a un albero XML esistente.
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 78a84401494e2d4280799632fa42dc95574e3e10
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105552"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a>Aggiunta di elementi, attributi e nodi a un albero XML (C#)
È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.  
  
## <a name="methods-for-adding-content"></a>Metodi per l'aggiunta di contenuto  
 I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Consente di aggiungere il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.|  
  
 I seguenti metodi consentono di aggiungere contenuto come nodi di pari livello di un oggetto <xref:System.Xml.Linq.XNode>. Il nodo più comune al quale viene aggiunto contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, tra cui <xref:System.Xml.Linq.XText> o <xref:System.Xml.Linq.XComment>.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.|  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.  
  
### <a name="code"></a>Codice  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a>Commenti  
 Questo codice genera l'output seguente:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  