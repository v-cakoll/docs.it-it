---
title: Esecuzione di query su strutture ad albero XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b2aa1e4852657590449be3e297302bf41ba3e5d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="c1256-102">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="c1256-103">Contenuto della sezione vengono forniti esempi di query [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1256-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
 <span data-ttu-id="c1256-104">Per ulteriori informazioni sulla scrittura [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="c1256-104">For more information about writing [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="c1256-105">Dopo aver creato un'istanza di un albero XML, la scrittura di query è il modo più efficace per estrarre dati dall'albero.</span><span class="sxs-lookup"><span data-stu-id="c1256-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="c1256-106">Inoltre, le query combinate con la costruzione funzionale consentono di generare un nuovo documento XML con una forma diversa rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="c1256-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1256-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c1256-107">In This Section</span></span>  
  
|<span data-ttu-id="c1256-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="c1256-108">Topic</span></span>|<span data-ttu-id="c1256-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1256-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c1256-110">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="c1256-111">Vengono forniti esempi comuni relativi all'esecuzione di query su alberi XML.</span><span class="sxs-lookup"><span data-stu-id="c1256-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="c1256-112">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="c1256-113">Vengono forniti esempi comuni di proiezione e trasformazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="c1256-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="c1256-114">Tecniche di Query (LINQ to XML) avanzate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="c1256-115">Vengono fornite tecniche di query che risultano utili negli scenari più avanzati.</span><span class="sxs-lookup"><span data-stu-id="c1256-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="c1256-116">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="c1256-117">Vengono presentate diverse espressioni XPath e il loro [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c1256-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="c1256-118">Trasformazioni funzionali pure di XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1256-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="c1256-119">Viene presentata una breve esercitazione sulla scrittura di query nello stile della programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="c1256-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1256-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1256-120">See Also</span></span>  
 <span data-ttu-id="c1256-121">[Guida per programmatori (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c1256-121">[Programming Guide (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
<span data-ttu-id="c1256-122"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="c1256-122"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span></span>
