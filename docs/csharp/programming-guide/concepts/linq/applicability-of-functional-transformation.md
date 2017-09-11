---
title: "Applicabilità della trasformazione funzionale (C#)"
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
ms.assetid: c78107bd-b006-4574-a3d4-bbf808388ff3
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b008bdef820b979e2aabd480e08a3bfa5ee5afa2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="applicability-of-functional-transformation-c"></a><span data-ttu-id="c90cb-102">Applicabilità della trasformazione funzionale (C#)</span><span class="sxs-lookup"><span data-stu-id="c90cb-102">Applicability of Functional Transformation (C#)</span></span>
<span data-ttu-id="c90cb-103">Le trasformazioni funzionali pure sono applicabili in un'ampia varietà di situazioni.</span><span class="sxs-lookup"><span data-stu-id="c90cb-103">Pure functional transformations are applicable in a wide variety of situations.</span></span>  
  
 <span data-ttu-id="c90cb-104">L'approccio della trasformazione funzionale è particolarmente indicato per l'esecuzione di query e modifiche di dati strutturati, pertanto si adatta perfettamente con le tecnologie LINQ.</span><span class="sxs-lookup"><span data-stu-id="c90cb-104">The functional transformation approach is ideally suited for querying and manipulating structured data; therefore it fits well with LINQ technologies.</span></span> <span data-ttu-id="c90cb-105">Tuttavia, la trasformazione funzionale presenta un'applicabilità molto più ampia rispetto all'utilizzo con LINQ.</span><span class="sxs-lookup"><span data-stu-id="c90cb-105">However, functional transformation has a much wider applicability than use with LINQ.</span></span> <span data-ttu-id="c90cb-106">Qualsiasi processo il cui obiettivo principale è trasformare dati da un formato a un altro può essere considerato un candidato valido per la trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c90cb-106">Any process where the main focus is on transforming data from one form to another should probably be considered as a candidate for functional transformation.</span></span>  
  
 <span data-ttu-id="c90cb-107">Questo approccio è applicabile a molti problemi che a prima vista potrebbero non apparire indicati.</span><span class="sxs-lookup"><span data-stu-id="c90cb-107">This approach is applicable to many problems that might not appear at first glance to be a candidate.</span></span> <span data-ttu-id="c90cb-108">Utilizzata insieme o separatamente rispetto a LINQ, la trasformazione funzionale deve essere considerata per le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="c90cb-108">Used in conjunction with or separately from LINQ, functional transformation should be considered for the following areas:</span></span>  
  
-   <span data-ttu-id="c90cb-109">Documenti basati su XML.</span><span class="sxs-lookup"><span data-stu-id="c90cb-109">XML-based documents.</span></span> <span data-ttu-id="c90cb-110">I dati ben formati di qualsiasi sottolinguaggio XML possono essere facilmente modificati tramite la trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c90cb-110">Well-formed data of any XML dialect can be easily manipulated through functional transformation.</span></span> <span data-ttu-id="c90cb-111">Per altre informazioni, vedere [Trasformazione funzionale di XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c90cb-111">For more information, see [Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).</span></span>  
  
-   <span data-ttu-id="c90cb-112">Altri formati di file strutturati.</span><span class="sxs-lookup"><span data-stu-id="c90cb-112">Other structured file formats.</span></span> <span data-ttu-id="c90cb-113">Dai file Windows.ini ai documenti di testo semplice, la maggior parte dei file presenta una struttura che si presta all'analisi e alla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="c90cb-113">From Windows.ini files to plain text documents, most files have some structure that lends itself to analysis and transformation.</span></span>  
  
-   <span data-ttu-id="c90cb-114">Protocolli di flusso dei dati.</span><span class="sxs-lookup"><span data-stu-id="c90cb-114">Data streaming protocols.</span></span> <span data-ttu-id="c90cb-115">La codifica e la decodifica di dati dai protocolli di comunicazione possono essere spesso rappresentate da una semplice trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c90cb-115">Encoding data into and decoding data from communication protocols can often be represented by a simple functional transform.</span></span>  
  
-   <span data-ttu-id="c90cb-116">Dati RDBMS e OODBMS.</span><span class="sxs-lookup"><span data-stu-id="c90cb-116">RDBMS and OODBMS data.</span></span> <span data-ttu-id="c90cb-117">I database relazionali e orientati a oggetti, quale XML, sono origini dati strutturate di largo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c90cb-117">Relational and object-oriented databases, just like XML, are widely-used structured data sources.</span></span>  
  
-   <span data-ttu-id="c90cb-118">Soluzioni matematiche, statistiche e scientifiche.</span><span class="sxs-lookup"><span data-stu-id="c90cb-118">Mathematic, statistic, and science solutions.</span></span> <span data-ttu-id="c90cb-119">In questi campi si tende a modificare grandi set di dati per assistere l'utente nella visualizzazione, nella stima o nella soluzione effettiva di problemi complessi.</span><span class="sxs-lookup"><span data-stu-id="c90cb-119">These fields tend to manipulate large data sets to assist the user in visualizing, estimating, or actually solving non-trivial problems.</span></span>  
  
 <span data-ttu-id="c90cb-120">Come descritto in [Refactoring in funzioni pure (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), l'uso di funzioni pure è un esempio di programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c90cb-120">As described in [Refactoring Into Pure Functions (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), using pure functions is an example of functional programming.</span></span> <span data-ttu-id="c90cb-121">Oltre a vantaggi immediati, l'uso di funzioni pure offre un'esperienza preziosa nel valutare i problemi da un punto di vista della trasformazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c90cb-121">In additional to their immediate benefits, using pure functions provides valuable experience in thinking about problems from a functional transformation perspective.</span></span> <span data-ttu-id="c90cb-122">Questo approccio può anche avere un impatto significativo sulla progettazione di programmi e classi.</span><span class="sxs-lookup"><span data-stu-id="c90cb-122">This approach can also have major impact on program and class design.</span></span> <span data-ttu-id="c90cb-123">Ciò vale soprattutto quando un problema si presta a una soluzione di trasformazione dei dati come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c90cb-123">This is especially true when a problem lends itself to a data transformation solution as described above.</span></span>  
  
 <span data-ttu-id="c90cb-124">Pur esulando dall'ambito di questa esercitazione, le progettazioni influenzate dal punto di vista della trasformazione funzionale tendono a essere centrate sui processi piuttosto che sugli oggetti come attori e la soluzione risultante tende a essere implementata come una serie di trasformazioni su vasta scala, anziché come singole modifiche allo stato degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c90cb-124">Although they are beyond the scope of this tutorial, designs that are influenced by the functional transformation perspective tend to center on processes more than on objects as actors, and the resulting solution tends to be implemented as series of large-scale transformations, rather than individual object state changes.</span></span>  
  
 <span data-ttu-id="c90cb-125">Ancora una volta, è opportuno tenere presente che C# supporta l'approccio imperativo e funzionale, quindi la progettazione ideale dell'applicazione potrebbe incorporare elementi di entrambi.</span><span class="sxs-lookup"><span data-stu-id="c90cb-125">Again, remember that C# supports both imperative and functional approaches, so the best design for your application might incorporate elements of both.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90cb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c90cb-126">See Also</span></span>  
 <span data-ttu-id="c90cb-127">[Introduzione alle trasformazioni funzionali pure (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="c90cb-127">[Introduction to Pure Functional Transformations (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
 <span data-ttu-id="c90cb-128">[Trasformazione funzionale di XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c90cb-128">[Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span></span>  
 [<span data-ttu-id="c90cb-129">Refactoring in funzioni pure (C#)</span><span class="sxs-lookup"><span data-stu-id="c90cb-129">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)

