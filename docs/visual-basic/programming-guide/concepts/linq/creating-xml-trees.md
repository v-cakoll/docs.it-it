---
title: Creazione di strutture ad albero XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: e86ba12b-17de-4579-81bb-66322b84cfbe
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
ms.openlocfilehash: c60746a3da6255e4c245febf55151b41186a75b7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-trees-visual-basic"></a><span data-ttu-id="e85f3-102">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-102">Creating XML Trees (Visual Basic)</span></span>
<span data-ttu-id="e85f3-103">Una delle attività più comuni di XML è la creazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="e85f3-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="e85f3-104">In questa sezione vengono descritti diversi modi per crearle.</span><span class="sxs-lookup"><span data-stu-id="e85f3-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e85f3-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e85f3-105">In This Section</span></span>  
  
|<span data-ttu-id="e85f3-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="e85f3-106">Topic</span></span>|<span data-ttu-id="e85f3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e85f3-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e85f3-108">Costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-108">Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="e85f3-109">Viene fornita una panoramica sulla costruzione funzionale in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e85f3-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="e85f3-110">La costruzione funzionale consente di creare tutta o parte della struttura ad albero XML in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="e85f3-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="e85f3-111">In questo argomento viene inoltre illustrato come incorporare query durante la costruzione di una struttura ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="e85f3-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="e85f3-112">Introduzione ai valori letterali XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e85f3-112">Introduction to XML Literals in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)|<span data-ttu-id="e85f3-113">Fornisce una rapida introduzione alla creazione di alberi in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mediante valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="e85f3-113">Provides a quick introduction to creating trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using XML literals.</span></span> <span data-ttu-id="e85f3-114">Questo argomento include collegamenti alla documentazione di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relativa ai valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="e85f3-114">This topic includes links to the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] documentation of XML literals.</span></span>|  
|[<span data-ttu-id="e85f3-115">Clonazione e Collegamento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-115">Cloning vs. Attaching (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="e85f3-116">Viene illustrata la differenza tra l'aggiunta di nodi da un albero XML esistente, in cui i nodi vengono prima clonati e poi aggiunti, e l'aggiunta di nodi senza elemento padre, in cui i nodi vengono semplicemente collegati.</span><span class="sxs-lookup"><span data-stu-id="e85f3-116">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="e85f3-117">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-117">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="e85f3-118">Viene illustrato come analizzare il codice XML da una vasta gamma di origini.</span><span class="sxs-lookup"><span data-stu-id="e85f3-118">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="e85f3-119">si basa su <xref:System.Xml.XmlReader>, che consente di analizzare il codice XML.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="e85f3-119"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="e85f3-120">Procedura: popolare una struttura ad albero XML con un XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-120">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="e85f3-121">Viene illustrato come popolare una struttura ad albero XML utilizzando un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="e85f3-121">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="e85f3-122">Procedura: eseguire la convalida tramite XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-122">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="e85f3-123">Viene illustrato come convalidare una struttura ad albero XML usando XSD.</span><span class="sxs-lookup"><span data-stu-id="e85f3-123">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="e85f3-124">Contenuto valido di oggetti XElement e XDocument</span><span class="sxs-lookup"><span data-stu-id="e85f3-124">Valid Content of XElement and XDocument Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects.md)|<span data-ttu-id="e85f3-125">Vengono illustrati gli argomenti validi che è possibile passare ai costruttori e i metodi usati per aggiungere contenuto a elementi e documenti.</span><span class="sxs-lookup"><span data-stu-id="e85f3-125">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e85f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e85f3-126">See Also</span></span>  
 [<span data-ttu-id="e85f3-127">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e85f3-127">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
