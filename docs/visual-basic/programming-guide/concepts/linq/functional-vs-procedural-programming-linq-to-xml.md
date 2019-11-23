---
title: Programmazione funzionale e procedurale (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
ms.openlocfilehash: 3d1e3cf01b30454d29836f176afcd39cb2b55b73
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353407"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a><span data-ttu-id="f0733-102">Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0733-102">Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f0733-103">Sono disponibili diversi tipi di applicazioni XML:</span><span class="sxs-lookup"><span data-stu-id="f0733-103">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="f0733-104">In alcune applicazioni da documenti XML di origine vengono prodotti nuovi documenti XML con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="f0733-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="f0733-105">In alcune applicazioni da documenti XML di origine vengono prodotti documenti risultanti in un formato completamente diverso, ad esempio file di testo CSV o HTML.</span><span class="sxs-lookup"><span data-stu-id="f0733-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="f0733-106">In alcune applicazioni da documenti XML di origine vengono inseriti record in un database.</span><span class="sxs-lookup"><span data-stu-id="f0733-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="f0733-107">In alcune applicazioni dai dati di un'altra origine, ad esempio un database, vengono creati documenti XML.</span><span class="sxs-lookup"><span data-stu-id="f0733-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="f0733-108">Quelli elencati non sono tutti i tipi di applicazioni XML disponibili, ma sono rappresentativi dei tipi di funzionalità che i programmatori XML devono implementare.</span><span class="sxs-lookup"><span data-stu-id="f0733-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="f0733-109">Con tutti questi tipi di applicazioni, gli sviluppatori possono adottare due approcci completamente diversi:</span><span class="sxs-lookup"><span data-stu-id="f0733-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="f0733-110">Costruzione funzionale usando un approccio dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="f0733-110">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="f0733-111">Modifica dell'albero XML in memoria usando codice procedurale.</span><span class="sxs-lookup"><span data-stu-id="f0733-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="f0733-112">In LINQ to XML sono supportati entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="f0733-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="f0733-113">Quando si usa l'approccio funzionale, vengono scritte trasformazioni che dai documenti di origine generano documenti completamente nuovi con la forma desiderata.</span><span class="sxs-lookup"><span data-stu-id="f0733-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="f0733-114">Quando si modifica un albero XML sul posto, viene scritto un codice che attraversa e si sposta attraverso i nodi in un albero XML in memoria, inserendo, eliminando e modificando i nodi secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="f0733-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="f0733-115">È possibile usare LINQ to XML con uno di questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="f0733-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="f0733-116">Si usano le stesse classe e in alcuni casi gli stessi metodi.</span><span class="sxs-lookup"><span data-stu-id="f0733-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="f0733-117">Tuttavia, la struttura e gli obiettivi dei due approcci sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="f0733-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="f0733-118">In situazioni diverse, ad esempio, un approccio offre in genere prestazioni più elevate dell'altro e usa una quantità maggiore o minore di memoria.</span><span class="sxs-lookup"><span data-stu-id="f0733-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="f0733-119">Inoltre, un approccio sarà più facile da scrivere dell'altro e produrrà codice più facilmente gestibile.</span><span class="sxs-lookup"><span data-stu-id="f0733-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="f0733-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="f0733-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md).</span></span>  
  
 <span data-ttu-id="f0733-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f0733-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0733-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0733-122">See also</span></span>

- [<span data-ttu-id="f0733-123">LINQ to XML Programming Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0733-123">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
