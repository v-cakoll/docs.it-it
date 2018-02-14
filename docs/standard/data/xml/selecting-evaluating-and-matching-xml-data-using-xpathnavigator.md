---
title: Selezione, valutazione e corrispondenza di dati XML con XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e503c5be7bb23d15c2b11ef1b31c2eeb5e4d5aa8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="699c9-102">Selezione, valutazione e corrispondenza di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="699c9-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce metodi per selezionare nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> usando una query XPath, valutare ed esaminare i risultati di un'espressione XPath e determinare se un nodo in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> corrisponde a un'espressione XPath specifica.</span><span class="sxs-lookup"><span data-stu-id="699c9-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="699c9-104">Questi e altri concetti relativi alla selezione, alla valutazione e alla corrispondenza di nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> vengono descritti negli argomenti che seguono.</span><span class="sxs-lookup"><span data-stu-id="699c9-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="699c9-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="699c9-105">In This Section</span></span>  
 [<span data-ttu-id="699c9-106">Selezionare dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-106">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="699c9-107">Viene descritto il set dei metodi della classe <xref:System.Xml.XPath.XPathNavigator> usati per selezionare un set di nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> usando un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="699c9-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="699c9-108">Valutare espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-108">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="699c9-109">Viene descritto il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> della classe <xref:System.Xml.XPath.XPathNavigator> usato per valutare un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="699c9-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="699c9-110">Corrispondenza di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-110">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="699c9-111">Viene descritto il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> della classe <xref:System.Xml.XPath.XPathNavigator> usato per valutare un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="699c9-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="699c9-112">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="699c9-112">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="699c9-113">Vengono descritti i tipi di nodo riconosciuti in una query XPath.</span><span class="sxs-lookup"><span data-stu-id="699c9-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="699c9-114">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="699c9-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 <span data-ttu-id="699c9-115">Viene descritto l'uso degli spazi dei nomi in una query XPath.</span><span class="sxs-lookup"><span data-stu-id="699c9-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="699c9-116">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="699c9-116">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)  
 <span data-ttu-id="699c9-117">Viene descritta la classe <xref:System.Xml.XPath.XPathExpression> che rappresenta una query XPath compilata.</span><span class="sxs-lookup"><span data-stu-id="699c9-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699c9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="699c9-118">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="699c9-119">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="699c9-119">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="699c9-120">Lettura di dati XML con XPathDocument e XmlDocument</span><span class="sxs-lookup"><span data-stu-id="699c9-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="699c9-121">Accesso ai dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-121">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="699c9-122">Modifica di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-122">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="699c9-123">Convalida dello schema con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="699c9-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
