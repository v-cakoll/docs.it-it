---
title: Trasformazioni funzionali pure di XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce372c12ec2359aa0f3f10e977241cb3d5a71ec8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="a552b-102">Trasformazioni funzionali pure di XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a552b-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="a552b-103">Contenuto della sezione viene fornita un'esercitazione sulle trasformazioni funzionali per XML.</span><span class="sxs-lookup"><span data-stu-id="a552b-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="a552b-104">Vengono illustrati i principali concetti e costrutti di linguaggio che è necessario comprendere per usare le trasformazioni funzionali e vengono presentati alcuni esempi di utilizzo delle trasformazioni funzionali per la modifica di documenti XML.</span><span class="sxs-lookup"><span data-stu-id="a552b-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="a552b-105">Anche se nell'esercitazione sono riportati esempi di codice LINQ to XML, tutti i concetti sottostanti sono validi anche per altre tecnologie LINQ.</span><span class="sxs-lookup"><span data-stu-id="a552b-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="a552b-106">Il [esercitazione: modifica di contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) esercitazione fornisce una serie di esempi, ognuno basato sul precedente.</span><span class="sxs-lookup"><span data-stu-id="a552b-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="a552b-107">In questi esempio è illustrato l'approccio delle trasformazioni funzionali pure per l'elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="a552b-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="a552b-108">In questa esercitazione si presuppone la conoscenza di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a552b-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="a552b-109">La semantica dettagliata dei costrutti del linguaggio non viene fornita, ma sono resi disponibili dei collegamenti alla documentazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="a552b-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="a552b-110">È inoltre necessaria una conoscenza operativa dei concetti di base dell'informatica e degli ambienti XML, compresi gli spazi dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="a552b-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a552b-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a552b-111">In This Section</span></span>  
  
|<span data-ttu-id="a552b-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="a552b-112">Topic</span></span>|<span data-ttu-id="a552b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a552b-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a552b-114">Introduzione alle trasformazioni funzionali Pure (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a552b-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="a552b-115">Vengono descritte le trasformazioni funzionali con una definizione della terminologia pertinente.</span><span class="sxs-lookup"><span data-stu-id="a552b-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="a552b-116">Esercitazione: Posticipata esecuzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a552b-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="a552b-117">Vengono descritte in dettaglio la valutazione lazy e l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="a552b-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="a552b-118">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a552b-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="a552b-119">In questa esercitazione viene illustrata una trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="a552b-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a552b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a552b-120">See Also</span></span>  
 [<span data-ttu-id="a552b-121">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a552b-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
