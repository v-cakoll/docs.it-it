---
title: Estrazione di dati XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: e639931204a416c3cde87044730364a4f387799a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287766"
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="a081f-102">Estrazione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a081f-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="a081f-103">Sono disponibili diversi metodi per rappresentare un documento XML in Microsoft .NET Framework,</span><span class="sxs-lookup"><span data-stu-id="a081f-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="a081f-104">inclusi l'uso di una classe <xref:System.String> o l'uso delle classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="a081f-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="a081f-105">Per facilitare lo spostamento tra queste diverse rappresentazioni di un documento XML, la classe <xref:System.Xml.XPath.XPathNavigator> offre una serie di metodi e proprietà per estrarre i dati XML come oggetto <xref:System.String>, <xref:System.Xml.XmlReader> o come oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a081f-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="a081f-106">Conversione di un XPathNavigator in stringa</span><span class="sxs-lookup"><span data-stu-id="a081f-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="a081f-107">‎La proprietà <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> della classe <xref:System.Xml.XPath.XPathNavigator> viene usata per ottenere il markup dell'intero documento XML o di un singolo nodo e dei relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="a081f-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a081f-108">La proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> ottiene solo il markup dei nodi figlio di un nodo.</span><span class="sxs-lookup"><span data-stu-id="a081f-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="a081f-109">Nell'esempio di codice seguente viene illustrato come salvare un intero documento XML contenuto in un oggetto <xref:System.Xml.XPath.XPathNavigator> come <xref:System.String>, sotto forma di nodo singolo assieme ai relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="a081f-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="a081f-110">Conversione di un XPathNavigator in XmlReader</span><span class="sxs-lookup"><span data-stu-id="a081f-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="a081f-111">Il metodo <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> viene usato per inviare il flusso dell'intero contenuto di un documento XML o solo di un singolo nodo e dei relativi nodi figlio a un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a081f-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="a081f-112">Quando viene creato l'oggetto <xref:System.Xml.XmlReader> con il nodo corrente e i relativi nodi figlio, la proprietà <xref:System.Xml.XmlReader> dell'oggetto <xref:System.Xml.XmlReader.ReadState%2A> viene impostata su <xref:System.Xml.ReadState.Initial>.</span><span class="sxs-lookup"><span data-stu-id="a081f-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="a081f-113">Quando il metodo <xref:System.Xml.XmlReader> dell'oggetto <xref:System.Xml.XmlReader.Read%2A> viene chiamato la prima volta, l'oggetto <xref:System.Xml.XmlReader> viene spostato sul nodo corrente dell'oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a081f-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="a081f-114">Il nuovo oggetto <xref:System.Xml.XmlReader> prosegue la lettura fino a quando non viene raggiunta la fine dell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="a081f-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="a081f-115">A questo punto il metodo <xref:System.Xml.XmlReader.Read%2A> restituisce `false` e la proprietà <xref:System.Xml.XmlReader> dell'oggetto <xref:System.Xml.XmlReader.ReadState%2A> viene impostata su <xref:System.Xml.ReadState.EndOfFile>.</span><span class="sxs-lookup"><span data-stu-id="a081f-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="a081f-116">La posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator> non è stata modificata dalla creazione o dallo spostamento dell'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a081f-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="a081f-117">Il metodo <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> è valido solo se è posizionato in corrispondenza di un elemento o di un nodo radice.</span><span class="sxs-lookup"><span data-stu-id="a081f-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="a081f-118">Nell'esempio di codice seguente viene illustrato come ottenere un oggetto <xref:System.Xml.XmlReader> contenente l'intero documento XML contenuto in un oggetto <xref:System.Xml.XPath.XPathDocument> sotto forma di nodo singolo assieme ai relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="a081f-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="a081f-119">Nell'esempio il file `books.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="a081f-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="a081f-120">Conversione di un XPathNavigator in XmlWriter</span><span class="sxs-lookup"><span data-stu-id="a081f-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="a081f-121">Il metodo <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> viene usato per inviare il flusso dell'intero contenuto di un documento XML o solo di un singolo nodo e dei relativi nodi figlio a un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a081f-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a081f-122">La posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator> non è stata modificata dalla creazione dell'oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a081f-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a081f-123">Nell'esempio di codice seguente viene illustrato come ottenere un oggetto <xref:System.Xml.XmlWriter> contenente l'intero documento XML contenuto in un oggetto <xref:System.Xml.XPath.XPathDocument> sotto forma di nodo singolo assieme ai relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="a081f-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="a081f-124">Nell'esempio il file `books.xml`, trovato prima in questo argomento, viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="a081f-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a081f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a081f-125">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="a081f-126">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="a081f-126">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="a081f-127">Navigazione del set di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a081f-127">Node Set Navigation Using XPathNavigator</span></span>](node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="a081f-128">Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a081f-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="a081f-129">Accesso a dati XML fortemente tipizzati con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a081f-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
