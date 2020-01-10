---
title: Inserimento dei dati XML utilizzando XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 68c003467d837fe79d5e275968e47fa5dc3490cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710726"
---
# <a name="insert-xml-data-using-xpathnavigator"></a><span data-ttu-id="8c6f0-102">Inserimento dei dati XML utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8c6f0-102">Insert XML Data using XPathNavigator</span></span>
<span data-ttu-id="8c6f0-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce un set di metodi usati per inserire nodi di pari livello, nodi figlio e nodi Attribute in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="8c6f0-104">Per usare questi metodi, è necessario che l'oggetto <xref:System.Xml.XPath.XPathNavigator> sia modificabile, ovvero, la relativa proprietà <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> deve essere `true`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="8c6f0-105">Gli oggetti <xref:System.Xml.XPath.XPathNavigator> che possono modificare un documento XML vengono creati dal metodo <xref:System.Xml.XmlDocument.CreateNavigator%2A> della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="8c6f0-106">Gli oggetti <xref:System.Xml.XPath.XPathNavigator> creati dalla classe <xref:System.Xml.XPath.XPathDocument> sono di sola lettura e qualsiasi tentativo di usare i metodi di modifica di un oggetto <xref:System.Xml.XPath.XPathNavigator> creato da un oggetto <xref:System.Xml.XPath.XPathDocument> genererà un oggetto <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="8c6f0-107">Per altre informazioni sulla creazioni di oggetti <xref:System.Xml.XPath.XPathNavigator> modificabili, vedere [Lettura di dati XML con XPathDocument e XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="8c6f0-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="inserting-nodes"></a><span data-ttu-id="8c6f0-108">Inserimento di nodi</span><span class="sxs-lookup"><span data-stu-id="8c6f0-108">Inserting Nodes</span></span>  
 <span data-ttu-id="8c6f0-109">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i metodi per inserire nodi di pari livello, nodi figlio e nodi Attribute in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-109">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="8c6f0-110">Tali metodi consentono di inserire nodi e attributi in diverse posizioni in relazione alla posizione corrente di un oggetto <xref:System.Xml.XPath.XPathNavigator> e vengono descritti nelle seguenti sezioni.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-110">These methods allow you to insert nodes and attributes in different locations in relation to the current position of an <xref:System.Xml.XPath.XPathNavigator> object and are described in the following sections.</span></span>  
  
