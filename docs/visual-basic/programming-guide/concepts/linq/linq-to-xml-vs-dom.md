---
title: LINQ to XML e DOM (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 18c36130-d598-40b7-9007-828232252978
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 73aef4ddf4b53297e31d9b8b763dc1cafbef5170
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-vs-dom-visual-basic"></a><span data-ttu-id="003ec-102">LINQ to XML e DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003ec-102">LINQ to XML vs. DOM (Visual Basic)</span></span>
<span data-ttu-id="003ec-103">In questa sezione vengono descritte alcune differenze fondamentali tra [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] e il XML attualmente più diffusa API di programmazione, il W3C Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="003ec-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="003ec-104">Nuove modalità di creazione degli alberi XML</span><span class="sxs-lookup"><span data-stu-id="003ec-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="003ec-105">In W3C DOM un albero XML viene compilata dal basso verso l'alto, ossia si crea un documento, si creano gli elementi e quindi si aggiungono gli elementi al documento.</span><span class="sxs-lookup"><span data-stu-id="003ec-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="003ec-106">Ad esempio, il seguente sarebbe normalmente per creare una struttura ad albero XML tramite l'implementazione Microsoft di DOM, <xref:System.Xml.XmlDocument>:</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="003ec-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 <span data-ttu-id="003ec-107">Questo stile di codifica non fornisce molte informazioni visive sulla struttura dell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-108">supporta questo approccio alla creazione di un albero XML, ma anche un approccio alternativo, *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="003ec-108"> supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="003ec-109">In Visual Basic, la costruzione funzionale utilizza valori letterali XML per compilare un albero XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-109">In Visual Basic, functional construction uses XML literals to build an XML tree.</span></span>  
  
 <span data-ttu-id="003ec-110">Di seguito è illustrata la creazione dello stesso albero XML utilizzando [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] costruzione funzionale:</span><span class="sxs-lookup"><span data-stu-id="003ec-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] functional construction:</span></span>  
  
```vb  
Dim contacts = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="Home">206-555-0144</Phone>  
            <Phone Type="Work">425-555-0145</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="003ec-111">Si noti che il rientro del codice per costruire la struttura ad albero XML illustra la struttura dell'XML sottostante.</span><span class="sxs-lookup"><span data-stu-id="003ec-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="003ec-112">Per ulteriori informazioni, vedere [la creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="003ec-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="003ec-113">Utilizzo diretto di elementi XML</span><span class="sxs-lookup"><span data-stu-id="003ec-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="003ec-114">Quando si programma con XML, l'obiettivo principale riguarda in genere gli elementi XML e talvolta gli attributi.</span><span class="sxs-lookup"><span data-stu-id="003ec-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="003ec-115">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è possibile usare direttamente gli elementi e gli attributi XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-115">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="003ec-116">Ad esempio, è possibile eseguire quanto le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="003ec-116">For example, you can do the following:</span></span>  
  
-   <span data-ttu-id="003ec-117">Creare elementi XML senza usare affatto un oggetto documento.</span><span class="sxs-lookup"><span data-stu-id="003ec-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="003ec-118">In questo modo la programmazione risulta semplificata quando è necessario usare frammenti di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
-   <span data-ttu-id="003ec-119">Caricare oggetti `T:System.Xml.Linq.XElement` direttamente da un file XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
-   <span data-ttu-id="003ec-120">Serializzare oggetti `T:System.Xml.Linq.XElement` a un file o un flusso.</span><span class="sxs-lookup"><span data-stu-id="003ec-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="003ec-121">Al contrario, in W3C DOM il documento XML viene usato come contenitore logico per l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="003ec-122">In DOM i nodi XML, inclusi elementi e attributi, devono essere creati nel contesto di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="003ec-123">Di seguito è riportato un frammento del codice usato per creare un elemento name in DOM:</span><span class="sxs-lookup"><span data-stu-id="003ec-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 <span data-ttu-id="003ec-124">Se si desidera usare un elemento in più documenti, è necessario importare i nodi tra documenti.</span><span class="sxs-lookup"><span data-stu-id="003ec-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-125">evita questo livello di complessità.</span><span class="sxs-lookup"><span data-stu-id="003ec-125"> avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="003ec-126">Quando si utilizza LINQ to XML, utilizzare la <xref:System.Xml.Linq.XDocument>classe solo se si desidera aggiungere un'istruzione di elaborazione o commento relativo al livello radice del documento.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="003ec-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="003ec-127">Gestione semplificata di nomi e spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="003ec-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="003ec-128">La gestione di nomi, spazi dei nomi e prefissi di spazio dei nomi è in genere un aspetto complesso della programmazione XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-129">semplifica e spazi dei nomi, eliminando la necessità di affrontare i prefissi dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="003ec-129"> simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="003ec-130">Se si desidera, è possibile controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="003ec-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="003ec-131">Se tuttavia si decide di non controllare in modo esplicito i prefissi dello spazio dei nomi, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] assegnerà i prefissi dello spazio dei nomi durante la serializzazione, se sono necessari oppure eseguirà la serializzazione utilizzando spazi dei nomi predefinito se non lo sono.</span><span class="sxs-lookup"><span data-stu-id="003ec-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="003ec-132">Se vengono utilizzati gli spazi dei nomi predefiniti, il documento risultante non conterrà prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="003ec-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="003ec-133">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="003ec-133">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="003ec-134">Un altro problema di DOM è che non consente di modificare il nome di un nodo.</span><span class="sxs-lookup"><span data-stu-id="003ec-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="003ec-135">È invece necessario creare un nuovo nodo e copiarvi tutti i nodi figlio, perdendo l'identità del nodo originale.</span><span class="sxs-lookup"><span data-stu-id="003ec-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-136">Per evitare questo problema consentendo di impostare il <xref:System.Xml.Linq.XName>proprietà su un nodo.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="003ec-136"> avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="003ec-137">Supporto dei metodi statici per il caricamento di XML</span><span class="sxs-lookup"><span data-stu-id="003ec-137">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-138">Consente di caricare XML usando metodi statici, anziché metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="003ec-138"> lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="003ec-139">semplificando le operazioni di caricamento e analisi.</span><span class="sxs-lookup"><span data-stu-id="003ec-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="003ec-140">Per ulteriori informazioni, vedere [procedura: caricamento di XML da un File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="003ec-140">For more information, see [How to: Load XML from a File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="003ec-141">Rimozione del supporto per i costrutti DTD</span><span class="sxs-lookup"><span data-stu-id="003ec-141">Removal of Support for DTD Constructs</span></span>  
 <span data-ttu-id="003ec-142">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] la programmazione XML risulta ulteriormente semplificata tramite la rimozione del supporto per entità e riferimenti di entità.</span><span class="sxs-lookup"><span data-stu-id="003ec-142">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="003ec-143">Oltre a essere complessa, la gestione di entità viene utilizzata raramente.</span><span class="sxs-lookup"><span data-stu-id="003ec-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="003ec-144">Rimuovendone il supporto è possibile riscontrare un aumento delle prestazioni e un'interfaccia di programmazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="003ec-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="003ec-145">Quando un [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] albero viene popolato, tutte le entità DTD vengono espanse.</span><span class="sxs-lookup"><span data-stu-id="003ec-145">When a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="003ec-146">Supporto per i frammenti</span><span class="sxs-lookup"><span data-stu-id="003ec-146">Support for Fragments</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-147">non fornisce un equivalente per la `XmlDocumentFragment` classe.</span><span class="sxs-lookup"><span data-stu-id="003ec-147"> does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="003ec-148">In molti casi, tuttavia, il `XmlDocumentFragment` concetto può essere gestito dal risultato di una query tipizzata come <xref:System.Collections.Generic.IEnumerable%601>di <xref:System.Xml.Linq.XNode>, o <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XNode> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="003ec-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="003ec-149">Supporto per XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="003ec-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-150">fornisce il supporto per <xref:System.Xml.XPath.XPathNavigator>tramite metodi di estensione di <xref:System.Xml.XPath?displayProperty=fullName>dello spazio dei nomi.</xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.XPath.XPathNavigator></span><span class="sxs-lookup"><span data-stu-id="003ec-150"> provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="003ec-151">Per ulteriori informazioni, vedere <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="003ec-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="003ec-152">Supporto per lo spazio vuoto e il rientro</span><span class="sxs-lookup"><span data-stu-id="003ec-152">Support for White Space and Indentation</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-153">spazio vuoto viene gestito più agevolmente rispetto a DOM.</span><span class="sxs-lookup"><span data-stu-id="003ec-153"> handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="003ec-154">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="003ec-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="003ec-155">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="003ec-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="003ec-156">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="003ec-156">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="003ec-157">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="003ec-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="003ec-158">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="003ec-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="003ec-159">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="003ec-159">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-160">spazio vuoto come viene archiviato un <xref:System.Xml.Linq.XText>nodo, anziché un specializzato <xref:System.Xml.XmlNodeType>tipo di nodo, come il DOM viene.</xref:System.Xml.XmlNodeType> </xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="003ec-160"> stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="003ec-161">Supporto per le annotazioni</span><span class="sxs-lookup"><span data-stu-id="003ec-161">Support for Annotations</span></span>  
 <span data-ttu-id="003ec-162">Gli elementi [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] supportano un set estensibile di annotazioni.</span><span class="sxs-lookup"><span data-stu-id="003ec-162">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] elements support an extensible set of annotations.</span></span> <span data-ttu-id="003ec-163">Questa funzione è utile per tenere traccia di varie informazioni su un elemento, ad esempio informazioni sullo schema, informazioni su se l'elemento è associato a un'interfaccia utente o altri tipi di informazioni specifiche dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="003ec-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="003ec-164">Per ulteriori informazioni, vedere [annotazioni LINQ to XML](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).</span><span class="sxs-lookup"><span data-stu-id="003ec-164">For more information, see [LINQ to XML Annotations](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="003ec-165">Supporto per le informazioni sullo schema</span><span class="sxs-lookup"><span data-stu-id="003ec-165">Support for Schema Information</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="003ec-166">fornisce il supporto per la convalida XSD tramite metodi di estensione di <xref:System.Xml.Schema?displayProperty=fullName>dello spazio dei nomi.</xref:System.Xml.Schema?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="003ec-166"> provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="003ec-167">È possibile verificare che un albero XML sia conforme a un XSD.</span><span class="sxs-lookup"><span data-stu-id="003ec-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="003ec-168">È possibile popolare l'albero XML con le informazioni sulla convalida post-schema.</span><span class="sxs-lookup"><span data-stu-id="003ec-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="003ec-169">Per ulteriori informazioni, vedere [procedura: convalidare XSD utilizzando](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) e <xref:System.Xml.Schema.Extensions>.</xref:System.Xml.Schema.Extensions></span><span class="sxs-lookup"><span data-stu-id="003ec-169">For more information, see [How to: Validate Using XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) and <xref:System.Xml.Schema.Extensions>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003ec-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="003ec-170">See Also</span></span>  
 [<span data-ttu-id="003ec-171">Introduzione (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="003ec-171">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
