---
title: Contenuto valido di XElement e XDocument Objects2
ms.date: 07/20/2015
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
ms.openlocfilehash: d222f19f6f588968a3ef1515dca522a4a80e1ffb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364344"
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="3b9f5-102">Contenuto valido di oggetti XElement e XDocument</span><span class="sxs-lookup"><span data-stu-id="3b9f5-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="3b9f5-103">In questo argomento vengono illustrati gli argomenti validi che è possibile passare a costruttori e i metodi usati per aggiungere contenuto a elementi e documenti.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="3b9f5-104">Contenuto valido</span><span class="sxs-lookup"><span data-stu-id="3b9f5-104">Valid Content</span></span>  
 <span data-ttu-id="3b9f5-105">Le query spesso restituiscono <xref:System.Collections.Generic.IEnumerable%601> come valore di <xref:System.Xml.Linq.XElement> o <xref:System.Collections.Generic.IEnumerable%601> come valore di <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="3b9f5-106">È possibile passare raccolte di oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> al costruttore <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="3b9f5-107">Pertanto è comodo passare i risultati di una query come contenuto in metodi e costruttori usati per popolare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="3b9f5-108">Quando si aggiunge contenuto semplice, è possibile passare diversi tipi a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="3b9f5-109">I tipi validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b9f5-109">Valid types include the following:</span></span>  
  
- <xref:System.String>  
  
- <xref:System.Double>  
  
- <xref:System.Single>  
  
- <xref:System.Decimal>  
  
- <xref:System.Boolean>  
  
- <xref:System.DateTime>  
  
- <xref:System.TimeSpan>  
  
- <xref:System.DateTimeOffset>  
  
- <span data-ttu-id="3b9f5-110">Qualsiasi tipo che implementa `Object.ToString`.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-110">Any type that implements `Object.ToString`.</span></span>  
  
- <span data-ttu-id="3b9f5-111">Qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-111">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="3b9f5-112">Quando si aggiunge contenuto complesso, è possibile passare diversi tipi a questo metodo:</span><span class="sxs-lookup"><span data-stu-id="3b9f5-112">When adding complex content, various types can be passed to this method:</span></span>  
  
- <xref:System.Xml.Linq.XObject>  
  
- <xref:System.Xml.Linq.XNode>  
  
- <xref:System.Xml.Linq.XAttribute>  
  
- <span data-ttu-id="3b9f5-113">Qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="3b9f5-113">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="3b9f5-114">Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-114">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="3b9f5-115">Se la raccolta contiene oggetti <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, ogni elemento della raccolta viene aggiunto separatamente.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-115">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="3b9f5-116">Se la raccolta contiene testo (oppure oggetti convertiti in testo), il testo della raccolta viene concatenato e aggiunto come un unico nodo di tipo text.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-116">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="3b9f5-117">Se il contenuto è `null`, non viene aggiunto nulla.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-117">If content is `null`, nothing is added.</span></span> <span data-ttu-id="3b9f5-118">Quando si passa una raccolta, gli elementi della raccolta possono essere `null`.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-118">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="3b9f5-119">Un elemento `null` della raccolta non ha effetto sull'albero.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-119">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="3b9f5-120">Un attributo aggiunto deve includere un nome univoco nell'elemento che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-120">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="3b9f5-121">Se quando si aggiungono oggetti <xref:System.Xml.Linq.XNode> o <xref:System.Xml.Linq.XAttribute>, il nuovo contenuto non ha elementi padre, gli oggetti vengono semplicemente collegati all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-121">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="3b9f5-122">Se invece il nuovo contenuto include già elementi padre e fa parte di un altro albero XML, viene duplicato e quindi collegato all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-122">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="3b9f5-123">Contenuto valido per documenti</span><span class="sxs-lookup"><span data-stu-id="3b9f5-123">Valid Content for Documents</span></span>  
 <span data-ttu-id="3b9f5-124">Non è possibile aggiungere attributi e contenuto semplice a un documento.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-124">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="3b9f5-125">Non sono molti gli scenari in cui è richiesta la creazione di un oggetto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-125">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="3b9f5-126">In genere, è invece possibile creare alberi XML con un nodo radice <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-126">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="3b9f5-127">A meno di particolari esigenze che richiedono la creazione di un documento, ad esempio perché è necessario creare istruzioni di elaborazione e commenti al primo livello o supportare tipi di documento, è consigliabile usare <xref:System.Xml.Linq.XElement> come nodo radice.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-127">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="3b9f5-128">Il contenuto valido per un documento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3b9f5-128">Valid content for a document includes the following:</span></span>  
  
- <span data-ttu-id="3b9f5-129">Zero o un oggetto <xref:System.Xml.Linq.XDocumentType>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-129">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="3b9f5-130">I tipi di documento devono essere inseriti prima dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-130">The document types must come before the element.</span></span>  
  
- <span data-ttu-id="3b9f5-131">Zero o un elemento.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-131">Zero or one element.</span></span>  
  
- <span data-ttu-id="3b9f5-132">Zero o più commenti.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-132">Zero or more comments.</span></span>  
  
- <span data-ttu-id="3b9f5-133">Zero o più istruzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-133">Zero or more processing instructions.</span></span>  
  
- <span data-ttu-id="3b9f5-134">Zero o più nodi di tipo text che contengono solo spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-134">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="3b9f5-135">Costruttori e funzioni che consentono l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="3b9f5-135">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="3b9f5-136">I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="3b9f5-136">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="3b9f5-137">Metodo</span><span class="sxs-lookup"><span data-stu-id="3b9f5-137">Method</span></span>|<span data-ttu-id="3b9f5-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b9f5-138">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|<span data-ttu-id="3b9f5-139">Costruisce un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-139">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|<span data-ttu-id="3b9f5-140">Costruisce un oggetto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-140">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="3b9f5-141">Aggiunge il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-141">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="3b9f5-142">Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-142">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="3b9f5-143">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-143">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="3b9f5-144">Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-144">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|<span data-ttu-id="3b9f5-145">Sostituisce tutto il contenuto (nodi figlio e attributi) di un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-145">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|<span data-ttu-id="3b9f5-146">Sostituisce gli attributi di un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-146">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|<span data-ttu-id="3b9f5-147">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-147">Replaces the children nodes with new content.</span></span>|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|<span data-ttu-id="3b9f5-148">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="3b9f5-148">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b9f5-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b9f5-149">See also</span></span>

- [<span data-ttu-id="3b9f5-150">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b9f5-150">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
