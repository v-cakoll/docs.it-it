---
title: Selezione di nodi utilizzando la navigazione XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 8f4136683f13a52b84ab9e8bfd69f30c8914e029
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710180"
---
# <a name="select-nodes-using-xpath-navigation"></a><span data-ttu-id="d00dc-102">Selezione di nodi utilizzando la navigazione XPath</span><span class="sxs-lookup"><span data-stu-id="d00dc-102">Select Nodes Using XPath Navigation</span></span>
<span data-ttu-id="d00dc-103">Il DOM (Document Object Model) XML contiene metodi che consentono di usare la navigazione XPath (XML Path Language) per eseguire query sulle informazioni del DOM.</span><span class="sxs-lookup"><span data-stu-id="d00dc-103">The XML Document Object Model (DOM) contains methods that allow you to use XML Path Language (XPath) navigation to query information in the DOM.</span></span> <span data-ttu-id="d00dc-104">È possibile usare XPath per individuare un singolo nodo specifico o tutti i nodi che corrispondono a certi criteri.</span><span class="sxs-lookup"><span data-stu-id="d00dc-104">You can use XPath to find a single, specific node or to find all nodes that match some criteria.</span></span>  
  
## <a name="xpath-select-methods"></a><span data-ttu-id="d00dc-105">Metodi di selezione XPath</span><span class="sxs-lookup"><span data-stu-id="d00dc-105">XPath Select Methods</span></span>  
 <span data-ttu-id="d00dc-106">Le classi DOM forniscono due metodi per la selezione XPath: il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> e il metodo <xref:System.Xml.XmlNode.SelectNodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="d00dc-106">The DOM classes provide two methods for XPath selection: the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method and the <xref:System.Xml.XmlNode.SelectNodes%2A> method.</span></span> <span data-ttu-id="d00dc-107">Il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> restituisce il primo nodo che corrisponde ai criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="d00dc-107">The <xref:System.Xml.XmlNode.SelectSingleNode%2A> method returns the first node that matches the selection criteria.</span></span> <span data-ttu-id="d00dc-108">Il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> restituisce un oggetto <xref:System.Xml.XmlNodeList> contenente i nodi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d00dc-108">The <xref:System.Xml.XmlNode.SelectNodes%2A> method returns an <xref:System.Xml.XmlNodeList> that contains the matching nodes.</span></span>  
  
 <span data-ttu-id="d00dc-109">Nell'esempio seguente viene usato il metodo <xref:System.Xml.XmlNode.SelectSingleNode%2A> per selezionare il primo nodo `book` nel quale il cognome dell'autore soddisfa i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="d00dc-109">The following example uses the <xref:System.Xml.XmlNode.SelectSingleNode%2A> method to select the first `book` node in which the author's last name meets the specified criteria.</span></span> <span data-ttu-id="d00dc-110">Il file bookstore.xml, fornito alla fine di questo argomento, viene usato come file di input.</span><span class="sxs-lookup"><span data-stu-id="d00dc-110">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's   
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's   
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 <span data-ttu-id="d00dc-111">Nell'esempio successivo viene usato il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> per selezionare tutti i nodi libro in cui il prezzo è maggiore di una quantità specificata.</span><span class="sxs-lookup"><span data-stu-id="d00dc-111">The next example uses the <xref:System.Xml.XmlNode.SelectNodes%2A> method to select all the book nodes in which the price is greater than a specified amount.</span></span> <span data-ttu-id="d00dc-112">Il prezzo di ogni libro nell'elenco selezionato viene quindi ridotto a livello di codice del dieci percento.</span><span class="sxs-lookup"><span data-stu-id="d00dc-112">The price for each book in the selected list is then programmatically reduced by ten percent.</span></span> <span data-ttu-id="d00dc-113">Infine, il file aggiornato viene scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="d00dc-113">Finally, the updated file is written to the console.</span></span> <span data-ttu-id="d00dc-114">Il file bookstore.xml, fornito alla fine di questo argomento, viene usato come file di input.</span><span class="sxs-lookup"><span data-stu-id="d00dc-114">The bookstore.xml file (which is provided at the end of this topic) is used as the input file.</span></span>  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 <span data-ttu-id="d00dc-115">Negli esempi precedenti la query XPath inizia dall'elemento del documento.</span><span class="sxs-lookup"><span data-stu-id="d00dc-115">The examples above start the XPath query at the document element.</span></span> <span data-ttu-id="d00dc-116">Impostando il punto iniziale per la query XPath si imposta il nodo di contesto, che è il punto da cui inizia la query XPath.</span><span class="sxs-lookup"><span data-stu-id="d00dc-116">Setting the starting point for the XPath query sets the context node, which is the starting point for the XPath query.</span></span> <span data-ttu-id="d00dc-117">Se non si desidera iniziare dall'elemento del documento, ma dal primo elemento figlio di tale elemento, è possibile codificare l'istruzione Select come segue:</span><span class="sxs-lookup"><span data-stu-id="d00dc-117">If you do not want to start at the document element, but want to start from the first child of the document element, you can code the select statement as follows:</span></span>  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 <span data-ttu-id="d00dc-118">Tutti gli oggetti <xref:System.Xml.XmlNodeList> sono sincronizzati con il documento sottostante.</span><span class="sxs-lookup"><span data-stu-id="d00dc-118">All <xref:System.Xml.XmlNodeList> objects are synchronized with the underlying document.</span></span> <span data-ttu-id="d00dc-119">Per questo motivo, se si scorre l'elenco dei nodi e si modifica il valore di un nodo, quest'ultimo verrà aggiornato anche nel documento dal quale proviene.</span><span class="sxs-lookup"><span data-stu-id="d00dc-119">Therefore, if you iterate through the node list and modify the value of a node, that node is also updated in the document it came from.</span></span> <span data-ttu-id="d00dc-120">Si noti nell'esempio precedente che quando un nodo viene modificato nell'oggetto <xref:System.Xml.XmlNodeList> selezionato, viene modificato anche il documento sottostante.</span><span class="sxs-lookup"><span data-stu-id="d00dc-120">Notice in the previous example that when a node is modified in the selected <xref:System.Xml.XmlNodeList> the underlying document is also modified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d00dc-121">Quando si modifica il documento sottostante, è consigliabile eseguire nuovamente la selezione.</span><span class="sxs-lookup"><span data-stu-id="d00dc-121">When the underlying document is modified, it is advisable to rerun the select.</span></span> <span data-ttu-id="d00dc-122">Se il nodo modificato è un nodo che potrebbe causare l'aggiunta del nodo all'elenco dove non figurava in precedenza o la relativa rimozione dall'elenco di nodi, è possibile che tale elenco non sia preciso.</span><span class="sxs-lookup"><span data-stu-id="d00dc-122">If the node modified is one that could cause the node to be added to the node list when it was not previously, or would now cause it to be removed from the node list, there is no guarantee that the node list is now accurate.</span></span>  
  
