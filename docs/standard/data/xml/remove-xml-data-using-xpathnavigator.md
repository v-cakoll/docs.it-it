---
title: Rimozione di dati XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: 062a98a9cc10e6be00f165cf617de2d92d65acbf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710362"
---
# <a name="remove-xml-data-using-xpathnavigator"></a><span data-ttu-id="a827f-102">Rimozione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a827f-102">Remove XML Data using XPathNavigator</span></span>
<span data-ttu-id="a827f-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce un set di metodi usati per rimuovere nodi e valori da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a827f-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="a827f-104">Per usare questi metodi, è necessario che l'oggetto <xref:System.Xml.XPath.XPathNavigator> sia modificabile, ovvero, la relativa proprietà <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> deve essere `true`.</span><span class="sxs-lookup"><span data-stu-id="a827f-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="a827f-105">Gli oggetti <xref:System.Xml.XPath.XPathNavigator> che possono modificare un documento XML vengono creati dal metodo <xref:System.Xml.XmlDocument.CreateNavigator%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a827f-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="a827f-106">Gli oggetti <xref:System.Xml.XPath.XPathNavigator> creati dalla classe <xref:System.Xml.XPath.XPathDocument> sono di sola lettura e qualsiasi tentativo di usare i metodi di modifica di un oggetto <xref:System.Xml.XPath.XPathNavigator> creato da un oggetto <xref:System.Xml.XPath.XPathDocument> genererà un oggetto <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="a827f-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="a827f-107">Per altre informazioni sulla creazioni di oggetti <xref:System.Xml.XPath.XPathNavigator> modificabili, vedere [Lettura di dati XML con XPathDocument e XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="a827f-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="removing-nodes"></a><span data-ttu-id="a827f-108">Rimozione di nodi</span><span class="sxs-lookup"><span data-stu-id="a827f-108">Removing Nodes</span></span>  
 <span data-ttu-id="a827f-109">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> per rimuovere nodi da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a827f-109">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to remove nodes from an XML document.</span></span>  
  
### <a name="removing-a-node"></a><span data-ttu-id="a827f-110">Rimozione di un nodo</span><span class="sxs-lookup"><span data-stu-id="a827f-110">Removing a Node</span></span>  
 <span data-ttu-id="a827f-111">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> per eliminare da un documento XML il nodo corrente su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a827f-111">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to delete the current node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on from an XML document.</span></span>  
  
 <span data-ttu-id="a827f-112">Dopo che un nodo è stato eliminato usando il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, non è più possibile raggiungerlo dal livello radice dell'oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a827f-112">After a node has been deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method, it is no longer reachable from the root of the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="a827f-113">Dopo che un nodo è stato eliminato, la classe <xref:System.Xml.XPath.XPathNavigator> viene posizionata sul nodo padre del nodo eliminato.</span><span class="sxs-lookup"><span data-stu-id="a827f-113">After a node has been deleted, the <xref:System.Xml.XPath.XPathNavigator> is positioned on the parent node of the deleted node.</span></span>  
  
 <span data-ttu-id="a827f-114">Un'operazione di eliminazione non influenza la posizione di un oggetto <xref:System.Xml.XPath.XPathNavigator> collocato sul nodo eliminato.</span><span class="sxs-lookup"><span data-stu-id="a827f-114">A delete operation doesn't affect the position of any <xref:System.Xml.XPath.XPathNavigator> object positioned on the deleted node.</span></span> <span data-ttu-id="a827f-115">Questi oggetti <xref:System.Xml.XPath.XPathNavigator> sono validi nel senso che è possibile spostarli all'interno del sottoalbero eliminato ma non è possibile spostarli nell'albero principale dei nodi usando i normali metodi di navigazione dei set di nodi della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a827f-115">These <xref:System.Xml.XPath.XPathNavigator> objects are valid in the sense that they can move within the deleted subtree, but cannot be moved to the main node tree using the regular node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a827f-116">È possibile usare il metodo <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> della classe <xref:System.Xml.XPath.XPathNavigator> per riportare questi oggetti <xref:System.Xml.XPath.XPathNavigator> nell'albero principale dei nodi o per spostarli dall'albero principale al sottoalbero eliminato.</span><span class="sxs-lookup"><span data-stu-id="a827f-116">The <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class can be used to move these <xref:System.Xml.XPath.XPathNavigator> objects back into the main node tree, or from the main node tree to the deleted subtree.</span></span>  
  
 <span data-ttu-id="a827f-117">Nell'esempio seguente l'elemento `price` del primo elemento `book` del file `contosoBooks.xml` viene eliminato usando il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="a827f-117">In the following example, the `price` element of the first `book` element of the `contosoBooks.xml` file is deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span> <span data-ttu-id="a827f-118">Dopo che l'elemento <xref:System.Xml.XPath.XPathNavigator> è stato eliminato, l'oggetto `price` è posizionato sull'elemento padre `book`.</span><span class="sxs-lookup"><span data-stu-id="a827f-118">The position of the <xref:System.Xml.XPath.XPathNavigator> object after the `price` element is deleted is on the parent `book` element.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="a827f-119">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="a827f-119">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a><span data-ttu-id="a827f-120">Rimozione di un nodo Attribute</span><span class="sxs-lookup"><span data-stu-id="a827f-120">Removing an Attribute Node</span></span>  
 <span data-ttu-id="a827f-121">I nodi Attribute vengono rimossi da un documento XML usando il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="a827f-121">Attribute nodes are removed from an XML document using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span>  
  
 <span data-ttu-id="a827f-122">Dopo che un nodo Attribute è stato eliminato, non è più possibile raggiungerlo dal nodo radice di un oggetto <xref:System.Xml.XmlDocument> e l'oggetto <xref:System.Xml.XPath.XPathNavigator> viene posizionato sull'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="a827f-122">After an attribute node has been deleted, it is no longer reachable from the root node of an <xref:System.Xml.XmlDocument> object and the <xref:System.Xml.XPath.XPathNavigator> object is positioned on the parent element.</span></span>  
  
