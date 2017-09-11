---
title: Proiezioni e trasformazioni (LINQ to XML) (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 723685400aadbf883d7ad939e6a1dd5bdeb7ba09
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="3347e-102">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3347e-103">In questa sezione vengono forniti esempi di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] proiezioni e trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="3347e-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3347e-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3347e-104">In This Section</span></span>  
  
|<span data-ttu-id="3347e-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="3347e-105">Topic</span></span>|<span data-ttu-id="3347e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3347e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3347e-107">Procedura: utilizzare dizionari in LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="3347e-108">Viene illustrato come trasformare dizionari in codice XML e viceversa.</span><span class="sxs-lookup"><span data-stu-id="3347e-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="3347e-109">Procedura: trasformare la forma di una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="3347e-110">Viene illustrato come trasformare la forma di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="3347e-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="3347e-111">Procedura: controllare il tipo di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="3347e-112">Viene illustrato come controllare il tipo di una query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3347e-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="3347e-113">Procedura: proiettare un nuovo tipo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="3347e-114">Viene illustrato come proiettare una raccolta di tipo definito dall'utente da una query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3347e-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="3347e-115">Procedura: proiettare un oggetto grafico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-115">How to: Project an Object Graph (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="3347e-116">Viene illustrato come proiettare un oggetto grafico più complesso da una query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3347e-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="3347e-117">Procedura: proiettare un tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="3347e-118">Viene illustrato come proiettare una raccolta di oggetti anonimi da una query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3347e-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="3347e-119">Procedura: generare file di testo da XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="3347e-120">Viene illustrato come trasformare un file XML in un file di testo non XML.</span><span class="sxs-lookup"><span data-stu-id="3347e-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="3347e-121">Procedura: generare XML da file CSV (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="3347e-122">Viene spiegato come usare [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] per analizzare un file CSV e generare codice XML da esso.</span><span class="sxs-lookup"><span data-stu-id="3347e-122">Shows how to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3347e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3347e-123">See Also</span></span>  
 [<span data-ttu-id="3347e-124">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3347e-124">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
