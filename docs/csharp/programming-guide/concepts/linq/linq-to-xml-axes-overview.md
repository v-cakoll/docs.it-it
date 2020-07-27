---
title: Panoramica degli assi LINQ to XML (C#)
description: Informazioni sui metodi dell'asse in C#, detti anche assi. È possibile eseguire una query su un albero XML in LINQ per trovare elementi e attributi e recuperarne i valori tramite gli assi.
ms.date: 07/20/2015
ms.assetid: 516792fb-461d-40a8-8a50-9993a51258fc
ms.openlocfilehash: bbda844e8cb2e3b1ff116fd834c6ab1fdd20c1f8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165445"
---
# <a name="linq-to-xml-axes-overview-c"></a>Panoramica degli assi LINQ to XML (C#)
Dopo aver creato un albero XML o aver caricato un documento XML in un albero XML, è possibile eseguire query su di essa per cercare elementi e attributi e recuperarne i valori. Per recuperare le raccolte vengono usati i *metodi dell'asse*, detti anche *assi*. Alcuni degli assi sono metodi delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> che restituiscono raccolte <xref:System.Collections.Generic.IEnumerable%601>. Alcuni degli assi sono metodi di estensione della classe <xref:System.Xml.Linq.Extensions>. Gli assi implementati come metodi di estensione operano sulle raccolte e restituiscono raccolte.  
  
 Come descritto in [Panoramica della classe XElement](./xelement-class-overview.md), un oggetto <xref:System.Xml.Linq.XElement> rappresenta il nodo di un unico elemento. Il contenuto di un elemento può essere semplice o complesso (talvolta definito contenuto strutturato). Un elemento semplice può essere vuoto o può contenere un valore. Se il nodo include contenuto strutturato, è possibile usare i diversi metodi dell'asse per recuperare enumerazioni di elementi discendente. I metodi dell'asse usati più di frequente sono <xref:System.Xml.Linq.XContainer.Elements%2A> e <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 Oltre ai metodi dell'asse, che restituiscono raccolte, sono disponibili altri due metodi usati frequentemente nelle query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Il metodo <xref:System.Xml.Linq.XContainer.Element%2A> restituisce un singolo oggetto <xref:System.Xml.Linq.XElement>. Il metodo <xref:System.Xml.Linq.XElement.Attribute%2A> restituisce un singolo oggetto <xref:System.Xml.Linq.XAttribute>.  
  
 Per molti scopi, le query LINQ forniscono il modo più potente per esaminare un albero, estrarre dati da esso e trasformarlo. Le query LINQ operano su oggetti che implementano <xref:System.Collections.Generic.IEnumerable%601> , mentre gli [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] assi restituiscono <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> raccolte e <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XAttribute> raccolte. Tali raccolte sono necessarie per l'esecuzione delle query.  
  
 Oltre ai metodi dell'asse che recuperano raccolte di elementi e attributi, sono disponibili altri metodi dell'asse che consentono di scorrere l'albero con maggior dettaglio. Ad esempio, anziché gestire elementi e attributi, è possibile operare sui nodi dell'albero. I nodi costituiscono un livello di granularità più preciso rispetto a elementi e attributi. Quando usano i nodi, è possibile esaminare commenti XML, nodi di tipo text, istruzioni di elaborazione e altro ancora. Questa funzionalità è ad esempio utile per chi intende scrivere il codice per un elaboratore di testo e desidera salvare i documenti in formato XML. Tuttavia, la maggior parte dei programmatori XML è interessata principalmente a elementi, attributi e ai relativi valori.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Metodi per il recupero di una raccolta di elementi  
 Di seguito sono riepilogati i metodi della classe <xref:System.Xml.Linq.XElement> (o delle relative classi di base) che vengono chiamati su un oggetto <xref:System.Xml.Linq.XElement> per restituire una raccolta di elementi.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dei progenitori dell'elemento. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dei progenitori per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dei discendenti dell'elemento. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dei discendenti per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi figlio dell'elemento. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi figlio per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi che seguono l'elemento corrente. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi che seguono l'elemento per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi che precedono l'elemento corrente. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi che precedono l'elemento per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dell'elemento e dei relativi progenitori. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> dell'elemento e dei relativi discendenti. Un overload restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement> degli elementi per i quali è stato specificato <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Metodo per il recupero di un singolo elemento  
 Il metodo seguente consente di recuperare un singolo elemento figlio da un oggetto <xref:System.Xml.Linq.XElement>.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=nameWithType>|Restituisce il primo oggetto <xref:System.Xml.Linq.XElement> figlio per il quale è stato specificato <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Metodo per il recupero di una raccolta di attributi  
 Il metodo seguente consente di recuperare gli attributi da un oggetto <xref:System.Xml.Linq.XElement>.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|Restituisce un <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XAttribute> di tutti gli attributi.|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Metodo per il recupero di un singolo attributo  
 Il metodo seguente consente di recuperare un singolo attributo da un oggetto <xref:System.Xml.Linq.XElement>.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>|Restituisce l'oggetto <xref:System.Xml.Linq.XAttribute> per il quale è stato specificato <xref:System.Xml.Linq.XName>.|  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (C#)](linq-to-xml-axes-overview.md)