#### <a name="default-attributes"></a><span data-ttu-id="a827f-123">Attributi predefiniti</span><span class="sxs-lookup"><span data-stu-id="a827f-123">Default Attributes</span></span>  
 <span data-ttu-id="a827f-124">Indipendentemente dal metodo usato per rimuovere gli attributi, la rimozione di attributi definiti come attributi predefiniti nella DTD o in XML Schema per il documento XML è soggetta ad alcuni limiti specifici.</span><span class="sxs-lookup"><span data-stu-id="a827f-124">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the DTD or XML Schema for the XML document.</span></span> <span data-ttu-id="a827f-125">Non è possibile rimuovere gli attributi predefiniti, a meno che non venga rimosso anche l'elemento al quale appartengono.</span><span class="sxs-lookup"><span data-stu-id="a827f-125">Default attributes cannot be removed unless the element they belong to is also removed.</span></span> <span data-ttu-id="a827f-126">Gli attributi predefiniti sono sempre presenti per gli elementi con attributi predefiniti dichiarati. Di conseguenza, l'eliminazione di un attributo predefinito determina l'inserimento di un attributo di sostituzione nell'elemento e la relativa inizializzazione in base al valore predefinito che era stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="a827f-126">Default attributes are always present for elements that have default attributes declared, and as a result, deleting a default attribute results in a replacement attribute being inserted into the element and initialized to the default value that was declared.</span></span>  
  
## <a name="removing-values"></a><span data-ttu-id="a827f-127">Rimozione di valore</span><span class="sxs-lookup"><span data-stu-id="a827f-127">Removing Values</span></span>  
 <span data-ttu-id="a827f-128">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i metodi <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> e <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> per rimuovere valori tipizzati e non tipizzati da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a827f-128">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to remove untyped and typed values from an XML document.</span></span>  
  
