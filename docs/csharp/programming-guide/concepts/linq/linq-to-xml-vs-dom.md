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
# <a name="linq-to-xml-vs-dom-c"></a><span data-ttu-id="da30b-102">LINQ to XML rispetto a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="da30b-102">LINQ to XML vs. DOM (C#)</span></span>
<span data-ttu-id="da30b-103">Questa sezione descrive alcune delle differenze principali tra [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] e l'API di programmazione XML attualmente più diffusa, ovvero DOM (Document Object Model) W3C.</span><span class="sxs-lookup"><span data-stu-id="da30b-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="da30b-104">Nuove modalità di creazione degli alberi XML</span><span class="sxs-lookup"><span data-stu-id="da30b-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="da30b-105">In W3C DOM un albero XML viene compilata dal basso verso l'alto, ossia si crea un documento, si creano gli elementi e quindi si aggiungono gli elementi al documento.</span><span class="sxs-lookup"><span data-stu-id="da30b-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="da30b-106">Ad esempio, di seguito viene illustrata la creazione di un tipico albero XML tramite l'implementazione Microsoft di DOM, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="da30b-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
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
  
 <span data-ttu-id="da30b-107">Questo stile di codifica non fornisce molte informazioni visive sulla struttura dell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> <span data-ttu-id="da30b-108">Oltre a questo approccio di creazione di un albero, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supporta un approccio alternativo, la *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="da30b-108">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="da30b-109">Nella costruzione funzionale vengono usati i costruttori <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute> per compilare un albero XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-109">Functional construction uses the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors to build an XML tree.</span></span>  
  
 <span data-ttu-id="da30b-110">Di seguito è illustrata la creazione dello stesso albero XML tramite la costruzione funzionale di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="da30b-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
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
  
 <span data-ttu-id="da30b-111">Si noti che il rientro del codice per costruire la struttura ad albero XML illustra la struttura dell'XML sottostante.</span><span class="sxs-lookup"><span data-stu-id="da30b-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="da30b-112">Per altre informazioni, vedere [Creazione di alberi XML (C#)](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da30b-112">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="da30b-113">Utilizzo diretto di elementi XML</span><span class="sxs-lookup"><span data-stu-id="da30b-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="da30b-114">Quando si programma con XML, l'obiettivo principale riguarda in genere gli elementi XML e talvolta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="da30b-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="da30b-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile usare direttamente gli elementi e gli attributi XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="da30b-116">È ad esempio possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da30b-116">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="da30b-117">Creare elementi XML senza usare affatto un oggetto documento.</span><span class="sxs-lookup"><span data-stu-id="da30b-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="da30b-118">In questo modo la programmazione risulta semplificata quando è necessario usare frammenti di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="da30b-119">Caricare oggetti `T:System.Xml.Linq.XElement` direttamente da un file XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="da30b-120">Serializzare oggetti `T:System.Xml.Linq.XElement` a un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="da30b-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="da30b-121">Al contrario, in W3C DOM il documento XML viene usato come contenitore logico per l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="da30b-122">In DOM i nodi XML, inclusi elementi e attributi, devono essere creati nel contesto di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="da30b-123">Di seguito è riportato un frammento del codice usato per creare un elemento name in DOM:</span><span class="sxs-lookup"><span data-stu-id="da30b-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 <span data-ttu-id="da30b-124">Se si desidera usare un elemento in più documenti, è necessario importare i nodi tra documenti.</span><span class="sxs-lookup"><span data-stu-id="da30b-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> <span data-ttu-id="da30b-125">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo livello di complessità viene evitato.</span><span class="sxs-lookup"><span data-stu-id="da30b-125">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="da30b-126">Con LINQ to XML la classe <xref:System.Xml.Linq.XDocument> viene usata solo se si desidera aggiungere un commento o un'istruzione di elaborazione al livello radice del documento.</span><span class="sxs-lookup"><span data-stu-id="da30b-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="da30b-127">Gestione semplificata di nomi e spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="da30b-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="da30b-128">La gestione di nomi, spazi dei nomi e prefissi di spazio dei nomi è in genere un aspetto complesso della programmazione XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> <span data-ttu-id="da30b-129">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nomi e spazi dei nomi sono semplificati grazie all'eliminazione della necessità di gestire i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da30b-129">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="da30b-130">Se si desidera, è possibile controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da30b-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="da30b-131">Se tuttavia si decide di non controllare in modo esplicito i prefissi, durante la serializzazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] assegnerà i prefissi di spazio dei nomi se sono necessari oppure eseguirà la serializzazione usando spazi dei nomi predefiniti, se non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="da30b-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="da30b-132">Se vengono utilizzati gli spazi dei nomi predefiniti, il documento risultante non conterrà prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da30b-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="da30b-133">Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da30b-133">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="da30b-134">Un altro problema di DOM è che non consente di modificare il nome di un nodo.</span><span class="sxs-lookup"><span data-stu-id="da30b-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="da30b-135">È invece necessario creare un nuovo nodo e copiarvi tutti i nodi figlio, perdendo l'identità del nodo originale.</span><span class="sxs-lookup"><span data-stu-id="da30b-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> <span data-ttu-id="da30b-136">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo problema viene evitato grazie alla possibilità di impostare la proprietà <xref:System.Xml.Linq.XName> in un nodo.</span><span class="sxs-lookup"><span data-stu-id="da30b-136">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="da30b-137">Supporto dei metodi statici per il caricamento di XML</span><span class="sxs-lookup"><span data-stu-id="da30b-137">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="da30b-138">consente di caricare XML usando metodi statici anziché metodi di istanza,</span><span class="sxs-lookup"><span data-stu-id="da30b-138">lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="da30b-139">semplificando le operazioni di caricamento e analisi.</span><span class="sxs-lookup"><span data-stu-id="da30b-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="da30b-140">Per ulteriori informazioni, vedere [come caricare XML da un fileC#()](./how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="da30b-140">For more information, see [How to load XML from a file (C#)](./how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="da30b-141">Rimozione del supporto per i costrutti DTD</span><span class="sxs-lookup"><span data-stu-id="da30b-141">Removal of Support for DTD Constructs</span></span>  
 <span data-ttu-id="da30b-142">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] la programmazione XML risulta ulteriormente semplificata tramite la rimozione del supporto per entità e riferimenti di entità.</span><span class="sxs-lookup"><span data-stu-id="da30b-142">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="da30b-143">Oltre a essere complessa, la gestione di entità viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="da30b-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="da30b-144">Rimuovendone il supporto è possibile riscontrare un aumento delle prestazioni e un'interfaccia di programmazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="da30b-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="da30b-145">Quando un albero [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene popolato, tutte le entità DTD vengono espanse.</span><span class="sxs-lookup"><span data-stu-id="da30b-145">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="da30b-146">Supporto per i frammenti</span><span class="sxs-lookup"><span data-stu-id="da30b-146">Support for Fragments</span></span>  
 <span data-ttu-id="da30b-147">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] non sono disponibili equivalenti per la classe `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="da30b-147">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="da30b-148">In molti casi, tuttavia, il concetto di `XmlDocumentFragment` può essere gestito dal risultato di una query digitato come <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XNode> o <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="da30b-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="da30b-149">Supporto per XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="da30b-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="da30b-150">supporta <xref:System.Xml.XPath.XPathNavigator> tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da30b-150">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="da30b-151">Per ulteriori informazioni, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da30b-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="da30b-152">Supporto per lo spazio vuoto e il rientro</span><span class="sxs-lookup"><span data-stu-id="da30b-152">Support for White Space and Indentation</span></span>  
 <span data-ttu-id="da30b-153">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene gestito più agevolmente rispetto a DOM.</span><span class="sxs-lookup"><span data-stu-id="da30b-153">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="da30b-154">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="da30b-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="da30b-155">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="da30b-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="da30b-156">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da30b-156">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="da30b-157">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="da30b-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="da30b-158">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="da30b-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="da30b-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="da30b-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="da30b-160">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lo spazio vuoto viene archiviato come nodo <xref:System.Xml.Linq.XText>, anziché con un nodo <xref:System.Xml.XmlNodeType.Whitespace> speciale, come invece avviene in DOM.</span><span class="sxs-lookup"><span data-stu-id="da30b-160">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="da30b-161">Supporto per le annotazioni</span><span class="sxs-lookup"><span data-stu-id="da30b-161">Support for Annotations</span></span>  
 <span data-ttu-id="da30b-162">Gli elementi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supportano un set estensibile di annotazioni.</span><span class="sxs-lookup"><span data-stu-id="da30b-162">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] elements support an extensible set of annotations.</span></span> <span data-ttu-id="da30b-163">Questa funzione è utile per tenere traccia di varie informazioni su un elemento, ad esempio informazioni sullo schema, informazioni su se l'elemento è associato a un'interfaccia utente o altri tipi di informazioni specifiche dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da30b-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="da30b-164">Per altre informazioni, vedere [Annotazioni LINQ to XML](./linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="da30b-164">For more information, see [LINQ to XML Annotations](./linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="da30b-165">Supporto per le informazioni sullo schema</span><span class="sxs-lookup"><span data-stu-id="da30b-165">Support for Schema Information</span></span>  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="da30b-166">supporta la convalida XSD tramite i metodi di estensione nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da30b-166">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="da30b-167">È possibile verificare che un albero XML sia conforme a un XSD.</span><span class="sxs-lookup"><span data-stu-id="da30b-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="da30b-168">È possibile popolare l'albero XML con le informazioni sulla convalida post-schema.</span><span class="sxs-lookup"><span data-stu-id="da30b-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="da30b-169">Per ulteriori informazioni, vedere [How to Validate Using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span><span class="sxs-lookup"><span data-stu-id="da30b-169">For more information, see [How to validate using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da30b-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da30b-170">See also</span></span>

- [<span data-ttu-id="da30b-171">Introduzione (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="da30b-171">Getting Started (LINQ to XML)</span></span>](./linq-to-xml-overview.md)
