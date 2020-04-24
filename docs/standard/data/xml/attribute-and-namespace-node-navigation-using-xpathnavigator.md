---
title: Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 23975f88-e0af-4b88-93de-9e20e11880ad
ms.openlocfilehash: 6809a2a47a9ca25a16a9be75a0a8a8b03f98a21d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711155"
---
# <a name="attribute-and-namespace-node-navigation-using-xpathnavigator"></a>Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator
La classe <xref:System.Xml.XPath.XPathNavigator> offre due set di metodi di navigazione. Il primo set, che si trova nell'argomento [Navigazione del set di nodi con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), consente di navigare nei *set di nodi* di un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>. Il secondo set, descritto in questo argomento, consente di navigare nei *nodi di attributi e dello spazio dei nomi* di un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.  
  
## <a name="attribute-node-navigation"></a>Navigazione di nodi di attributi  
 Gli attributi sono proprietà di un elemento, non elementi figlio dell'elemento. Questa distinzione è importante, a causa dei metodi della classe <xref:System.Xml.XPath.XPathNavigator> usati per esplorare i nodi di pari livello, padre e figlio.  
  
 Ad esempio, per spostarsi da un elemento a un attributo o tra più attributi non vengono usati i metodi <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>. Infatti gli attributi dispongono di metodi di navigazione distinti.  
  
 Di seguito sono riportati i metodi di navigazione degli attributi della classe <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>  
  
 Quando il nodo corrente è un elemento, è possibile usare la proprietà <xref:System.Xml.XPath.XPathNavigator.HasAttributes%2A> per verificare la presenza di eventuali attributi associati all'elemento. Una volta appurato che l'elemento dispone di attributi, sono disponibili diversi metodi per accedere agli attributi. Per rimuovere un singolo attributo dall'elemento, usare il metodo <xref:System.Xml.XPath.XPathNavigator.GetAttribute%2A>. Per spostare l'oggetto <xref:System.Xml.XPath.XPathNavigator> su un attributo specifico, usare il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>. È inoltre possibile scorrere ogni attributo di un elemento usando il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A> seguito da più chiamate al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>.  
  
> [!NOTE]
> Quando l'oggetto <xref:System.Xml.XPath.XPathNavigator> è posizionato in corrispondenza di un nodo di attributo o dello spazio dei nomi, i metodi <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> restituiscono sempre `false` e non influiscono sulla posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator>. Eccezioni sono rappresentate dai metodi <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
## <a name="namespace-node-navigation"></a>Navigazione di nodi dello spazio dei nomi  
 A ciascun elemento è associato un set di nodi dello spazio dei nomi, uno per ogni singolo prefisso dello spazio dei nomi associato a un URI dello spazio dei nomi nell'ambito per l'elemento (incluso il prefisso XML associato allo spazio dei nomi `http://www.w3.org/XML/1998/namespace` e dichiarato in modo implicito in ogni documento XML) e uno per lo spazio dei nomi predefinito se è presente nell'ambito dell'elemento. L'elemento è l'elemento padre di ogni nodo dello spazio dei nomi. Tuttavia, un nodo dello spazio dei nomi non è un elemento figlio dell'elemento padre corrispondente.  
  
 Come nel caso degli attributi, per spostarsi da un elemento a un nodo dello spazio dei nomi o tra più nodi dello spazio dei nomi non vengono usati i metodi <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>. Infatti i nodi dello spazio dei nomi dispongono di metodi di navigazione distinti.  
  
 Di seguito sono riportati i metodi di navigazione dello spazio dei nomi della classe <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>  
  
 È sempre presente almeno un nodo dello spazio dei nomi nell'ambito di ogni elemento in un documento XML. Questo è il nodo dello spazio dei nomi con il prefisso `xml` e l'URI dello spazio dei nomi `http://www.w3.org/XML/1998/namespace`. Per recuperare un URI dello spazio dei nomi nell'ambito in base a un prefisso specifico, usare il metodo <xref:System.Xml.XPath.XPathNavigator.GetNamespace%2A>. Per spostare l'oggetto <xref:System.Xml.XPath.XPathNavigator> su un nodo specifico dello spazio dei nomi, usare il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>. È inoltre possibile scorrere ogni nodo dello spazio dei nomi di un elemento usando il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> seguito da più chiamate al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>.  
  