### <a name="removing-untyped-values"></a><span data-ttu-id="a827f-129">Rimozione di valori non tipizzati</span><span class="sxs-lookup"><span data-stu-id="a827f-129">Removing Untyped Values</span></span>  
 <span data-ttu-id="a827f-130">Il metodo <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> consente semplicemente di inserire il valore non tipizzato `string`, passato come parametro, come valore del nodo su cui è attualmente posizionato l'oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a827f-130">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="a827f-131">Il passaggio di una stringa vuota al metodo <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> causa la rimozione del valore del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="a827f-131">Passing an empty string to the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method removes the value of the current node.</span></span>  
  
 <span data-ttu-id="a827f-132">Nell'esempio seguente il valore dell'elemento `price` del primo elemento `book` del file `contosoBooks.xml` viene rimosso usando il metodo <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="a827f-132">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="a827f-133">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="a827f-133">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a><span data-ttu-id="a827f-134">Rimozione di valori tipizzati</span><span class="sxs-lookup"><span data-stu-id="a827f-134">Removing Typed Values</span></span>  
 <span data-ttu-id="a827f-135">Quando il tipo di un nodo è un tipo semplice di W3C XML Schema, il nuovo valore inserito tramite il metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> viene controllato rispetto ai facet del tipo semplice prima dell'impostazione del valore.</span><span class="sxs-lookup"><span data-stu-id="a827f-135">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="a827f-136">Se il nuovo valore non è valido in base al tipo del nodo (ad esempio, l'impostazione di un valore `-1` su un elemento il cui tipo è `xs:positiveInteger`), viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a827f-136">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span> <span data-ttu-id="a827f-137">Anche al metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> non può essere passato il valore `null` come parametro.</span><span class="sxs-lookup"><span data-stu-id="a827f-137">The <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method also cannot be passed `null` as a parameter.</span></span> <span data-ttu-id="a827f-138">Di conseguenza la rimozione del valore di un nodo tipizzato deve essere conforme al tipo di schema del nodo.</span><span class="sxs-lookup"><span data-stu-id="a827f-138">As a result removing the value of a typed node must comply with the schema type of the node.</span></span>  
  
 <span data-ttu-id="a827f-139">Nell'esempio seguente il valore dell'elemento `price` del primo elemento `book` del file `contosoBooks.xml` viene rimosso usando il metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, impostando il valore su `0`.</span><span class="sxs-lookup"><span data-stu-id="a827f-139">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method by setting the value to `0`.</span></span> <span data-ttu-id="a827f-140">Il valore del nodo non viene rimosso, ma il prezzo del libro è stato rimosso in base al relativo tipo di dati `xs:decimal`.</span><span class="sxs-lookup"><span data-stu-id="a827f-140">The value of the node is not removed, but the price of the book has been removed according to its data type of `xs:decimal`.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a><span data-ttu-id="a827f-141">Nodi dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a827f-141">Namespace Nodes</span></span>  
 <span data-ttu-id="a827f-142">Non è possibile eliminare i nodi dello spazio dei nomi da un oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a827f-142">Namespace nodes cannot be deleted from an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="a827f-143">I tentativi di eliminare i nodi dello spazio dei nomi usando il metodo <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a827f-143">Attempts to delete namespace nodes using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method results in an exception.</span></span>  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="a827f-144">Proprietà InnerXml e OuterXml</span><span class="sxs-lookup"><span data-stu-id="a827f-144">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="a827f-145">Le proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> della classe <xref:System.Xml.XPath.XPathNavigator> consentono di modificare il markup XML dei nodi su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a827f-145">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="a827f-146">La proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> consente di modificare il markup XML dei nodi figlio su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator> con il contenuto analizzato della `string` XML specificata.</span><span class="sxs-lookup"><span data-stu-id="a827f-146">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="a827f-147">Allo stesso modo, la proprietà <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> consente di modificare il markup XML dei nodi figlio su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator> nonché il nodo corrente stesso.</span><span class="sxs-lookup"><span data-stu-id="a827f-147">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="a827f-148">Oltre ai metodi descritti in questo argomento, è possibile usare le proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> per rimuovere nodi e valori da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a827f-148">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="a827f-149">Per altre informazioni sull'utilizzo delle proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> per modificare i nodi, vedere l'argomento [Modificare i dati XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="a827f-149">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to modify nodes, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="a827f-150">Salvataggio di un documento XML</span><span class="sxs-lookup"><span data-stu-id="a827f-150">Saving an XML Document</span></span>  
 <span data-ttu-id="a827f-151">Il salvataggio delle modifiche apportate a un oggetto <xref:System.Xml.XmlDocument> mediante i metodi descritti in questo argomento viene eseguito usando i metodi della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a827f-151">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="a827f-152">Per altre informazioni sul salvataggio delle modifiche apportate a un oggetto <xref:System.Xml.XmlDocument>, vedere [Salvataggio e scrittura di un documento](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="a827f-152">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a827f-153">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a827f-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="a827f-154">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="a827f-154">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="a827f-155">Inserimento dei dati XML utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a827f-155">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="a827f-156">Modifica dei dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a827f-156">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
