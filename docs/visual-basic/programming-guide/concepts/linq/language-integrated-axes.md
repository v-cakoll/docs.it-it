---
title: Assi integrati nel linguaggio in Visual Basic (LINQ to XML) | Documenti di Microsoft
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
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7ca88aed0772f4fb93ab561af4bd9a1129cbf3c5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="55e6f-102">Assi integrati nel linguaggio in Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="55e6f-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="55e6f-103">Questa sezione vengono descritte le funzionalità incorporate nel [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] linguaggio per semplificare l'accesso a XML.</span><span class="sxs-lookup"><span data-stu-id="55e6f-103">This section describes features built directly into the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="55e6f-104">Questi assi [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] integrati vengono usati in molti degli esempi della documentazione relativa a LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="55e6f-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55e6f-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="55e6f-105">In This Section</span></span>  
  
|<span data-ttu-id="55e6f-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="55e6f-106">Topic</span></span>|<span data-ttu-id="55e6f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55e6f-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="55e6f-108">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="55e6f-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="55e6f-109">Fornisce l'accesso agli elementi figlio di uno dei seguenti: un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto, una raccolta di <xref:System.Xml.Linq.XElement>oggetti o una raccolta di <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="55e6f-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="55e6f-110">Questo asse è equivalente a di <xref:System.Xml.Linq.XContainer.Elements%2A>asse.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="55e6f-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="55e6f-111">Proprietà axis descendant XML</span><span class="sxs-lookup"><span data-stu-id="55e6f-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="55e6f-112">Fornisce l'accesso ai discendenti di uno dei seguenti: un <xref:System.Xml.Linq.XElement>oggetto, un <xref:System.Xml.Linq.XDocument>oggetto o una raccolta di <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="55e6f-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="55e6f-113">Questo asse è equivalente a di <xref:System.Xml.Linq.XContainer.Descendants%2A>asse.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="55e6f-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="55e6f-114">Proprietà axis dell'attributo XML</span><span class="sxs-lookup"><span data-stu-id="55e6f-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="55e6f-115">Fornisce l'accesso a un attributo di un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="55e6f-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="55e6f-116">Questo asse è quasi equivalente a di <xref:System.Xml.Linq.XElement.Attribute%2A>asse.</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="55e6f-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="55e6f-117">Questo asse è diverso da di <xref:System.Xml.Linq.XElement.Attribute%2A>asse in quanto restituisce il valore dell'attributo, non un <xref:System.Xml.Linq.XAttribute>oggetto.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="55e6f-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="55e6f-118">Proprietà dell'indicizzatore di estensione</span><span class="sxs-lookup"><span data-stu-id="55e6f-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="55e6f-119">Fornisce l'accesso ai singoli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="55e6f-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55e6f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55e6f-120">See Also</span></span>  
 [<span data-ttu-id="55e6f-121">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55e6f-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
