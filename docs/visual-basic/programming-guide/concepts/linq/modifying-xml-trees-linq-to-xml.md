---
title: Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ff0f95afec6248ba7f64812be5f9906c90496d9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="936a5-102">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="936a5-103"> è un archivio in memoria usato per un albero XML.</span><span class="sxs-lookup"><span data-stu-id="936a5-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="936a5-104">Dopo aver caricato o analizzato un albero XML da un'origine [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consente di modificare tale struttura sul posto e quindi di serializzarla, salvandola in un file o inviandola a un server remoto.</span><span class="sxs-lookup"><span data-stu-id="936a5-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="936a5-105">Quando si modifica un albero sul posto, vengono usati determinati metodi, ad esempio <xref:System.Xml.Linq.XContainer.Add%2A>.</xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="936a5-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="936a5-106">È tuttavia disponibile un altro approccio che prevede l'uso della costruzione funzionale per generare un nuovo albero con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="936a5-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="936a5-107">A seconda dei tipi di modifiche che è necessario apportate all'albero XML, e a seconda delle dimensioni della struttura, questo approccio può risultare più affidabile e più semplice da sviluppare.</span><span class="sxs-lookup"><span data-stu-id="936a5-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="936a5-108">Nel primo argomento di questa sezione vengono messi a confronto questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="936a5-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="936a5-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="936a5-109">In This Section</span></span>  
  
|<span data-ttu-id="936a5-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="936a5-110">Topic</span></span>|<span data-ttu-id="936a5-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="936a5-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="936a5-112">Differenze tra la modifica dell'albero XML in memoria e la Costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="936a5-113">La modifica di una struttura ad albero XML in memoria viene messa a confronto con la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="936a5-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="936a5-114">Aggiunta di elementi, attributi e nodi a una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="936a5-115">Vengono fornite informazioni sull'aggiunta di elementi, attributi o nodi a un albero XML.</span><span class="sxs-lookup"><span data-stu-id="936a5-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="936a5-116">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="936a5-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="936a5-117">Vengono fornite informazioni sulla modifica di elementi, attributi o nodi esistenti.</span><span class="sxs-lookup"><span data-stu-id="936a5-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="936a5-118">Rimozione di elementi, attributi e nodi da una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="936a5-119">Vengono fornite informazioni sulla rimozione di elementi, attributi o nodi da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="936a5-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="936a5-120">Gestione di coppie nome/valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="936a5-121">Viene descritto come gestire le informazioni dell'applicazione che è preferibile mantenere come coppie nome/valore, ad esempio informazioni di configurazione o impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="936a5-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="936a5-122">Procedura: modificare il Namespace per una struttura ad albero XML intero (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="936a5-123">Viene illustrato come spostare un albero XML da uno spazio dei nomi a un altro.</span><span class="sxs-lookup"><span data-stu-id="936a5-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="936a5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="936a5-124">See Also</span></span>  
 [<span data-ttu-id="936a5-125">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="936a5-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