### <a name="inserting-sibling-nodes"></a><span data-ttu-id="8c6f0-111">Inserimento di nodi di pari livello</span><span class="sxs-lookup"><span data-stu-id="8c6f0-111">Inserting Sibling Nodes</span></span>  
 <span data-ttu-id="8c6f0-112">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i seguenti metodi per inserire nodi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-112">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert sibling nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 <span data-ttu-id="8c6f0-113">Tali metodi consentono di inserire nodi di pari livello prima e dopo il nodo su cui l'oggetto <xref:System.Xml.XPath.XPathNavigator> è attualmente posizionato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-113">These methods insert sibling nodes before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="8c6f0-114">I metodi <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> e <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> sono in overload e accettano un oggetto `string`, <xref:System.Xml.XmlReader> o un oggetto <xref:System.Xml.XPath.XPathNavigator> contenente il nodo di pari livello da aggiungere come parametro.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-114">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> methods are overloaded and accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the sibling node to add as parameters.</span></span> <span data-ttu-id="8c6f0-115">Entrambi i metodi restituiscono inoltre un oggetto <xref:System.Xml.XmlWriter> usato per inserire i nodi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-115">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert sibling nodes.</span></span>  
  
 <span data-ttu-id="8c6f0-116">Nei metodi <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> e <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> viene inserito un nodo singolo di pari livello prima e dopo il nodo su cui un oggetto <xref:System.Xml.XPath.XPathNavigator> è attualmente posizionato usando come parametri il prefisso dello spazio dei nomi, il nome locale, l'URI dello spazio dei nomi e il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-116">The <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods insert a single sibling node before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="8c6f0-117">Nell'esempio seguente viene inserito un nuovo elemento `pages` prima dell'elemento figlio `price` del primo elemento `book` nel file `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-117">In the following example a new `pages` element is inserted before the `price` child element of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 <span data-ttu-id="8c6f0-118">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="8c6f0-119">Per altre informazioni sui metodi <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> e <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-119">For more information about the <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-child-nodes"></a><span data-ttu-id="8c6f0-120">Inserimento di nodi figlio</span><span class="sxs-lookup"><span data-stu-id="8c6f0-120">Inserting Child Nodes</span></span>  
 <span data-ttu-id="8c6f0-121">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i seguenti metodi per inserire nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-121">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert child nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 <span data-ttu-id="8c6f0-122">In tali metodi i nodi figlio sono aggiunti o anteposti alla fine e all'inizio dell'elenco dei nodi figlio del nodo sul quale un oggetto <xref:System.Xml.XPath.XPathNavigator> è attualmente posizionato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-122">These methods append and prepend child nodes to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="8c6f0-123">Analogamente ai metodi descritti nella sezione "Inserimento di nodi di pari livello", nei metodi <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> e <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> viene accettato un oggetto `string`, <xref:System.Xml.XmlReader> o un oggetto <xref:System.Xml.XPath.XPathNavigator> contenente il nodo figlio da aggiungere come parametri.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-123">Like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the child node to add as parameters.</span></span> <span data-ttu-id="8c6f0-124">Entrambi i metodi restituiscono inoltre un oggetto <xref:System.Xml.XmlWriter> usato per inserire i nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-124">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert child nodes.</span></span>  
  
 <span data-ttu-id="8c6f0-125">Analogamente ai metodi descritti nella sezione "Inserimento di nodi di pari livello", nei metodi <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> e <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> viene inserito un singolo nodo figlio alla fine e all'inizio dell'elenco dei nodi figlio del nodo su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator> usando come parametri il prefisso dello spazio dei nomi, il nome locale, l'URI dello spazio dei nomi e il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-125">Also like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods insert a single child node to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="8c6f0-126">Nell'esempio seguente, viene aggiunto un nuovo elemento figlio `pages` all'elenco degli elementi figlio del primo elemento `book` nel file `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-126">In the following example, a new `pages` child element is appended to the list of child elements of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 <span data-ttu-id="8c6f0-127">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-127">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="8c6f0-128">Per altre informazioni sui metodi <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> e <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-128">For more information about the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-attribute-nodes"></a><span data-ttu-id="8c6f0-129">Inserimento di nodi Attribute</span><span class="sxs-lookup"><span data-stu-id="8c6f0-129">Inserting Attribute Nodes</span></span>  
 <span data-ttu-id="8c6f0-130">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i seguenti metodi per inserire nodi Attribute.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-130">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert attribute nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 <span data-ttu-id="8c6f0-131">Tali metodi consentono di inserire nodi Attribute sul nodo di tipo element su cui un oggetto <xref:System.Xml.XPath.XPathNavigator> è attualmente posizionato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-131">These methods insert attribute nodes on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="8c6f0-132">Nel metodo <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> viene creato un nodo Attribute sul nodo di tipo element su cui un oggetto <xref:System.Xml.XPath.XPathNavigator> è attualmente posizionato usando come parametri il prefisso dello spazio dei nomi, il nome locale, l'URI dello spazio dei nomi e il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-132">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method creates an attribute node on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span> <span data-ttu-id="8c6f0-133">Il metodo <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> restituisce un oggetto <xref:System.Xml.XmlWriter> usato per inserire i nodi Attribute.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-133">The <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method returns an <xref:System.Xml.XmlWriter> object used to insert attribute nodes.</span></span>  
  
 <span data-ttu-id="8c6f0-134">Nell'esempio seguente vengono creati nuovi attributi `discount` e `currency` sull'elemento figlio `price` del primo elemento `book` nel file `contosoBooks.xml` usando l'oggetto <xref:System.Xml.XmlWriter> restituito dal metodo <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-134">In the following example, new `discount` and `currency` attributes are created on the `price` child element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XmlWriter> object returned from the <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 <span data-ttu-id="8c6f0-135">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-135">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="8c6f0-136">Per altre informazioni sui metodi <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> e <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-136">For more information about the <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