## <a name="namespaces-in-xpath-expressions"></a><span data-ttu-id="d00dc-123">Spazi dei nomi nelle espressioni XPath</span><span class="sxs-lookup"><span data-stu-id="d00dc-123">Namespaces in XPath Expressions</span></span>  
 <span data-ttu-id="d00dc-124">Le espressioni XPath possono includere spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d00dc-124">XPath expressions can include namespaces.</span></span> <span data-ttu-id="d00dc-125">La risoluzione dello spazio dei nomi viene supportata usando il tipo <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="d00dc-125">Namespace resolution is supported using the <xref:System.Xml.XmlNamespaceManager>.</span></span> <span data-ttu-id="d00dc-126">Se l'espressione XPath include un prefisso, sarà necessario aggiungere la coppia costituita dal prefisso e dall'URI dello spazio dei nomi all'oggetto <xref:System.Xml.XmlNamespaceManager> e l'oggetto <xref:System.Xml.XmlNamespaceManager> verrà passato al metodo <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> o <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>.</span><span class="sxs-lookup"><span data-stu-id="d00dc-126">If the XPath expression includes a prefix, the prefix and namespace URI pair must be added to the <xref:System.Xml.XmlNamespaceManager>, and the <xref:System.Xml.XmlNamespaceManager> is passed to the <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> or <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29> method.</span></span> <span data-ttu-id="d00dc-127">Si noti che negli esempi di codice precedenti viene usato l'oggetto <xref:System.Xml.XmlNamespaceManager> per risolvere lo spazio dei nomi del documento bookstore.xml.</span><span class="sxs-lookup"><span data-stu-id="d00dc-127">Notice that the code examples above use the <xref:System.Xml.XmlNamespaceManager> to resolve the namespace of the bookstore.xml document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d00dc-128">Se l'espressione XPath non include un prefisso, si presuppone che l'URI dello spazio dei nomi (Uniform Resource Identifier) sia lo spazio dei nomi vuoto.</span><span class="sxs-lookup"><span data-stu-id="d00dc-128">If the XPath expression does not include a prefix, it is assumed that the namespace Uniform Resource Identifier (URI) is the empty namespace.</span></span> <span data-ttu-id="d00dc-129">Se l'XML include uno spazio dei nomi predefinito, sarà necessario aggiungere un prefisso e un URI dello spazio dei nomi anche all'oggetto <xref:System.Xml.XmlNamespaceManager>. In caso contrario, non verrà selezionato alcun nodo.</span><span class="sxs-lookup"><span data-stu-id="d00dc-129">If your XML includes a default namespace, you must still add a prefix and namespace URI to the <xref:System.Xml.XmlNamespaceManager>; otherwise, no nodes will be selected.</span></span>  
  
#### <a name="input-file"></a><span data-ttu-id="d00dc-130">File di input</span><span class="sxs-lookup"><span data-stu-id="d00dc-130">Input File</span></span>  
 <span data-ttu-id="d00dc-131">Di seguito è riportato il file bookstore.xml usato come file di input negli esempi di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="d00dc-131">The following is the bookstore.xml file that is used as the input file in the examples in this topic:</span></span>  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d00dc-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d00dc-132">See also</span></span>

- [<span data-ttu-id="d00dc-133">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="d00dc-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
