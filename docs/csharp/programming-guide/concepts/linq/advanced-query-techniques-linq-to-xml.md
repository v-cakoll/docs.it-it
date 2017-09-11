---
title: Tecniche di query avanzate (LINQ to XML) (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 028d978e-215b-4d50-ba70-adce0659386d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91460ed99854edda829503d451728c4274d7ba2b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="advanced-query-techniques-linq-to-xml-c"></a><span data-ttu-id="aa5e2-102">Tecniche di query avanzate (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-102">Advanced Query Techniques (LINQ to XML) (C#)</span></span>
<span data-ttu-id="aa5e2-103">Contenuto della sezione vengono forniti esempi di tecniche di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] più avanzate.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa5e2-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="aa5e2-104">In This Section</span></span>  
  
|<span data-ttu-id="aa5e2-105">Argomento</span><span class="sxs-lookup"><span data-stu-id="aa5e2-105">Topic</span></span>|<span data-ttu-id="aa5e2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa5e2-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="aa5e2-107">Procedura: Unire due raccolte (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-107">How to: Join Two Collections (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="aa5e2-108">Viene illustrato come usare la clausola `Join` per sfruttare le relazioni nei dati XML.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="aa5e2-109">Procedura: Creare una gerarchia tramite il raggruppamento (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-109">How to: Create Hierarchy Using Grouping (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="aa5e2-110">Viene illustrato come raggruppare dati e quindi generare codice XML basato sul raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="aa5e2-111">Procedura: Eseguire una query in LINQ to XML tramite XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-111">How to: Query LINQ to XML Using XPath (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="aa5e2-112">Viene illustrato come recuperare raccolte basate su query XPath.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="aa5e2-113">Procedura: Scrivere un metodo dell'asse LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-113">How to: Write a LINQ to XML Axis Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="aa5e2-114">Viene illustrato come scrivere un metodo [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dell'asse.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="aa5e2-115">Procedura: Eseguire trasformazioni del flusso di testo in XML (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-115">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transformations-of-text-to-xml.md)|<span data-ttu-id="aa5e2-116">Viene illustrato come trasformare file di testo di dimensioni molto grandi in XML durante la gestione di un footprint di memoria di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-116">Shows how to transform very large text files into XML while maintaining a small memory footprint.</span></span>|  
|[<span data-ttu-id="aa5e2-117">Procedura: Elencare tutti i nodi in un albero (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-117">How to: List All Nodes in a Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="aa5e2-118">Viene presentato un metodo di utilità che elenca tutti i nodi di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-118">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="aa5e2-119">Questa funzione è utile per il debug di codice che modifica un albero XML.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-119">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="aa5e2-120">Procedura: Recuperare paragrafi da un documento Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-120">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="aa5e2-121">Viene presentato codice con cui viene aperto un documento Office Open XML, quindi vengono recuperati i paragrafi in una raccolta di oggetti XElement, il testo dei paragrafi e gli stili dei paragrafi.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-121">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="aa5e2-122">Procedura: Modificare un documento Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-122">How to: Modify an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="aa5e2-123">Viene presentato codice con cui viene aperto, modificato e salvato un documento Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-123">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="aa5e2-124">Procedura: Popolare un albero XML dal file system (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-124">How to: Populate an XML Tree from the File System (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="aa5e2-125">Viene presentato codice con cui viene creato un albero XML dal file system.</span><span class="sxs-lookup"><span data-stu-id="aa5e2-125">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa5e2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa5e2-126">See Also</span></span>  
 [<span data-ttu-id="aa5e2-127">Esecuzione di query su strutture ad albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="aa5e2-127">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

