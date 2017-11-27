---
title: Modifica degli alberi XML (LINQ to XML) (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de66788186f3ffd09560d8eacdebbbaa5edf067c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="6f732-102">Modifica degli alberi XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="6f732-103"> è un archivio in memoria usato per un albero XML.</span><span class="sxs-lookup"><span data-stu-id="6f732-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="6f732-104">Dopo aver caricato o analizzato un albero XML da un'origine, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di modificare l'albero sul posto e quindi di serializzarlo, salvandolo in un file o inviandolo a un server remoto.</span><span class="sxs-lookup"><span data-stu-id="6f732-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="6f732-105">Per la modifica di un albero sul posto vengono usati determinati metodi, ad esempio <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f732-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="6f732-106">È tuttavia disponibile un altro approccio che prevede l'uso della costruzione funzionale per generare un nuovo albero con una forma diversa.</span><span class="sxs-lookup"><span data-stu-id="6f732-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="6f732-107">A seconda dei tipi di modifiche che è necessario apportate all'albero XML, e a seconda delle dimensioni della struttura, questo approccio può risultare più affidabile e più semplice da sviluppare.</span><span class="sxs-lookup"><span data-stu-id="6f732-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="6f732-108">Nel primo argomento di questa sezione vengono messi a confronto questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="6f732-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f732-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6f732-109">In This Section</span></span>  
  
|<span data-ttu-id="6f732-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="6f732-110">Topic</span></span>|<span data-ttu-id="6f732-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f732-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6f732-112">Differenze tra la modifica dell'albero XML in memoria e la Costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="6f732-113">La modifica di una struttura ad albero XML in memoria viene messa a confronto con la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="6f732-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="6f732-114">Aggiunta di elementi, attributi e nodi a una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="6f732-115">Vengono fornite informazioni sull'aggiunta di elementi, attributi o nodi a un albero XML.</span><span class="sxs-lookup"><span data-stu-id="6f732-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="6f732-116">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="6f732-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="6f732-117">Vengono fornite informazioni sulla modifica di elementi, attributi o nodi esistenti.</span><span class="sxs-lookup"><span data-stu-id="6f732-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="6f732-118">Rimozione di elementi, attributi e nodi da un albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="6f732-119">Vengono fornite informazioni sulla rimozione di elementi, attributi o nodi da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="6f732-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="6f732-120">Gestione di coppie nome/valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="6f732-121">Viene descritto come gestire le informazioni dell'applicazione che è preferibile mantenere come coppie nome/valore, ad esempio informazioni di configurazione o impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="6f732-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="6f732-122">Procedura: modificare il Namespace per un intero albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="6f732-123">Viene illustrato come spostare un albero XML da uno spazio dei nomi a un altro.</span><span class="sxs-lookup"><span data-stu-id="6f732-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f732-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f732-124">See Also</span></span>  
 [<span data-ttu-id="6f732-125">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f732-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