> [!NOTE]
> Quando l'oggetto <xref:System.Xml.XPath.XPathNavigator> è posizionato in corrispondenza di un nodo di attributo o dello spazio dei nomi, i metodi <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> restituiscono sempre `false` e non influiscono sulla posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator>. Eccezioni sono rappresentate dai metodi <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
### <a name="the-xpathnamespacescope-enumeration"></a>Enumerazione di XPathNamespaceScope  
 Durante la navigazione dei nodi dello spazio dei nomi è possibile chiamare i metodi <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> con un parametro <xref:System.Xml.XPath.XPathNamespaceScope>. Tali metodi si comportano in modo diverso rispetto alle relative controparti chiamate senza parametri. L'enumerazione <xref:System.Xml.XPath.XPathNamespaceScope> presenta i valori <xref:System.Xml.XPath.XPathNamespaceScope.All>, <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml> o <xref:System.Xml.XPath.XPathNamespaceScope.Local>.  
  
 Negli esempi seguenti viene mostrato quali spazi dei nomi vengono restituiti dai metodi <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> in vari ambiti in un documento XML.  
  
```xml  
<root>  
    <element1 xmlns="http://www.contoso.com" xmlns:books="http://www.contoso.com/books">  
        <element2 />  
    </element1>  
</root>  
```  
  
 La sequenza di spazi dei nomi (ovvero, lo spazio dei nomi in corrispondenza del quale si trova l'oggetto <xref:System.Xml.XPath.XPathNavigator> dopo la chiamata al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> seguita da una serie di chiamate al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>) è la seguente.  
  
- Quando è posizionata su `element2`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` e `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Quando è posizionata su `element1`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` e `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Quando è posizionata su `root`: `xmlns:xml="http://www.w3.org/XML/1998/namespace".`  
  
> [!NOTE]
> La classe <xref:System.Xml.XPath.XPathNavigator> restituisce i nodi dello spazio dei nomi in ordine inverso rispetto al documento. Pertanto, il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> essenzialmente consente uno spostamento all'ultimo nodo dello spazio dei nomi nell'ambito corrente.  
  
 Negli esempi seguenti viene mostrato quali spazi dei nomi vengono restituiti dai metodi <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> e <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> con l'enumerazione <xref:System.Xml.XPath.XPathNamespaceScope> specificata in vari ambiti in un documento XML.  
  
```xml  
<root xmlns="http://www.contoso.com" xmlns:a="http://www.contoso.com/a" xmlns:b="http://www.contoso.com/b">  
    <child1 xmlns="" xmlns:a="urn:a">  
        <child2 xmlns:c="urn:c" />  
    </child1>  
</root>  
```  
  
 Quando è posizionata su `child2`, la sequenza di spazi dei nomi (ovvero, lo spazio dei nomi in corrispondenza del quale si trova l'oggetto <xref:System.Xml.XPath.XPathNavigator> dopo la chiamata al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> seguita da una serie di chiamate al metodo <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>) è la seguente.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.All>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"`, `xmlns="http://www.contoso.com"` e `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"` e `xmlns="http://www.contoso.com"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.Local>: `xmlns:c="urn:c"`.  
  
> [!NOTE]
> La classe <xref:System.Xml.XPath.XPathNavigator> restituisce i nodi dello spazio dei nomi in ordine inverso rispetto al documento. Pertanto, il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> essenzialmente consente uno spostamento all'ultimo nodo dello spazio dei nomi nell'ambito corrente.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Elaborazione di dati XML con il modello di dati XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Navigazione del set di nodi con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [Estrazione di dati XML con XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
- [Accesso a dati XML fortemente tipizzati con XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
