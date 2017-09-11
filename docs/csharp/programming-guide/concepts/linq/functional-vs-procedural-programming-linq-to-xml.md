---
title: Programmazione funzionale e programmazione procedurale (LINQ to XML) (C#)
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
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0920206524f9ff93a6be2acdb230f59c244840f7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="b68a9-102">Programmazione funzionale e programmazione procedurale (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b68a9-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b68a9-103">Sono disponibili diversi tipi di applicazioni XML:</span><span class="sxs-lookup"><span data-stu-id="b68a9-103">There are various types of XML applications:</span></span>  
  
-   <span data-ttu-id="b68a9-104">In alcune applicazioni da documenti XML di origine vengono prodotti nuovi documenti XML con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="b68a9-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
-   <span data-ttu-id="b68a9-105">In alcune applicazioni da documenti XML di origine vengono prodotti documenti risultanti in un formato completamente diverso, ad esempio file di testo CSV o HTML.</span><span class="sxs-lookup"><span data-stu-id="b68a9-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
-   <span data-ttu-id="b68a9-106">In alcune applicazioni da documenti XML di origine vengono inseriti record in un database.</span><span class="sxs-lookup"><span data-stu-id="b68a9-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
-   <span data-ttu-id="b68a9-107">In alcune applicazioni dai dati di un'altra origine, ad esempio un database, vengono creati documenti XML.</span><span class="sxs-lookup"><span data-stu-id="b68a9-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="b68a9-108">Quelli elencati non sono tutti i tipi di applicazioni XML disponibili, ma sono rappresentativi dei tipi di funzionalità che i programmatori XML devono implementare.</span><span class="sxs-lookup"><span data-stu-id="b68a9-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="b68a9-109">Con tutti questi tipi di applicazioni, gli sviluppatori possono adottare due approcci completamente diversi:</span><span class="sxs-lookup"><span data-stu-id="b68a9-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
-   <span data-ttu-id="b68a9-110">Costruzione funzionale usando un approccio dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="b68a9-110">Functional construction using a declarative approach.</span></span>  
  
-   <span data-ttu-id="b68a9-111">Modifica dell'albero XML in memoria usando codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="b68a9-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="b68a9-112">In LINQ to XML sono supportati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="b68a9-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="b68a9-113">Quando si usa l'approccio funzionale, vengono scritte trasformazioni che dai documenti di origine generano documenti completamente nuovi con la forma desiderata.</span><span class="sxs-lookup"><span data-stu-id="b68a9-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="b68a9-114">Quando si modifica un albero XML sul posto, viene scritto un codice che attraversa e si sposta attraverso i nodi in un albero XML in memoria, inserendo, eliminando e modificando i nodi secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="b68a9-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="b68a9-115">È possibile usare LINQ to XML con uno di questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="b68a9-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="b68a9-116">Si usano le stesse classe e in alcuni casi gli stessi metodi.</span><span class="sxs-lookup"><span data-stu-id="b68a9-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="b68a9-117">Tuttavia, la struttura e gli obiettivi dei due approcci sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="b68a9-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="b68a9-118">In situazioni diverse, ad esempio, un approccio offre in genere prestazioni più elevate dell'altro e usa una quantità maggiore o minore di memoria.</span><span class="sxs-lookup"><span data-stu-id="b68a9-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="b68a9-119">Inoltre, un approccio sarà più facile da scrivere dell'altro e produrrà codice più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="b68a9-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="b68a9-120">Per un confronto tra i due approcci, vedere [Differenze tra la modifica dell'albero XML in memoria e la costruzione funzionale (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b68a9-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b68a9-121">Per un'esercitazione sulla scrittura delle trasformazioni funzionali, vedere [Trasformazioni funzionali pure di XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b68a9-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68a9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b68a9-122">See Also</span></span>  
 [<span data-ttu-id="b68a9-123">Panoramica della programmazione con LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b68a9-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

