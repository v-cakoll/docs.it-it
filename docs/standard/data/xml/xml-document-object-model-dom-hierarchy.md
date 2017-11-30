---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="740c9-102">Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)</span><span class="sxs-lookup"><span data-stu-id="740c9-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="740c9-103">Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.</span><span class="sxs-lookup"><span data-stu-id="740c9-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="740c9-104">![DOM XML Document Object Model &#40; &#41; gerarchia](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="740c9-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="740c9-105">Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="740c9-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="740c9-106">Le classi seguenti non ereditano il **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="740c9-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="740c9-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="740c9-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="740c9-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="740c9-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="740c9-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="740c9-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="740c9-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="740c9-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="740c9-111">Il **XmlImplementation** classe viene utilizzata per creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="740c9-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="740c9-112">Per ulteriori informazioni, vedere [creazione di documenti XML](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="740c9-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="740c9-113">Il **XmlNamedNodeMap** classe gestisce un set di nodi non ordinato.</span><span class="sxs-lookup"><span data-stu-id="740c9-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="740c9-114">Per ulteriori informazioni, vedere [il recupero di nodi non ordinati per nome o indice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="740c9-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="740c9-115">Il **XmlNodeList** classe gestisce un elenco ordinato di nodi.</span><span class="sxs-lookup"><span data-stu-id="740c9-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="740c9-116">Per ulteriori informazioni, vedere [recupero di nodi ordinati in base all'indice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="740c9-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="740c9-117">Il **XmlNodeChangedEventArgs** classe gestisce i gestori eventi registrati il **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="740c9-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="740c9-118">Per ulteriori informazioni, vedere [gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="740c9-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="740c9-119">Il **XmlLinkedNode** classe eredita da **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="740c9-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="740c9-120">Lo scopo consiste nell'eseguire l'override di due metodi di **XmlNode**: il **PreviousSibling** e **NextSibling** metodi.</span><span class="sxs-lookup"><span data-stu-id="740c9-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="740c9-121">Questi metodi sottoposti a override vengono quindi ereditati e utilizzati da **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, e **XmlProcessingInstruction**, che sono classi di elementi di pari livello precedenti e successivi.</span><span class="sxs-lookup"><span data-stu-id="740c9-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740c9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="740c9-122">See Also</span></span>  
 [<span data-ttu-id="740c9-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="740c9-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
