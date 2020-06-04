---
title: Esecuzione di query su strutture ad albero XML
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 22e3dd873e2be8381f3d8da8f7c4284d09e45543
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411870"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="e7ce7-102">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="e7ce7-103">Contenuto della sezione vengono forniti esempi di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7ce7-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="e7ce7-104">Per ulteriori informazioni sulla scrittura di query LINQ, vedere [Introduzione con LINQ in Visual Basic](getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="e7ce7-104">For more information about writing LINQ queries, see [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="e7ce7-105">Dopo aver creato un'istanza di un albero XML, la scrittura di query è il modo più efficace per estrarre dati dall'albero.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="e7ce7-106">Inoltre, le query combinate con la costruzione funzionale consentono di generare un nuovo documento XML con una forma diversa rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7ce7-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e7ce7-107">In This Section</span></span>  
  
|<span data-ttu-id="e7ce7-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="e7ce7-108">Topic</span></span>|<span data-ttu-id="e7ce7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7ce7-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e7ce7-110">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)|<span data-ttu-id="e7ce7-111">Vengono forniti esempi comuni relativi all'esecuzione di query su alberi XML.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="e7ce7-112">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="e7ce7-113">Vengono forniti esempi comuni di proiezione e trasformazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="e7ce7-114">Tecniche di query avanzate (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="e7ce7-115">Vengono fornite tecniche di query che risultano utili negli scenari più avanzati.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="e7ce7-116">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)|<span data-ttu-id="e7ce7-117">Vengono presentate diverse espressioni XPath e gli equivalenti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7ce7-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="e7ce7-118">Trasformazioni funzionali pure di XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](pure-functional-transformations-of-xml.md)|<span data-ttu-id="e7ce7-119">Viene presentata una breve esercitazione sulla scrittura di query nello stile della programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="e7ce7-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7ce7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7ce7-120">See also</span></span>

- [<span data-ttu-id="e7ce7-121">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7ce7-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](programming-guide-linq-to-xml.md)
- [<span data-ttu-id="e7ce7-122">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7ce7-122">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
