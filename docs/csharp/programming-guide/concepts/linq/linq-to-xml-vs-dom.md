---
title: LINQ to XML rispetto a DOM (C#)
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f6a89bba1ff2753f04406a060beb37bf2bf6552c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344789"
---
# <a name="linq-to-xml-vs-dom-c"></a>LINQ to XML rispetto a DOM (C#)
Questa sezione descrive alcune delle differenze principali tra [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e l'API di programmazione XML attualmente più diffusa, ovvero DOM (Document Object Model) W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Nuove modalità di creazione degli alberi XML  
 In W3C DOM un albero XML viene compilata dal basso verso l'alto, ossia si crea un documento, si creano gli elementi e quindi si aggiungono gli elementi al documento.  
  
 Ad esempio, di seguito viene illustrata la creazione di un tipico albero XML tramite l'implementazione Microsoft di DOM, <xref:System.Xml.XmlDocument>:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";          
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";          
XmlElement street1 = doc.CreateElement("Street1");          
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 Questo stile di codifica non fornisce molte informazioni visive sulla struttura dell'albero XML. Oltre a questo approccio di creazione di un albero, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporta un approccio alternativo, la *costruzione funzionale*. Nella costruzione funzionale vengono usati i costruttori <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute> per compilare un albero XML.  
  
 Di seguito è illustrata la creazione dello stesso albero XML tramite la costruzione funzionale di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",   
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Si noti che il rientro del codice per costruire la struttura ad albero XML illustra la struttura dell'XML sottostante.  
  
 Per altre informazioni, vedere [Creazione di alberi XML (C#)](./linq-to-xml-overview.md).  
  
## <a name="working-directly-with-xml-elements"></a>Utilizzo diretto di elementi XML  
 Quando si programma con XML, l'obiettivo principale riguarda in genere gli elementi XML e talvolta gli attributi. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile usare direttamente gli elementi e gli attributi XML. È ad esempio possibile eseguire le operazioni seguenti:  
  
- Creare elementi XML senza usare affatto un oggetto documento. In questo modo la programmazione risulta semplificata quando è necessario usare frammenti di alberi XML.  
  
- Caricare oggetti `T:System.Xml.Linq.XElement` direttamente da un file XML.  
  
- Serializzare oggetti `T:System.Xml.Linq.XElement` a un file o un flusso.  
  
 Al contrario, in W3C DOM il documento XML viene usato come contenitore logico per l'albero XML. In DOM i nodi XML, inclusi elementi e attributi, devono essere creati nel contesto di un documento XML. Di seguito è riportato un frammento del codice usato per creare un elemento name in DOM:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 Se si desidera usare un elemento in più documenti, è necessario importare i nodi tra documenti. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo livello di complessità viene evitato.  
  
 Con LINQ to XML la classe <xref:System.Xml.Linq.XDocument> viene usata solo se si desidera aggiungere un commento o un'istruzione di elaborazione al livello radice del documento.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Gestione semplificata di nomi e spazi dei nomi  
 La gestione di nomi, spazi dei nomi e prefissi di spazio dei nomi è in genere un aspetto complesso della programmazione XML. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nomi e spazi dei nomi sono semplificati grazie all'eliminazione della necessità di gestire i prefissi di spazio dei nomi. Se si desidera, è possibile controllare i prefissi di spazio dei nomi. Se tuttavia si decide di non controllare in modo esplicito i prefissi, durante la serializzazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] assegnerà i prefissi di spazio dei nomi se sono necessari oppure eseguirà la serializzazione usando spazi dei nomi predefiniti, se non sono necessari. Se vengono utilizzati gli spazi dei nomi predefiniti, il documento risultante non conterrà prefissi di spazio dei nomi. Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).  
  
 Un altro problema di DOM è che non consente di modificare il nome di un nodo. È invece necessario creare un nuovo nodo e copiarvi tutti i nodi figlio, perdendo l'identità del nodo originale. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo problema viene evitato grazie alla possibilità di impostare la proprietà <xref:System.Xml.Linq.XName> in un nodo.  
  
## <a name="static-method-support-for-loading-xml"></a>Supporto dei metodi statici per il caricamento di XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di caricare XML usando metodi statici anziché metodi di istanza, semplificando le operazioni di caricamento e analisi. Per ulteriori informazioni, vedere [come caricare XML da un fileC#()](./how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Rimozione del supporto per i costrutti DTD  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] la programmazione XML risulta ulteriormente semplificata tramite la rimozione del supporto per entità e riferimenti di entità. Oltre a essere complessa, la gestione di entità viene utilizzata raramente. Rimuovendone il supporto è possibile riscontrare un aumento delle prestazioni e un'interfaccia di programmazione semplificata. Quando un albero [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene popolato, tutte le entità DTD vengono espanse.  
  
## <a name="support-for-fragments"></a>Supporto per i frammenti  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] non sono disponibili equivalenti per la classe `XmlDocumentFragment`. In molti casi, tuttavia, il concetto di `XmlDocumentFragment` può essere gestito dal risultato di una query digitato come <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XNode> o <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>.  
  
## <a name="support-for-xpathnavigator"></a>Supporto per XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporta <xref:System.Xml.XPath.XPathNavigator> tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.XPath?displayProperty=nameWithType>. Per ulteriori informazioni, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Supporto per lo spazio vuoto e il rientro  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene gestito più agevolmente rispetto a DOM.  
  
 In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro. Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo. Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato. È possibile che si desideri non modificare questo rientro in alcun modo. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.  
  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene archiviato come nodo <xref:System.Xml.Linq.XText>, anziché con un nodo <xref:System.Xml.XmlNodeType.Whitespace> speciale, come invece avviene in DOM.  
  
## <a name="support-for-annotations"></a>Supporto per le annotazioni  
 Gli elementi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supportano un set estensibile di annotazioni. Questa funzione è utile per tenere traccia di varie informazioni su un elemento, ad esempio informazioni sullo schema, informazioni su se l'elemento è associato a un'interfaccia utente o altri tipi di informazioni specifiche dell'applicazione. Per altre informazioni, vedere [Annotazioni LINQ to XML](./linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Supporto per le informazioni sullo schema  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporta la convalida XSD tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>. È possibile verificare che un albero XML sia conforme a un XSD. È possibile popolare l'albero XML con le informazioni sulla convalida post-schema. Per ulteriori informazioni, vedere [How to Validate Using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.
  
## <a name="see-also"></a>Vedere anche

- [Introduzione (LINQ to XML)](./linq-to-xml-overview.md)
