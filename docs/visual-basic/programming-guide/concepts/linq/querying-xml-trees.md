---
title: Esecuzione di query su strutture ad albero XML
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: c8103820a231ba0fb5e8e7c15b7a2b9e7c996e65
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346572"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="9474e-102">Esecuzione di query su strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="9474e-103">Contenuto della sezione vengono forniti esempi di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9474e-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="9474e-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="9474e-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="9474e-105">Dopo aver creato un'istanza di un albero XML, la scrittura di query è il modo più efficace per estrarre dati dall'albero.</span><span class="sxs-lookup"><span data-stu-id="9474e-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="9474e-106">Inoltre, le query combinate con la costruzione funzionale consentono di generare un nuovo documento XML con una forma diversa rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="9474e-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9474e-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9474e-107">In This Section</span></span>  
  
|<span data-ttu-id="9474e-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="9474e-108">Topic</span></span>|<span data-ttu-id="9474e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9474e-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9474e-110">Basic Queries (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="9474e-111">Vengono forniti esempi comuni relativi all'esecuzione di query su alberi XML.</span><span class="sxs-lookup"><span data-stu-id="9474e-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="9474e-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="9474e-113">Vengono forniti esempi comuni di proiezione e trasformazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="9474e-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="9474e-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="9474e-115">Vengono fornite tecniche di query che risultano utili negli scenari più avanzati.</span><span class="sxs-lookup"><span data-stu-id="9474e-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="9474e-116">LINQ to XML for XPath Users (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="9474e-117">Vengono presentate diverse espressioni XPath e gli equivalenti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9474e-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="9474e-118">Pure Functional Transformations of XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="9474e-119">Viene presentata una breve esercitazione sulla scrittura di query nello stile della programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="9474e-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9474e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9474e-120">See also</span></span>

- [<span data-ttu-id="9474e-121">Programming Guide (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9474e-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
- [<span data-ttu-id="9474e-122">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9474e-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
