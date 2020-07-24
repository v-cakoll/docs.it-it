---
title: Programmazione funzionale e procedurale (LINQ to XML) (C#)
description: Per l'elaborazione di XML, LINQ to XML supporta la modifica della struttura ad albero XML in memoria e procedurale e una costruzione funzionale che usa un approccio dichiarativo.
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e19f9311c56f4fe2c5e7e5f228aca6c03c6fe04d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103658"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="d2399-103">Programmazione funzionale e procedurale (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="d2399-103">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="d2399-104">Sono disponibili diversi tipi di applicazioni XML:</span><span class="sxs-lookup"><span data-stu-id="d2399-104">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="d2399-105">In alcune applicazioni da documenti XML di origine vengono prodotti nuovi documenti XML con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="d2399-105">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="d2399-106">In alcune applicazioni da documenti XML di origine vengono prodotti documenti risultanti in un formato completamente diverso, ad esempio file di testo CSV o HTML.</span><span class="sxs-lookup"><span data-stu-id="d2399-106">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="d2399-107">In alcune applicazioni da documenti XML di origine vengono inseriti record in un database.</span><span class="sxs-lookup"><span data-stu-id="d2399-107">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="d2399-108">In alcune applicazioni dai dati di un'altra origine, ad esempio un database, vengono creati documenti XML.</span><span class="sxs-lookup"><span data-stu-id="d2399-108">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="d2399-109">Quelli elencati non sono tutti i tipi di applicazioni XML disponibili, ma sono rappresentativi dei tipi di funzionalità che i programmatori XML devono implementare.</span><span class="sxs-lookup"><span data-stu-id="d2399-109">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="d2399-110">Con tutti questi tipi di applicazioni, gli sviluppatori possono adottare due approcci completamente diversi:</span><span class="sxs-lookup"><span data-stu-id="d2399-110">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="d2399-111">Costruzione funzionale usando un approccio dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="d2399-111">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="d2399-112">Modifica dell'albero XML in memoria usando codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="d2399-112">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="d2399-113">In LINQ to XML sono supportati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="d2399-113">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="d2399-114">Quando si usa l'approccio funzionale, vengono scritte trasformazioni che dai documenti di origine generano documenti completamente nuovi con la forma desiderata.</span><span class="sxs-lookup"><span data-stu-id="d2399-114">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="d2399-115">Quando si modifica un albero XML sul posto, viene scritto un codice che attraversa e si sposta attraverso i nodi in un albero XML in memoria, inserendo, eliminando e modificando i nodi secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="d2399-115">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="d2399-116">È possibile usare LINQ to XML con uno di questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="d2399-116">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="d2399-117">Si usano le stesse classe e in alcuni casi gli stessi metodi.</span><span class="sxs-lookup"><span data-stu-id="d2399-117">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="d2399-118">Tuttavia, la struttura e gli obiettivi dei due approcci sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="d2399-118">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="d2399-119">In situazioni diverse, ad esempio, un approccio offre in genere prestazioni più elevate dell'altro e usa una quantità maggiore o minore di memoria.</span><span class="sxs-lookup"><span data-stu-id="d2399-119">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="d2399-120">Inoltre, un approccio sarà più facile da scrivere dell'altro e produrrà codice più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="d2399-120">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="d2399-121">Per visualizzare i due approcci contrapposti, vedere la pagina relativa alla [modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d2399-121">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d2399-122">Per un'esercitazione sulla scrittura delle trasformazioni funzionali, vedere [Trasformazioni funzionali pure di XML (C#)](./introduction-to-pure-functional-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="d2399-122">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](./introduction-to-pure-functional-transformations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2399-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2399-123">See also</span></span>

- [<span data-ttu-id="d2399-124">Panoramica della programmazione con LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="d2399-124">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