## <a name="copying-nodes"></a><span data-ttu-id="8c6f0-137">Copia di nodi</span><span class="sxs-lookup"><span data-stu-id="8c6f0-137">Copying Nodes</span></span>  
 <span data-ttu-id="8c6f0-138">In alcuni casi può essere necessario compilare un documento XML con il contenuto di un altro documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-138">In certain cases you may want to populate an XML document with the contents from another XML document.</span></span> <span data-ttu-id="8c6f0-139">Entrambe le classi <xref:System.Xml.XPath.XPathNavigator> e <xref:System.Xml.XmlWriter> sono in grado di copiare i nodi in un oggetto<xref:System.Xml.XmlDocument> proveniente da un oggetto <xref:System.Xml.XmlReader> esistente o da un oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-139">Both the <xref:System.Xml.XPath.XPathNavigator> class and the <xref:System.Xml.XmlWriter> class can copy nodes to an <xref:System.Xml.XmlDocument> object from an existing <xref:System.Xml.XmlReader> object or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="8c6f0-140">Gli overload dei metodi <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> e <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> della classe <xref:System.Xml.XPath.XPathNavigator> accettano tutti un oggetto <xref:System.Xml.XPath.XPathNavigator> o un oggetto <xref:System.Xml.XmlReader> come parametro.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-140">The <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class all have overloads that can accept an <xref:System.Xml.XPath.XPathNavigator> object or an <xref:System.Xml.XmlReader> object as a parameter.</span></span>  
  
 <span data-ttu-id="8c6f0-141">Gli overload del metodo <xref:System.Xml.XmlWriter.WriteNode%2A> della classe <xref:System.Xml.XmlWriter> possono accettare un oggetto <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-141">The <xref:System.Xml.XmlWriter.WriteNode%2A> method of the <xref:System.Xml.XmlWriter> class has overloads that can accept an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="8c6f0-142">Nell'esempio seguente tutti gli elementi `book` vengono copiati da un documento all'altro.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-142">The following example copies all the `book` elements from one document to another.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a><span data-ttu-id="8c6f0-143">Inserimento dei valori</span><span class="sxs-lookup"><span data-stu-id="8c6f0-143">Inserting Values</span></span>  
 <span data-ttu-id="8c6f0-144">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce i metodi <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> e <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> per inserire i valori di un nodo in un oggetto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-144">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to insert values for a node into an <xref:System.Xml.XmlDocument> object.</span></span>  
  
