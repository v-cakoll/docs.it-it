---
title: Esecuzione di query su strutture ad albero XML (C#)
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
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4bad11434ed2610492854d5ec4a7a84bceb189f3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="6d5e0-102">Esecuzione di query su strutture ad albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="6d5e0-103">Contenuto della sezione vengono forniti esempi di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d5e0-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="6d5e0-104">Per altre informazioni sulla scrittura di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], vedere [Introduzione a LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="6d5e0-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="6d5e0-105">Dopo aver creato un'istanza di un albero XML, la scrittura di query è il modo più efficace per estrarre dati dall'albero.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="6d5e0-106">Inoltre, le query combinate con la costruzione funzionale consentono di generare un nuovo documento XML con una forma diversa rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d5e0-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6d5e0-107">In This Section</span></span>  
  
|<span data-ttu-id="6d5e0-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="6d5e0-108">Topic</span></span>|<span data-ttu-id="6d5e0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d5e0-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6d5e0-110">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) (Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-110">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span></span>|<span data-ttu-id="6d5e0-111">Vengono forniti esempi comuni relativi all'esecuzione di query su alberi XML.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-111">Provides common examples of querying XML trees.</span></span>|  
|<span data-ttu-id="6d5e0-112">[Projections and Transformations (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md) (Proiezioni e trasformazioni (LINQ to XML) in C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-112">[Projections and Transformations (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)</span></span>|<span data-ttu-id="6d5e0-113">Vengono forniti esempi comuni di proiezione e trasformazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|<span data-ttu-id="6d5e0-114">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md) (Tecniche di query avanzate (LINQ to XML) in C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-114">[Advanced Query Techniques (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)</span></span>|<span data-ttu-id="6d5e0-115">Vengono fornite tecniche di query che risultano utili negli scenari più avanzati.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="6d5e0-116">LINQ to XML per gli utenti di XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="6d5e0-117">Vengono presentate diverse espressioni XPath e gli equivalenti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d5e0-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="6d5e0-118">Trasformazioni funzionali pure di XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6d5e0-118">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="6d5e0-119">Viene presentata una breve esercitazione sulla scrittura di query nello stile della programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="6d5e0-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d5e0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d5e0-120">See Also</span></span>  
 <span data-ttu-id="6d5e0-121">[Guida per programmatori (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="6d5e0-121">[Programming Guide (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="6d5e0-122">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="6d5e0-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

