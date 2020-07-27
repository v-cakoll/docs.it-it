---
title: LINQ to XML rispetto a DOM (C#)
description: Informazioni sulle differenze principali tra LINQ to XML e l'API di programmazione XML W3C Document Object Model (DOM).
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f5fc3fd7869079d47d7c9031e3668afeed7a117b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165345"
---
# <a name="linq-to-xml-vs-dom-c"></a><span data-ttu-id="9c576-103">LINQ to XML rispetto a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="9c576-103">LINQ to XML vs. DOM (C#)</span></span>
<span data-ttu-id="9c576-104">Questa sezione descrive alcune delle differenze principali tra [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e l'API di programmazione XML attualmente più diffusa, ovvero DOM (Document Object Model) W3C.</span><span class="sxs-lookup"><span data-stu-id="9c576-104">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="9c576-105">Nuove modalità di creazione degli alberi XML</span><span class="sxs-lookup"><span data-stu-id="9c576-105">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="9c576-106">In W3C DOM un albero XML viene compilata dal basso verso l'alto, ossia si crea un documento, si creano gli elementi e quindi si aggiungono gli elementi al documento.</span><span class="sxs-lookup"><span data-stu-id="9c576-106">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="9c576-107">Ad esempio, di seguito viene illustrata la creazione di un tipico albero XML tramite l'implementazione Microsoft di DOM, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="9c576-107">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
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
  
 <span data-ttu-id="9c576-108">Questo stile di codifica non fornisce molte informazioni visive sulla struttura dell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-108">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> <span data-ttu-id="9c576-109">Oltre a questo approccio di creazione di un albero, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporta un approccio alternativo, la *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="9c576-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="9c576-110">Nella costruzione funzionale vengono usati i costruttori <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute> per compilare un albero XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-110">Functional construction uses the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors to build an XML tree.</span></span>  
  
 <span data-ttu-id="9c576-111">Di seguito è illustrata la creazione dello stesso albero XML tramite la costruzione funzionale di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9c576-111">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
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
  
 <span data-ttu-id="9c576-112">Si noti che il rientro del codice per costruire la struttura ad albero XML illustra la struttura dell'XML sottostante.</span><span class="sxs-lookup"><span data-stu-id="9c576-112">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="9c576-113">Per altre informazioni, vedere [Creazione di alberi XML (C#)](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c576-113">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="9c576-114">Utilizzo diretto di elementi XML</span><span class="sxs-lookup"><span data-stu-id="9c576-114">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="9c576-115">Quando si programma con XML, l'obiettivo principale riguarda in genere gli elementi XML e talvolta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="9c576-115">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="9c576-116">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile usare direttamente gli elementi e gli attributi XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-116">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="9c576-117">Ad esempio, è possibile eseguire quanto le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c576-117">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="9c576-118">Creare elementi XML senza usare affatto un oggetto documento.</span><span class="sxs-lookup"><span data-stu-id="9c576-118">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="9c576-119">In questo modo la programmazione risulta semplificata quando è necessario usare frammenti di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-119">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="9c576-120">Caricare oggetti `T:System.Xml.Linq.XElement` direttamente da un file XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-120">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="9c576-121">Serializzare oggetti `T:System.Xml.Linq.XElement` a un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="9c576-121">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="9c576-122">Al contrario, in W3C DOM il documento XML viene usato come contenitore logico per l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-122">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="9c576-123">In DOM i nodi XML, inclusi elementi e attributi, devono essere creati nel contesto di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-123">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="9c576-124">Di seguito è riportato un frammento del codice usato per creare un elemento name in DOM:</span><span class="sxs-lookup"><span data-stu-id="9c576-124">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 <span data-ttu-id="9c576-125">Se si desidera usare un elemento in più documenti, è necessario importare i nodi tra documenti.</span><span class="sxs-lookup"><span data-stu-id="9c576-125">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> <span data-ttu-id="9c576-126">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo livello di complessità viene evitato.</span><span class="sxs-lookup"><span data-stu-id="9c576-126">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="9c576-127">Con LINQ to XML la classe <xref:System.Xml.Linq.XDocument> viene usata solo se si desidera aggiungere un commento o un'istruzione di elaborazione al livello radice del documento.</span><span class="sxs-lookup"><span data-stu-id="9c576-127">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="9c576-128">Gestione semplificata di nomi e spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="9c576-128">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="9c576-129">La gestione di nomi, spazi dei nomi e prefissi di spazio dei nomi è in genere un aspetto complesso della programmazione XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-129">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> <span data-ttu-id="9c576-130">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nomi e spazi dei nomi sono semplificati grazie all'eliminazione della necessità di gestire i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9c576-130">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="9c576-131">Se si desidera, è possibile controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9c576-131">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="9c576-132">Se tuttavia si decide di non controllare in modo esplicito i prefissi, durante la serializzazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] assegnerà i prefissi di spazio dei nomi se sono necessari oppure eseguirà la serializzazione usando spazi dei nomi predefiniti, se non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="9c576-132">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="9c576-133">Se vengono utilizzati gli spazi dei nomi predefiniti, il documento risultante non conterrà prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9c576-133">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="9c576-134">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9c576-134">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="9c576-135">Un altro problema di DOM è che non consente di modificare il nome di un nodo.</span><span class="sxs-lookup"><span data-stu-id="9c576-135">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="9c576-136">È invece necessario creare un nuovo nodo e copiarvi tutti i nodi figlio, perdendo l'identità del nodo originale.</span><span class="sxs-lookup"><span data-stu-id="9c576-136">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> <span data-ttu-id="9c576-137">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo problema viene evitato grazie alla possibilità di impostare la proprietà <xref:System.Xml.Linq.XName> in un nodo.</span><span class="sxs-lookup"><span data-stu-id="9c576-137">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="9c576-138">Supporto dei metodi statici per il caricamento di XML</span><span class="sxs-lookup"><span data-stu-id="9c576-138">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9c576-139">consente di caricare XML usando metodi statici anziché metodi di istanza,</span><span class="sxs-lookup"><span data-stu-id="9c576-139">lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="9c576-140">semplificando le operazioni di caricamento e analisi.</span><span class="sxs-lookup"><span data-stu-id="9c576-140">This simplifies loading and parsing.</span></span> <span data-ttu-id="9c576-141">Per ulteriori informazioni, vedere [come caricare XML da un file (C#)](./how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="9c576-141">For more information, see [How to load XML from a file (C#)](./how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="9c576-142">Rimozione del supporto per i costrutti DTD</span><span class="sxs-lookup"><span data-stu-id="9c576-142">Removal of Support for DTD Constructs</span></span>  
 <span data-ttu-id="9c576-143">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] la programmazione XML risulta ulteriormente semplificata tramite la rimozione del supporto per entità e riferimenti di entità.</span><span class="sxs-lookup"><span data-stu-id="9c576-143">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="9c576-144">Oltre a essere complessa, la gestione di entità viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="9c576-144">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="9c576-145">Rimuovendone il supporto è possibile riscontrare un aumento delle prestazioni e un'interfaccia di programmazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="9c576-145">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="9c576-146">Quando un albero [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene popolato, tutte le entità DTD vengono espanse.</span><span class="sxs-lookup"><span data-stu-id="9c576-146">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="9c576-147">Supporto per i frammenti</span><span class="sxs-lookup"><span data-stu-id="9c576-147">Support for Fragments</span></span>  
 <span data-ttu-id="9c576-148">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] non sono disponibili equivalenti per la classe `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="9c576-148">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="9c576-149">In molti casi, tuttavia, il concetto di `XmlDocumentFragment` può essere gestito dal risultato di una query digitato come <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XNode> o <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9c576-149">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="9c576-150">Supporto per XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="9c576-150">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9c576-151">supporta <xref:System.Xml.XPath.XPathNavigator> tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c576-151">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="9c576-152">Per altre informazioni, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c576-152">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="9c576-153">Supporto per lo spazio vuoto e il rientro</span><span class="sxs-lookup"><span data-stu-id="9c576-153">Support for White Space and Indentation</span></span>  
 <span data-ttu-id="9c576-154">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene gestito più agevolmente rispetto a DOM.</span><span class="sxs-lookup"><span data-stu-id="9c576-154">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="9c576-155">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="9c576-155">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="9c576-156">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="9c576-156">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="9c576-157">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c576-157">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="9c576-158">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="9c576-158">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="9c576-159">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="9c576-159">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="9c576-160">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="9c576-160">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="9c576-161">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene archiviato come nodo <xref:System.Xml.Linq.XText>, anziché con un nodo <xref:System.Xml.XmlNodeType.Whitespace> speciale, come invece avviene in DOM.</span><span class="sxs-lookup"><span data-stu-id="9c576-161">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="9c576-162">Supporto per le annotazioni</span><span class="sxs-lookup"><span data-stu-id="9c576-162">Support for Annotations</span></span>  
 <span data-ttu-id="9c576-163">Gli elementi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supportano un set estensibile di annotazioni.</span><span class="sxs-lookup"><span data-stu-id="9c576-163">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] elements support an extensible set of annotations.</span></span> <span data-ttu-id="9c576-164">Questa funzione è utile per tenere traccia di varie informazioni su un elemento, ad esempio informazioni sullo schema, informazioni su se l'elemento è associato a un'interfaccia utente o altri tipi di informazioni specifiche dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9c576-164">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="9c576-165">Per altre informazioni, vedere [Annotazioni LINQ to XML](./linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="9c576-165">For more information, see [LINQ to XML Annotations](./linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="9c576-166">Supporto per le informazioni sullo schema</span><span class="sxs-lookup"><span data-stu-id="9c576-166">Support for Schema Information</span></span>  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9c576-167">supporta la convalida XSD tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c576-167">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="9c576-168">È possibile verificare che un albero XML sia conforme a un XSD.</span><span class="sxs-lookup"><span data-stu-id="9c576-168">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="9c576-169">È possibile popolare l'albero XML con le informazioni sulla convalida post-schema.</span><span class="sxs-lookup"><span data-stu-id="9c576-169">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="9c576-170">Per ulteriori informazioni, vedere [come eseguire la convalida utilizzando XSD](./how-to-validate-using-xsd-linq-to-xml.md) e <xref:System.Xml.Schema.Extensions> .</span><span class="sxs-lookup"><span data-stu-id="9c576-170">For more information, see [How to validate using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c576-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c576-171">See also</span></span>

- [<span data-ttu-id="9c576-172">Introduzione (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="9c576-172">Getting Started (LINQ to XML)</span></span>](./linq-to-xml-overview.md)
