---
title: Contenuto valido di XElement e XDocument Objects2 | Documenti di Microsoft
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
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ecdcd4c2c0ec61cf248c9e210d42abb750e0546b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="de372-102">Contenuto valido di oggetti XElement e XDocument</span><span class="sxs-lookup"><span data-stu-id="de372-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="de372-103">In questo argomento vengono illustrati gli argomenti validi che è possibile passare a costruttori e i metodi usati per aggiungere contenuto a elementi e documenti.</span><span class="sxs-lookup"><span data-stu-id="de372-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="de372-104">Contenuto valido</span><span class="sxs-lookup"><span data-stu-id="de372-104">Valid Content</span></span>  
 <span data-ttu-id="de372-105">Le query spesso restituiscono <xref:System.Collections.Generic.IEnumerable%601>di <xref:System.Xml.Linq.XElement>o <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="de372-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="de372-106">È possibile passare raccolte di <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>gli oggetti per il <xref:System.Xml.Linq.XElement>costruttore.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="de372-107">Pertanto è comodo passare i risultati di una query come contenuto in metodi e costruttori usati per popolare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="de372-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="de372-108">Quando si aggiunge contenuto semplice, è possibile passare diversi tipi a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="de372-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="de372-109">I tipi validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="de372-109">Valid types include the following:</span></span>  
  
-   <span data-ttu-id="de372-110"><xref:System.String></xref:System.String></span><span class="sxs-lookup"><span data-stu-id="de372-110"><xref:System.String></span></span>  
  
-   <span data-ttu-id="de372-111"><xref:System.Double></xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="de372-111"><xref:System.Double></span></span>  
  
-   <span data-ttu-id="de372-112"><xref:System.Single></xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="de372-112"><xref:System.Single></span></span>  
  
-   <span data-ttu-id="de372-113"><xref:System.Decimal></xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="de372-113"><xref:System.Decimal></span></span>  
  
-   <span data-ttu-id="de372-114"><xref:System.Boolean></xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="de372-114"><xref:System.Boolean></span></span>  
  
-   <span data-ttu-id="de372-115"><xref:System.DateTime></xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="de372-115"><xref:System.DateTime></span></span>  
  
-   <span data-ttu-id="de372-116"><xref:System.TimeSpan></xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="de372-116"><xref:System.TimeSpan></span></span>  
  
-   <span data-ttu-id="de372-117"><xref:System.DateTimeOffset></xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="de372-117"><xref:System.DateTimeOffset></span></span>  
  
-   <span data-ttu-id="de372-118">Qualsiasi tipo che implementa `Object.ToString`.</span><span class="sxs-lookup"><span data-stu-id="de372-118">Any type that implements `Object.ToString`.</span></span>  
  
-   <span data-ttu-id="de372-119">Qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="de372-119">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="de372-120">Quando si aggiunge contenuto complesso, è possibile passare diversi tipi a questo metodo:</span><span class="sxs-lookup"><span data-stu-id="de372-120">When adding complex content, various types can be passed to this method:</span></span>  
  
-   <span data-ttu-id="de372-121"><xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="de372-121"><xref:System.Xml.Linq.XObject></span></span>  
  
-   <span data-ttu-id="de372-122"><xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="de372-122"><xref:System.Xml.Linq.XNode></span></span>  
  
-   <span data-ttu-id="de372-123"><xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="de372-123"><xref:System.Xml.Linq.XAttribute></span></span>  
  
