---
title: Creazione di strutture ad albero XML (C#)
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
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99b197b86096b803b9732ab2546b23ff59e3e2fe
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="20510-102">Creazione di strutture ad albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="20510-103">Una delle attività più comuni di XML è la creazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="20510-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="20510-104">In questa sezione vengono descritti diversi modi per crearle.</span><span class="sxs-lookup"><span data-stu-id="20510-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20510-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="20510-105">In This Section</span></span>  
  
|<span data-ttu-id="20510-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="20510-106">Topic</span></span>|<span data-ttu-id="20510-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20510-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="20510-108">Costruzione funzionale (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="20510-109">Viene fornita una panoramica sulla costruzione funzionale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20510-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="20510-110">La costruzione funzionale consente di creare tutta o parte della struttura ad albero XML in un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="20510-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="20510-111">In questo argomento viene inoltre illustrato come incorporare query durante la costruzione di una struttura ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="20510-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="20510-112">Creazione di alberi in C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="20510-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="20510-113">Viene illustrato come creare alberi in C#.</span><span class="sxs-lookup"><span data-stu-id="20510-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="20510-114">Clonazione e Aggiunta (C#) </span><span class="sxs-lookup"><span data-stu-id="20510-114">Cloning vs. Attaching (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="20510-115">Viene illustrata la differenza tra l'aggiunta di nodi da un albero XML esistente, in cui i nodi vengono prima clonati e poi aggiunti, e l'aggiunta di nodi senza elemento padre, in cui i nodi vengono semplicemente collegati.</span><span class="sxs-lookup"><span data-stu-id="20510-115">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="20510-116">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-116">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="20510-117">Viene illustrato come analizzare il codice XML da una vasta gamma di origini.</span><span class="sxs-lookup"><span data-stu-id="20510-117">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="20510-118"> rappresenta un livello superiore rispetto all'oggetto <xref:System.Xml.XmlReader>, che viene usato per analizzare il codice XML.</span><span class="sxs-lookup"><span data-stu-id="20510-118"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="20510-119">Procedura: Popolare una struttura ad albero XML con un XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-119">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="20510-120">Viene illustrato come popolare un albero XML usando un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="20510-120">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="20510-121">Procedura: Eseguire la convalida tramite XSD (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-121">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="20510-122">Viene illustrato come convalidare una struttura ad albero XML usando XSD.</span><span class="sxs-lookup"><span data-stu-id="20510-122">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="20510-123">Contenuto valido di oggetti XElement e XDocument</span><span class="sxs-lookup"><span data-stu-id="20510-123">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="20510-124">Vengono illustrati gli argomenti validi che è possibile passare ai costruttori e i metodi usati per aggiungere contenuto a elementi e documenti.</span><span class="sxs-lookup"><span data-stu-id="20510-124">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20510-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20510-125">See Also</span></span>  
 [<span data-ttu-id="20510-126">Guida per programmatori (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="20510-126">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

