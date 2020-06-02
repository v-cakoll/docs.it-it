---
title: Creazione di nuovi nodi nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: d99a3c68c7554ab266d71a4cbf2e676bc6db8cbc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289577"
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="31618-102">Creazione di nuovi nodi nel DOM</span><span class="sxs-lookup"><span data-stu-id="31618-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="31618-103">Il tipo <xref:System.Xml.XmlDocument> dispone di un metodo di creazione per tutti i tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="31618-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="31618-104">Per creare il nodo, è sufficiente fornire al metodo un nome, se necessario, e un contenuto o altri parametri per i nodi che hanno un contenuto, ad esempio un nodo di tipo text.</span><span class="sxs-lookup"><span data-stu-id="31618-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="31618-105">I metodi seguenti necessitano di un nome e di pochi altri parametri per creare un nodo appropriato.</span><span class="sxs-lookup"><span data-stu-id="31618-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="31618-106">Per altri tipi di nodi è necessario fornire più informazioni dei soli dati per i parametri.</span><span class="sxs-lookup"><span data-stu-id="31618-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="31618-107">Per informazioni sugli attributi, vedere [Creazione di nuovi attributi per gli elementi nel DOM](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="31618-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="31618-108">Per informazioni sulla convalida dei nomi di elementi e attributi, vedere [Verifica dei nomi di attributi ed elementi XML durante la creazione di nuovi nodi](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="31618-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="31618-109">Per creare riferimenti alle entità, vedere [Creazione di nuovi riferimenti alle entità](creating-new-entity-references.md).</span><span class="sxs-lookup"><span data-stu-id="31618-109">For creating entity references, see [Creating New Entity References](creating-new-entity-references.md).</span></span> <span data-ttu-id="31618-110">Per informazioni su come gli spazi dei nomi incidono sull'espansione dei riferimenti alle entità, vedere [Effetto degli spazi dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="31618-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="31618-111">Una volta creati i nuovi nodi, sono disponibili vari metodi per inserirli nell'albero.</span><span class="sxs-lookup"><span data-stu-id="31618-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="31618-112">Nella seguente tabella sono elencati i metodi con una descrizione del punto in cui il nodo viene visualizzato nel DOM XML.</span><span class="sxs-lookup"><span data-stu-id="31618-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="31618-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="31618-113">Method</span></span>|<span data-ttu-id="31618-114">Posizione del nodo</span><span class="sxs-lookup"><span data-stu-id="31618-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="31618-115">Inserito prima del nodo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="31618-115">Inserted before the reference node.</span></span> <span data-ttu-id="31618-116">Ad esempio, per inserire il nuovo nodo ad esempio nella posizione 5:</span><span class="sxs-lookup"><span data-stu-id="31618-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="31618-117">Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.InsertBefore%2A>.</span><span class="sxs-lookup"><span data-stu-id="31618-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="31618-118">Inserito dopo il nodo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="31618-118">Inserted after the reference node.</span></span> <span data-ttu-id="31618-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="31618-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="31618-120">Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.InsertAfter%2A>.</span><span class="sxs-lookup"><span data-stu-id="31618-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="31618-121">Il nodo viene aggiunto alla fine dell'elenco di nodi figlio per il nodo specificato.</span><span class="sxs-lookup"><span data-stu-id="31618-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="31618-122">Se il nodo aggiunto è un <xref:System.Xml.XmlDocumentFragment>, l'intero contenuto del frammento del documento viene spostato nell'elenco figlio di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="31618-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="31618-123">Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.AppendChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="31618-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="31618-124">Il nodo viene aggiunto all'inizio dell'elenco di nodi figlio per il nodo specificato.</span><span class="sxs-lookup"><span data-stu-id="31618-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="31618-125">Se il nodo aggiunto è un <xref:System.Xml.XmlDocumentFragment>, l'intero contenuto del frammento del documento viene spostato nell'elenco figlio di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="31618-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="31618-126">Per altre informazioni, vedere il metodo <xref:System.Xml.XmlNode.PrependChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="31618-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="31618-127">Il nodo <xref:System.Xml.XmlAttribute> viene aggiunto alla fine della raccolta di attributi associata all'elemento.</span><span class="sxs-lookup"><span data-stu-id="31618-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="31618-128">Per altre informazioni, vedere il metodo <xref:System.Xml.XmlAttributeCollection.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="31618-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31618-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31618-129">See also</span></span>

- [<span data-ttu-id="31618-130">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="31618-130">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