-   <span data-ttu-id="de372-124">Qualsiasi tipo che implementa<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="de372-124">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="de372-125">Se un oggetto implementa <xref:System.Collections.Generic.IEnumerable%601>, la raccolta nell'oggetto viene enumerata e vengono aggiunti tutti gli elementi nella raccolta.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="de372-125">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="de372-126">Se la raccolta contiene <xref:System.Xml.Linq.XNode>o <xref:System.Xml.Linq.XAttribute>oggetti, ogni elemento nella raccolta viene aggiunto separatamente.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="de372-126">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="de372-127">Se la raccolta contiene testo (oppure oggetti convertiti in testo), il testo della raccolta viene concatenato e aggiunto come un unico nodo di tipo text.</span><span class="sxs-lookup"><span data-stu-id="de372-127">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="de372-128">Se il contenuto è `null`, non viene aggiunto nulla.</span><span class="sxs-lookup"><span data-stu-id="de372-128">If content is `null`, nothing is added.</span></span> <span data-ttu-id="de372-129">Quando si passa una raccolta, gli elementi della raccolta possono essere `null`.</span><span class="sxs-lookup"><span data-stu-id="de372-129">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="de372-130">Un elemento `null` della raccolta non ha effetto sull'albero.</span><span class="sxs-lookup"><span data-stu-id="de372-130">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="de372-131">Un attributo aggiunto deve includere un nome univoco nell'elemento che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="de372-131">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="de372-132">Quando si aggiunge <xref:System.Xml.Linq.XNode>o <xref:System.Xml.Linq.XAttribute>oggetti, se il nuovo contenuto non ha elementi padre, quindi gli oggetti vengono semplicemente collegati all'albero XML.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="de372-132">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="de372-133">Se invece il nuovo contenuto include già elementi padre e fa parte di un altro albero XML, viene duplicato e quindi collegato all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="de372-133">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="de372-134">Contenuto valido per documenti</span><span class="sxs-lookup"><span data-stu-id="de372-134">Valid Content for Documents</span></span>  
 <span data-ttu-id="de372-135">Non è possibile aggiungere attributi e contenuto semplice a un documento.</span><span class="sxs-lookup"><span data-stu-id="de372-135">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="de372-136">Non sono presenti molti scenari che è necessario creare un <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="de372-136">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="de372-137">Al contrario, in genere è possibile creare strutture ad albero XML con un <xref:System.Xml.Linq.XElement>nodo radice.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-137">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="de372-138">A meno che non si dispone di un requisito specifico per creare un documento (ad esempio perché è necessario creare istruzioni di elaborazione e commenti al primo livello o supportare tipi di documento), è spesso più conveniente utilizzare <xref:System.Xml.Linq.XElement>come nodo radice.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-138">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="de372-139">Il contenuto valido per un documento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="de372-139">Valid content for a document includes the following:</span></span>  
  
-   <span data-ttu-id="de372-140">Zero o uno <xref:System.Xml.Linq.XDocumentType>oggetti.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="de372-140">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="de372-141">I tipi di documento devono essere inseriti prima dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="de372-141">The document types must come before the element.</span></span>  
  
-   <span data-ttu-id="de372-142">Zero o un elemento.</span><span class="sxs-lookup"><span data-stu-id="de372-142">Zero or one element.</span></span>  
  
-   <span data-ttu-id="de372-143">Zero o più commenti.</span><span class="sxs-lookup"><span data-stu-id="de372-143">Zero or more comments.</span></span>  
  
-   <span data-ttu-id="de372-144">Zero o più istruzioni di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="de372-144">Zero or more processing instructions.</span></span>  
  
-   <span data-ttu-id="de372-145">Zero o più nodi di tipo text che contengono solo spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="de372-145">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="de372-146">Costruttori e funzioni che consentono l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="de372-146">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="de372-147">I metodi seguenti consentono di aggiungere contenuto figlio a un <xref:System.Xml.Linq.XElement>o un <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-147">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="de372-148">Metodo</span><span class="sxs-lookup"><span data-stu-id="de372-148">Method</span></span>|<span data-ttu-id="de372-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de372-149">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de372-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="de372-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></span></span>|<span data-ttu-id="de372-151">Costruisce un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-151">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="de372-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="de372-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></span></span>|<span data-ttu-id="de372-153">Costruisce un <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="de372-153">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="de372-154"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="de372-154"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="de372-155">Aggiunge alla fine del contenuto figlio <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-155">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="de372-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="de372-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="de372-157">Aggiunge contenuto dopo la <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="de372-157">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="de372-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="de372-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="de372-159">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="de372-159">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="de372-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="de372-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="de372-161">Aggiunge contenuto all'inizio del contenuto figlio dell'elemento <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="de372-161">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="de372-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A></span><span class="sxs-lookup"><span data-stu-id="de372-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></span></span>|<span data-ttu-id="de372-163">Sostituisce tutto il contenuto (nodi figlio e attributi) di un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-163">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="de372-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="de372-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span></span>|<span data-ttu-id="de372-165">Sostituisce gli attributi di un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="de372-165">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="de372-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span><span class="sxs-lookup"><span data-stu-id="de372-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span></span>|<span data-ttu-id="de372-167">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="de372-167">Replaces the children nodes with new content.</span></span>|  
|<span data-ttu-id="de372-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A></span><span class="sxs-lookup"><span data-stu-id="de372-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></span></span>|<span data-ttu-id="de372-169">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="de372-169">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de372-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de372-170">See Also</span></span>  
 [<span data-ttu-id="de372-171">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de372-171">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
