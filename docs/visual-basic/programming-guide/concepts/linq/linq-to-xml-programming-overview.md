---
title: LINQ to Cenni preliminari sulla programmazione XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: a7c07d0a-1fae-4610-ae51-56dd7075cc14
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 57d52b1bc46263e4e8e662be6a83bf4718813b43
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-programming-overview-visual-basic"></a><span data-ttu-id="2ca9e-102">LINQ to Cenni preliminari sulla programmazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-102">LINQ to XML Programming Overview (Visual Basic)</span></span>
<span data-ttu-id="2ca9e-103">In questi argomenti vengono fornite informazioni preliminari di alto livello sulle classi [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], nonché informazioni dettagliate sulle tre classi più importanti.</span><span class="sxs-lookup"><span data-stu-id="2ca9e-103">These topics provide high-level overview information about the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes, as well as detailed information about three of the most important classes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ca9e-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2ca9e-104">In This Section</span></span>  
  
|<span data-ttu-id="2ca9e-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="2ca9e-105">Topic</span></span>|<span data-ttu-id="2ca9e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ca9e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2ca9e-107">Programmazione Programmazione procedurale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-107">Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-vs-procedural-programming-linq-to-xml.md)|<span data-ttu-id="2ca9e-108">Viene fornita una panoramica di alto livello dei due principali approcci alla scrittura di applicazioni LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="2ca9e-108">Provides a high level view of the two principle approaches to writing LINQ to XML applications.</span></span>|  
|[<span data-ttu-id="2ca9e-109">LINQ to XML panoramica delle classi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-109">LINQ to XML Classes Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-classes-overview.md)|<span data-ttu-id="2ca9e-110">Vengono forniti cenni preliminari sulle classi di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ca9e-110">Provides an overview of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes.</span></span>|  
|[<span data-ttu-id="2ca9e-111">Cenni preliminari sulla classe XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-111">XElement Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md)|<span data-ttu-id="2ca9e-112">Introduce la <xref:System.Xml.Linq.XElement>classe, che rappresenta elementi XML.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2ca9e-112">Introduces the <xref:System.Xml.Linq.XElement> class, which represents XML elements.</span></span> <span data-ttu-id="2ca9e-113"><xref:System.Xml.Linq.XElement>è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gerarchia delle classi.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2ca9e-113"><xref:System.Xml.Linq.XElement> is one of the fundamental classes in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] class hierarchy.</span></span>|  
|[<span data-ttu-id="2ca9e-114">Cenni preliminari sulla classe XAttribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-114">XAttribute Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md)|<span data-ttu-id="2ca9e-115">Introduce la <xref:System.Xml.Linq.XAttribute>classe, che rappresenta gli attributi XML.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="2ca9e-115">Introduces the <xref:System.Xml.Linq.XAttribute> class, which represents XML attributes.</span></span>|  
|[<span data-ttu-id="2ca9e-116">Cenni preliminari sulla classe XDocument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-116">XDocument Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)|<span data-ttu-id="2ca9e-117">Introduce la <xref:System.Xml.Linq.XDocument>classe, che rappresenta documenti XML.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="2ca9e-117">Introduces the <xref:System.Xml.Linq.XDocument> class, which represents XML documents.</span></span>|  
|[<span data-ttu-id="2ca9e-118">Procedura: compilare in LINQ to XML esempi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-118">How to: Build LINQ to XML Examples (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-build-linq-to-xml-examples.md)|<span data-ttu-id="2ca9e-119">Contiene il `Imports` istruzioni necessari per la creazione di esempi di LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="2ca9e-119">Contains the `Imports` statements that are required to build the LINQ to XML examples.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ca9e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ca9e-120">See Also</span></span>  
 [<span data-ttu-id="2ca9e-121">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ca9e-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
