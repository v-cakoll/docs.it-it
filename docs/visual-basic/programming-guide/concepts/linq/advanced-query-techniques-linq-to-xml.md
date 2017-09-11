---
title: Tecniche di Query (LINQ to XML) avanzate (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 79be877c-fadc-4dfb-9f03-426082b13656
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6983fa5b9637210bb3c56e8f693eb4f956dab0a8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="advanced-query-techniques-linq-to-xml-visual-basic"></a><span data-ttu-id="c8e18-102">Tecniche di Query (LINQ to XML) avanzate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-102">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c8e18-103">Contenuto della sezione vengono forniti esempi di tecniche di query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] più avanzate.</span><span class="sxs-lookup"><span data-stu-id="c8e18-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8e18-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c8e18-104">In This Section</span></span>  
  
|<span data-ttu-id="c8e18-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="c8e18-105">Topic</span></span>|<span data-ttu-id="c8e18-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8e18-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c8e18-107">Procedura: unire due raccolte (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-107">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="c8e18-108">Viene illustrato come usare la clausola `Join` per sfruttare le relazioni nei dati XML.</span><span class="sxs-lookup"><span data-stu-id="c8e18-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="c8e18-109">Procedura: creare una gerarchia tramite raggruppamento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-109">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="c8e18-110">Viene illustrato come raggruppare dati e quindi generare codice XML basato sul raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="c8e18-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="c8e18-111">Procedura: eseguire una Query LINQ to XML tramite XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-111">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="c8e18-112">Viene illustrato come recuperare raccolte basate su query XPath.</span><span class="sxs-lookup"><span data-stu-id="c8e18-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="c8e18-113">Procedura: scrivere un LINQ nel metodo Axis XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-113">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="c8e18-114">Viene illustrato come scrivere un metodo [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] dell'asse.</span><span class="sxs-lookup"><span data-stu-id="c8e18-114">Shows how to write a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axis method.</span></span>|  
|[<span data-ttu-id="c8e18-115">Procedura: elencare tutti i nodi in una struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-115">How to: List All Nodes in a Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="c8e18-116">Viene presentato un metodo di utilità che elenca tutti i nodi di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="c8e18-116">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="c8e18-117">Questa funzione è utile per il debug di codice che modifica un albero XML.</span><span class="sxs-lookup"><span data-stu-id="c8e18-117">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="c8e18-118">Procedura: recuperare paragrafi da un documento Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-118">How to: Retrieve Paragraphs from an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="c8e18-119">Viene presentato codice con cui viene aperto un documento Office Open XML, quindi vengono recuperati i paragrafi in una raccolta di oggetti XElement, il testo dei paragrafi e gli stili dei paragrafi.</span><span class="sxs-lookup"><span data-stu-id="c8e18-119">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="c8e18-120">Procedura: modificare un documento Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-120">How to: Modify an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="c8e18-121">Viene presentato codice con cui viene aperto, modificato e salvato un documento Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="c8e18-121">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="c8e18-122">Procedura: popolare una struttura ad albero XML dal File System (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-122">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="c8e18-123">Viene presentato codice con cui viene creato un albero XML dal file system.</span><span class="sxs-lookup"><span data-stu-id="c8e18-123">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8e18-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8e18-124">See Also</span></span>  
 [<span data-ttu-id="c8e18-125">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e18-125">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
