---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: a6099b6c5e30fbf2e4d5d4ed046369bc8f884845
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291435"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="c65fc-102">Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)</span><span class="sxs-lookup"><span data-stu-id="c65fc-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="c65fc-103">Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.</span><span class="sxs-lookup"><span data-stu-id="c65fc-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="c65fc-104">![Document Object Model XML &#40;gerarchia&#41; DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="c65fc-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="c65fc-105">Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="c65fc-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="c65fc-106">Le classi seguenti non ereditano da **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="c65fc-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="c65fc-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="c65fc-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="c65fc-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="c65fc-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="c65fc-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="c65fc-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="c65fc-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="c65fc-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="c65fc-111">La classe **XmlImplementation** viene usata per creare un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c65fc-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="c65fc-112">Per altre informazioni, vedere [Creazione di documenti XML](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="c65fc-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="c65fc-113">Dalla classe **XmlNamedNodeMap** viene gestito un set di nodi non ordinato.</span><span class="sxs-lookup"><span data-stu-id="c65fc-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="c65fc-114">Per altre informazioni, vedere [Recupero di nodi non ordinati in base al nome o all'indice](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="c65fc-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="c65fc-115">Dalla classe **XmlNodeList** viene gestito un elenco di nodi ordinato.</span><span class="sxs-lookup"><span data-stu-id="c65fc-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="c65fc-116">Per altre informazioni, vedere [Recupero di nodi ordinati in base all'indice](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="c65fc-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="c65fc-117">Dalla classe **XmlNodeChangedEventArgs** vengono gestiti i gestori eventi registrati in **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="c65fc-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="c65fc-118">Per altre informazioni, vedere [Gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="c65fc-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="c65fc-119">La classe **XmlLinkedNode** eredita da **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="c65fc-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="c65fc-120">Lo scopo di questa classe è di eseguire l'override di due metodi di **XmlNode**: i metodi **PreviousSibling** e **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="c65fc-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="c65fc-121">Questi metodi di cui è stato eseguito l'override vengono quindi ereditati e usati dalle classi **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, che presentano elementi di pari livello precedenti e successivi.</span><span class="sxs-lookup"><span data-stu-id="c65fc-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65fc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c65fc-122">See also</span></span>

- [<span data-ttu-id="c65fc-123">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="c65fc-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
