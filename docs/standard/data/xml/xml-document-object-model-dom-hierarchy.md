---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef2b5b200f95cdfac9b08a33c328c1dfb797e59e
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537774"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="f85aa-102">Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)</span><span class="sxs-lookup"><span data-stu-id="f85aa-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="f85aa-103">Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.</span><span class="sxs-lookup"><span data-stu-id="f85aa-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="f85aa-104">![Gerarchia del modello a oggetti di documenti XML &#40;DOM&#41;](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="f85aa-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="f85aa-105">Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="f85aa-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="f85aa-106">Le classi seguenti non ereditano da **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="f85aa-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="f85aa-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="f85aa-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="f85aa-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="f85aa-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="f85aa-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="f85aa-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="f85aa-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="f85aa-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="f85aa-111">La classe **XmlImplementation** viene usata per creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f85aa-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="f85aa-112">Per altre informazioni, vedere [Creazione di documenti XML](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="f85aa-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="f85aa-113">Dalla classe **XmlNamedNodeMap** viene gestito un set di nodi non ordinato.</span><span class="sxs-lookup"><span data-stu-id="f85aa-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="f85aa-114">Per altre informazioni, vedere [Recupero di nodi non ordinati in base al nome o all'indice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="f85aa-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="f85aa-115">Dalla classe **XmlNodeList** viene gestito un elenco di nodi ordinato.</span><span class="sxs-lookup"><span data-stu-id="f85aa-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="f85aa-116">Per altre informazioni, vedere [Recupero di nodi ordinati in base all'indice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="f85aa-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="f85aa-117">Dalla classe **XmlNodeChangedEventArgs** vengono gestiti i gestori eventi registrati in **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="f85aa-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="f85aa-118">Per altre informazioni, vedere [Gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="f85aa-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="f85aa-119">La classe **XmlLinkedNode** eredita da **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="f85aa-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="f85aa-120">Lo scopo di questa classe è di eseguire l'override di due metodi di **XmlNode**: i metodi **PreviousSibling** e **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="f85aa-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="f85aa-121">Questi metodi di cui è stato eseguito l'override vengono quindi ereditati e usati dalle classi **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, che presentano elementi di pari livello precedenti e successivi.</span><span class="sxs-lookup"><span data-stu-id="f85aa-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85aa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85aa-122">See also</span></span>

- [<span data-ttu-id="f85aa-123">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="f85aa-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
