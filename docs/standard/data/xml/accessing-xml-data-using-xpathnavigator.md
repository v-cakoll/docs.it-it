---
title: Accesso ai dati XML con XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9e0b6d8545fccf9148aaa317b6d936c5c9f02775
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="c7703-102">Accesso ai dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="c7703-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce metodi per esplorare i nodi, estrarre dati XML e accedere a dati XML tipizzati in modo sicuro in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c7703-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7703-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c7703-104">In This Section</span></span>  
 [<span data-ttu-id="c7703-105">Navigazione del set di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="c7703-106">Vengono descritti i metodi di navigazione di set di nodi della classe <xref:System.Xml.XPath.XPathNavigator> usati per esplorare i nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c7703-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="c7703-107">Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="c7703-108">Vengono descritti i metodi di navigazione degli attributi e dello spazio dei nomi della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c7703-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="c7703-109">Estrarre dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="c7703-110">Vengono descritti i diversi metodi per l'estrazione dei dati XML da un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c7703-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="c7703-111">Accesso a dati XML fortemente tipizzati con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="c7703-112">Viene descritto l'accesso a dati XML tipizzati in modo sicuro in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> mediante la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c7703-112">Describes accessing strongly-typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="c7703-113">Funzioni e variabili definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="c7703-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="c7703-114">Viene descritta l'implementazione di una classe <xref:System.Xml.Xsl.XsltContext> personalizzata insieme alle interfacce <xref:System.Xml.Xsl.IXsltContextFunction> e <xref:System.Xml.Xsl.IXsltContextVariable> che supportano le funzioni di estensione e le variabili.</span><span class="sxs-lookup"><span data-stu-id="c7703-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7703-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7703-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="c7703-116">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="c7703-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="c7703-117">Lettura di dati XML con XPathDocument e XmlDocument</span><span class="sxs-lookup"><span data-stu-id="c7703-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="c7703-118">Selezione, valutazione e corrispondenza di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c7703-119">Modifica di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c7703-120">Convalida dello schema con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c7703-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
