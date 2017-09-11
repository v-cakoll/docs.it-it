---
title: LINQ to XML Annotations2 | Documenti di Microsoft
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 97f5386630ba687e4401ee0cfb70f7170e273a53
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="7714a-102">Annotazioni LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7714a-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="7714a-103">Le annotazioni [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consentono di associare qualsiasi oggetto arbitrario di qualsiasi tipo arbitrario a qualsiasi componente XML di una struttura ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="7714a-103">Annotations in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="7714a-104">Per aggiungere un'annotazione a un componente XML, ad esempio un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>, si chiama il <xref:System.Xml.Linq.XObject.AddAnnotation%2A>(metodo).</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7714a-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="7714a-105">Le annotazioni vengono recuperate in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="7714a-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="7714a-106">Si noti che le annotazioni non fanno parte dell'infoset XML; non sono serializzate né deserializzate.</span><span class="sxs-lookup"><span data-stu-id="7714a-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7714a-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="7714a-107">Methods</span></span>  
 <span data-ttu-id="7714a-108">Con le annotazioni è possibile usare i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7714a-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="7714a-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="7714a-109">Method</span></span>|<span data-ttu-id="7714a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7714a-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7714a-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A></span><span class="sxs-lookup"><span data-stu-id="7714a-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></span></span>|<span data-ttu-id="7714a-112">Aggiunge un oggetto all'elenco di annotazioni di un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="7714a-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="7714a-113"><xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A></span><span class="sxs-lookup"><span data-stu-id="7714a-113"><xref:System.Xml.Linq.XObject.Annotation%2A></span></span>|<span data-ttu-id="7714a-114">Ottiene il primo oggetto annotazione del tipo specificato da un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="7714a-114">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="7714a-115"><xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A></span><span class="sxs-lookup"><span data-stu-id="7714a-115"><xref:System.Xml.Linq.XObject.Annotations%2A></span></span>|<span data-ttu-id="7714a-116">Ottiene una raccolta di annotazioni del tipo specificato per un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="7714a-116">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="7714a-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span><span class="sxs-lookup"><span data-stu-id="7714a-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span></span>|<span data-ttu-id="7714a-118">Rimuove le annotazioni del tipo specificato da un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="7714a-118">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7714a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7714a-119">See Also</span></span>  
 [<span data-ttu-id="7714a-120">LINQ to XML (Visual Basic) di programmazione avanzata</span><span class="sxs-lookup"><span data-stu-id="7714a-120">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
