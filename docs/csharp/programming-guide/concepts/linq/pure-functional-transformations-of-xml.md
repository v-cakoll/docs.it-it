---
title: Trasformazioni funzionali pure di XML (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 97e8e582-eb3d-4756-bbfb-0899eb688ae4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32259e0b75d8c098663b589f33e2f36344fb15cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="pure-functional-transformations-of-xml-c"></a><span data-ttu-id="94016-102">Trasformazioni funzionali pure di XML (C#)</span><span class="sxs-lookup"><span data-stu-id="94016-102">Pure Functional Transformations of XML (C#)</span></span>
<span data-ttu-id="94016-103">Contenuto della sezione viene fornita un'esercitazione sulle trasformazioni funzionali per XML.</span><span class="sxs-lookup"><span data-stu-id="94016-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="94016-104">Vengono illustrati i principali concetti e costrutti di linguaggio che è necessario comprendere per usare le trasformazioni funzionali e vengono presentati alcuni esempi di utilizzo delle trasformazioni funzionali per la modifica di documenti XML.</span><span class="sxs-lookup"><span data-stu-id="94016-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="94016-105">Anche se nell'esercitazione sono riportati esempi di codice LINQ to XML, tutti i concetti sottostanti sono validi anche per altre tecnologie LINQ.</span><span class="sxs-lookup"><span data-stu-id="94016-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="94016-106">L'[esercitazione sulla modifica del contenuto in un documento WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) offre una serie di esempi, ognuno dei quali si basa su quello precedente.</span><span class="sxs-lookup"><span data-stu-id="94016-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="94016-107">In questi esempio è illustrato l'approccio delle trasformazioni funzionali pure per l'elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="94016-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="94016-108">Questa esercitazione presuppone una conoscenza di C# a livello professionale.</span><span class="sxs-lookup"><span data-stu-id="94016-108">This tutorial assumes a working knowledge of C#.</span></span> <span data-ttu-id="94016-109">La semantica dettagliata dei costrutti del linguaggio non viene fornita, ma sono resi disponibili dei collegamenti alla documentazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="94016-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="94016-110">È inoltre necessaria una conoscenza operativa dei concetti di base dell'informatica e degli ambienti XML, compresi gli spazi dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="94016-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94016-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="94016-111">In This Section</span></span>  
  
|<span data-ttu-id="94016-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="94016-112">Topic</span></span>|<span data-ttu-id="94016-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94016-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="94016-114">Introduzione alle trasformazioni funzionali pure (C#)</span><span class="sxs-lookup"><span data-stu-id="94016-114">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="94016-115">Vengono descritte le trasformazioni funzionali con una definizione della terminologia pertinente.</span><span class="sxs-lookup"><span data-stu-id="94016-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="94016-116">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="94016-116">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)|<span data-ttu-id="94016-117">Vengono descritte in dettaglio la valutazione lazy e l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="94016-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|<span data-ttu-id="94016-118">[Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) (Esercitazione sulla modifica del contenuto in un documento WordprocessingML (C#))</span><span class="sxs-lookup"><span data-stu-id="94016-118">[Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)</span></span>|<span data-ttu-id="94016-119">In questa esercitazione viene illustrata una trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="94016-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94016-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94016-120">See Also</span></span>  
 [<span data-ttu-id="94016-121">Esecuzione di query su strutture ad albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="94016-121">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