### <a name="inserting-untyped-values"></a><span data-ttu-id="8c6f0-145">Inserimento di valori non tipizzati</span><span class="sxs-lookup"><span data-stu-id="8c6f0-145">Inserting Untyped Values</span></span>  
 <span data-ttu-id="8c6f0-146">Il metodo <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> consente semplicemente di inserire il valore non tipizzato `string`, passato come parametro, come valore del nodo su cui è attualmente posizionato l'oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-146">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="8c6f0-147">Il valore viene inserito senza alcun tipo o senza verificare la validità del nuovo valore in base al tipo del nodo se sono disponibili le informazioni sullo schema.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-147">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="8c6f0-148">Nell'esempio seguente, il metodo <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> viene usato per aggiornare tutti gli elementi `price` nel file `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-148">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="8c6f0-149">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-149">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a><span data-ttu-id="8c6f0-150">Inserimento di valori tipizzati</span><span class="sxs-lookup"><span data-stu-id="8c6f0-150">Inserting Typed Values</span></span>  
 <span data-ttu-id="8c6f0-151">Quando il tipo di un nodo è un tipo semplice di W3C XML Schema, il nuovo valore inserito tramite il metodo <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> viene controllato rispetto ai facet del tipo semplice prima dell'impostazione del valore.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-151">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="8c6f0-152">Se il nuovo valore non è valido in base al tipo del nodo (ad esempio, l'impostazione di un valore `-1` su un elemento il cui tipo è `xs:positiveInteger`), viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-152">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="8c6f0-153">Nell'esempio seguente si tenta di modificare il valore dell'elemento `price` del primo elemento `book` nel file `contosoBooks.xml` in un valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-153">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="8c6f0-154">Poiché il tipo XML Schema dell'elemento `price` viene definito come `xs:decimal` nei file `contosoBooks.xsd`, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-154">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
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
  
navigator.SetTypedValue(DateTime.Now)  
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
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="8c6f0-155">Nell'esempio il file `contosoBooks.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-155">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="8c6f0-156">Anche il file `contosoBooks.xsd` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-156">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="8c6f0-157">Proprietà InnerXml e OuterXml</span><span class="sxs-lookup"><span data-stu-id="8c6f0-157">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="8c6f0-158">Le proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> della classe <xref:System.Xml.XPath.XPathNavigator> consentono di modificare il markup XML dei nodi su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-158">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="8c6f0-159">La proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> consente di modificare il markup XML dei nodi figlio su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator> con il contenuto analizzato della `string` XML specificata.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-159">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="8c6f0-160">Allo stesso modo, la proprietà <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> consente di modificare il markup XML dei nodi figlio su cui è attualmente posizionato un oggetto <xref:System.Xml.XPath.XPathNavigator> nonché il nodo corrente stesso.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-160">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="8c6f0-161">Oltre ai metodi descritti in questo argomento, è possibile usare le proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> per rimuovere nodi e valori da un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-161">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to insert nodes and values in an XML document.</span></span> <span data-ttu-id="8c6f0-162">Per altre informazioni sull'uso delle proprietà <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> e <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> per inserire nodi e valori, vedere l'argomento [Modificare dati XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="8c6f0-162">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to insert nodes and values, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="namespace-and-xmllang-conflicts"></a><span data-ttu-id="8c6f0-163">Conflitti tra spazio dei nomi e xml:lang</span><span class="sxs-lookup"><span data-stu-id="8c6f0-163">Namespace and xml:lang Conflicts</span></span>  
 <span data-ttu-id="8c6f0-164">Determinati conflitti relativi all'ambito dello spazio dei nomi e delle dichiarazioni `xml:lang` possono verificarsi quando si inseriscono i dati XML usando i metodi <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> e <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> della classe<xref:System.Xml.XPath.XPathNavigator> che accetta oggetti <xref:System.Xml.XmlReader> come parametri.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-164">Certain conflicts related to the scope of namespace and `xml:lang` declarations can occur when inserting XML data using the <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class that take <xref:System.Xml.XmlReader> objects as parameters.</span></span>  
  
 <span data-ttu-id="8c6f0-165">Di seguito sono riportati alcuni tra i possibili conflitti tra gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-165">The following are the possible namespace conflicts.</span></span>  
  
- <span data-ttu-id="8c6f0-166">Se viene rilevato uno spazio dei nomi nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader>, in cui il mapping del prefisso URI dello spazio dei nomi non si trova nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, viene aggiunta una nuova dichiarazione dello spazio dei nomi al nuovo nodo inserito.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-166">If there is a namespace in-scope within the <xref:System.Xml.XmlReader> object's context, where the prefix to namespace URI mapping is not in the <xref:System.Xml.XPath.XPathNavigator> object's context, a new namespace declaration is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="8c6f0-167">Se lo stesso URI dello spazio dei nomi si trova sia nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader> che nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, ma con un diverso prefisso mappato in entrambi i contesti, viene aggiunta una nuova dichiarazione dello spazio dei nomi al nuovo nodo inserito, con prefisso e URI dello spazio dei nomi tratti dall'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-167">If the same namespace URI is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different prefix mapped to it in both contexts, a new namespace declaration is added to the newly inserted node, with the prefix and namespace URI taken from the <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="8c6f0-168">Se lo stesso prefisso dello spazio dei nomi si trova sia nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader> che nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, ma con un diverso URI dello spazio dei nomi mappato in entrambi i contesti, viene aggiunta una nuova dichiarazione dello spazio dei nomi al nuovo nodo inserito, che ridichiara il prefisso con l'URI dello spazio dei nomi tratto dall'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-168">If the same namespace prefix is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different namespace URI mapped to it in both contexts, a new namespace declaration is added to the newly inserted node which re-declares that prefix with the namespace URI taken from <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="8c6f0-169">Se il prefisso e l'URI dello spazio dei nomi in entrambi i contesti dell'oggetto <xref:System.Xml.XmlReader> e dell'oggetto <xref:System.Xml.XPath.XPathNavigator> sono gli stessi, non viene aggiunta alcuna nuova dichiarazione dello spazio dei nomi al nuovo nodo inserito.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-169">If the prefix as well as the namespace URI in both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context is the same, no new namespace declaration is added to the newly inserted node.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c6f0-170">La descrizione precedente è valida anche per le dichiarazioni dello spazio dei nomi con la `string` vuota come prefisso (ad esempio la dichiarazione dello spazio dei nomi predefinita).</span><span class="sxs-lookup"><span data-stu-id="8c6f0-170">The description above also applies to namespace declarations with the empty `string` as a prefix (for example, the default namespace declaration).</span></span>  
  
 <span data-ttu-id="8c6f0-171">Di seguito sono riportati alcuni tra i possibili conflitti `xml:lang`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-171">The following are the possible `xml:lang` conflicts.</span></span>  
  
- <span data-ttu-id="8c6f0-172">Se viene rilevato un attributo `xml:lang` nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader> ma non nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, viene aggiunto al nuovo nodo inserito un attributo `xml:lang` il cui valore viene tratto dall'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-172">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XmlReader> object's context but not in the <xref:System.Xml.XPath.XPathNavigator> object's context, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="8c6f0-173">Se viene rilevato un attributo `xml:lang` sia nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader> che nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, ma ciascuno con un valore diverso, viene aggiunto al nuovo nodo inserito un attributo `xml:lang` il cui valore viene tratto dall'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-173">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each has a different value, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="8c6f0-174">Se viene rilevato un attributo `xml:lang` sia nell'ambito del contesto dell'oggetto <xref:System.Xml.XmlReader> che nel contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator>, ma ciascuno con lo stesso valore, non viene aggiunto alcun nuovo attributo `xml:lang` al nodo appena inserito.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-174">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each with the same value, no new `xml:lang` attribute is added on the newly inserted node.</span></span>  
  
- <span data-ttu-id="8c6f0-175">Se viene rilevato un attributo `xml:lang` nell'ambito del contesto dell'oggetto <xref:System.Xml.XPath.XPathNavigator> ma non nel contesto dell'oggetto <xref:System.Xml.XmlReader>, non viene aggiunto alcun attributo `xml:lang` al nuovo nodo inserito.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-175">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XPath.XPathNavigator> object's context, but none existing in the <xref:System.Xml.XmlReader> object's context, no `xml:lang` attribute is added to the newly inserted node.</span></span>  
  
## <a name="inserting-nodes-with-xmlwriter"></a><span data-ttu-id="8c6f0-176">Inserimento di nodi con XmlWriter</span><span class="sxs-lookup"><span data-stu-id="8c6f0-176">Inserting Nodes with XmlWriter</span></span>  
 <span data-ttu-id="8c6f0-177">I metodi usati per inserire nodi di pari livello, nodi figlio e nodi Attribute descritti nella sezione "Inserimento di nodi e valori" sono in overload.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-177">The methods used to insert sibling, child and attribute nodes described in the "Inserting Nodes and Values" section are overloaded.</span></span> <span data-ttu-id="8c6f0-178">I metodi <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> e <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> della classe <xref:System.Xml.XPath.XPathNavigator> restituiscono un oggetto <xref:System.Xml.XmlWriter> usato per inserire i nodi.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-178">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class return an <xref:System.Xml.XmlWriter> object used to insert nodes.</span></span>  
  
### <a name="unsupported-xmlwriter-methods"></a><span data-ttu-id="8c6f0-179">Metodi XmlWriter non supportati</span><span class="sxs-lookup"><span data-stu-id="8c6f0-179">Unsupported XmlWriter Methods</span></span>  
 <span data-ttu-id="8c6f0-180">Non tutti i metodi usati per scrivere le informazioni in un documento XML usando la classe <xref:System.Xml.XmlWriter> sono supportati dalla classe <xref:System.Xml.XPath.XPathNavigator> a causa della differenza tra il modello dati XPath e il modello DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="8c6f0-180">Not all of the methods used for writing information to an XML document using the <xref:System.Xml.XmlWriter> class are supported by the <xref:System.Xml.XPath.XPathNavigator> class due to difference between the XPath data model and the Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="8c6f0-181">Nella tabella seguente vengono descritti i metodi della classe <xref:System.Xml.XmlWriter> non supportati dalla classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-181">The following table describes the <xref:System.Xml.XmlWriter> class methods not supported by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
|<span data-ttu-id="8c6f0-182">Metodo</span><span class="sxs-lookup"><span data-stu-id="8c6f0-182">Method</span></span>|<span data-ttu-id="8c6f0-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c6f0-183">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|<span data-ttu-id="8c6f0-184">Genera un'eccezione <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-184">Throws a <xref:System.NotSupportedException> exception.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|<span data-ttu-id="8c6f0-185">Ignorato al livello radice e genera un'eccezione <xref:System.NotSupportedException> se chiamato a qualsiasi altro livello nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-185">Ignored at the root level and throws a <xref:System.NotSupportedException> exception if called at any other level in the XML document.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|<span data-ttu-id="8c6f0-186">Considerato come una chiamata al metodo <xref:System.Xml.XmlWriter.WriteString%2A> per il carattere o i caratteri equivalenti.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-186">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|<span data-ttu-id="8c6f0-187">Considerato come una chiamata al metodo <xref:System.Xml.XmlWriter.WriteString%2A> per il carattere o i caratteri equivalenti.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-187">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|<span data-ttu-id="8c6f0-188">Considerato come una chiamata al metodo <xref:System.Xml.XmlWriter.WriteString%2A> per il carattere o i caratteri equivalenti.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-188">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
  
 <span data-ttu-id="8c6f0-189">Per altre informazioni sulla classe <xref:System.Xml.XmlWriter>, vedere la documentazione di riferimento per la classe <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-189">For more information about the <xref:System.Xml.XmlWriter> class, see the <xref:System.Xml.XmlWriter> class reference documentation.</span></span>  
  
### <a name="multiple-xmlwriter-objects"></a><span data-ttu-id="8c6f0-190">Più oggetti XmlWriter</span><span class="sxs-lookup"><span data-stu-id="8c6f0-190">Multiple XmlWriter Objects</span></span>  
 <span data-ttu-id="8c6f0-191">È possibile disporre di più oggetti <xref:System.Xml.XPath.XPathNavigator> che scelgono parti diverse di un documento XML con uno o più oggetti <xref:System.Xml.XmlWriter> aperti.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-191">It is possible to have multiple <xref:System.Xml.XPath.XPathNavigator> objects pointing to different parts of an XML document with one or more open <xref:System.Xml.XmlWriter> objects.</span></span> <span data-ttu-id="8c6f0-192">Sono consentiti e supportati più oggetti <xref:System.Xml.XmlWriter> in scenari a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-192">Multiple <xref:System.Xml.XmlWriter> objects are allowed and supported in single-threaded scenarios.</span></span>  
  
 <span data-ttu-id="8c6f0-193">Di seguito sono riportate note importanti relative all'utilizzo di più oggetti <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-193">The following are important notes to consider when using multiple <xref:System.Xml.XmlWriter> objects.</span></span>  
  
- <span data-ttu-id="8c6f0-194">I frammenti XML scritti dagli oggetti <xref:System.Xml.XmlWriter> vengono aggiunti al documento XML quando viene chiamato il metodo <xref:System.Xml.XmlWriter.Close%2A> di ciascun oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-194">XML fragments written by <xref:System.Xml.XmlWriter> objects are added to the XML document when the <xref:System.Xml.XmlWriter.Close%2A> method of each <xref:System.Xml.XmlWriter> object is called.</span></span> <span data-ttu-id="8c6f0-195">Fino a quel punto, l'oggetto <xref:System.Xml.XmlWriter> sta scrivendo un frammento disconnesso.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-195">Until that point, the <xref:System.Xml.XmlWriter> object is writing a disconnected fragment.</span></span> <span data-ttu-id="8c6f0-196">Se viene eseguita un'operazione sul documento XML, i frammenti scritti da un oggetto <xref:System.Xml.XmlWriter> prima che sia stato chiamato il metodo <xref:System.Xml.XmlWriter.Close%2A> non sono interessati dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-196">If an operation is performed on the XML document, any fragments being written by an <xref:System.Xml.XmlWriter> object, before the <xref:System.Xml.XmlWriter.Close%2A> has been called, are not affected.</span></span>  
  
- <span data-ttu-id="8c6f0-197">Se viene rilevato un oggetto <xref:System.Xml.XmlWriter> aperto in un particolare sottoalbero XML che viene in seguito eliminato, l'oggetto <xref:System.Xml.XmlWriter> può ancora essere aggiunto al sottoalbero.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-197">If there is an open <xref:System.Xml.XmlWriter> object on a particular XML subtree and that subtree is deleted, the <xref:System.Xml.XmlWriter> object may still add to the sub-tree.</span></span> <span data-ttu-id="8c6f0-198">Il sottoalbero diviene semplicemente un frammento eliminato.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-198">The subtree simply becomes a deleted fragment.</span></span>  
  
- <span data-ttu-id="8c6f0-199">Se più oggetti <xref:System.Xml.XmlWriter> vengono aperti nello stesso punto del documento XML, verranno aggiunti al documento XML in base all'ordine in cui gli oggetti<xref:System.Xml.XmlWriter> sono stati chiusi, non nell'ordine in base al quale sono stati aperti.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-199">If multiple <xref:System.Xml.XmlWriter> objects are opened at the same point in the XML document, they are added to the XML document in the order in which the <xref:System.Xml.XmlWriter> objects are closed, not in the order in which they were opened.</span></span>  
  
 <span data-ttu-id="8c6f0-200">Nell'esempio seguente viene creato un oggetto <xref:System.Xml.XmlDocument>, quindi un oggetto <xref:System.Xml.XPath.XPathNavigator> e infine viene usato l'oggetto <xref:System.Xml.XmlWriter> restituito dal metodo <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> per creare la struttura del primo libro nel file `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-200">The following example creates an <xref:System.Xml.XmlDocument> object, creates an <xref:System.Xml.XPath.XPathNavigator> object, and then uses the <xref:System.Xml.XmlWriter> object returned by the <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> method to create the structure of the first book in the `books.xml` file.</span></span> <span data-ttu-id="8c6f0-201">L'oggetto viene quindi salvato come file `book.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-201">The example then saves it as the `book.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="8c6f0-202">Salvataggio di un documento XML</span><span class="sxs-lookup"><span data-stu-id="8c6f0-202">Saving an XML Document</span></span>  
 <span data-ttu-id="8c6f0-203">Il salvataggio delle modifiche apportate a un oggetto <xref:System.Xml.XmlDocument> mediante i metodi descritti in questo argomento viene eseguito usando i metodi della classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="8c6f0-203">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="8c6f0-204">Per altre informazioni sul salvataggio delle modifiche apportate a un oggetto <xref:System.Xml.XmlDocument>, vedere [Salvataggio e scrittura di un documento](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="8c6f0-204">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6f0-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c6f0-205">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="8c6f0-206">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="8c6f0-206">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="8c6f0-207">Modificare dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8c6f0-207">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="8c6f0-208">Rimuovere dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8c6f0-208">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
