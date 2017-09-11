---
title: 'Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (C#)'
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
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 293e8de848f83517211e3f3ed640102a2c534764
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a><span data-ttu-id="9ea89-102">Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-102">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>
<span data-ttu-id="9ea89-103">In questa esercitazione viene illustrato come applicare l'approccio delle trasformazioni funzionali e LINQ to XML per modificare documenti XML.</span><span class="sxs-lookup"><span data-stu-id="9ea89-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="9ea89-104">Negli esempio in C# vengono eseguite query e modificate le informazioni in documenti WordprocessingML di Office Open XML salvati tramite Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="9ea89-104">The C# examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="9ea89-105">Per altre informazioni, vedere il sito Web [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573).</span><span class="sxs-lookup"><span data-stu-id="9ea89-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ea89-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9ea89-106">In This Section</span></span>  
  
|<span data-ttu-id="9ea89-107">Argomento</span><span class="sxs-lookup"><span data-stu-id="9ea89-107">Topic</span></span>|<span data-ttu-id="9ea89-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ea89-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9ea89-109">Forma dei documenti WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-109">Shape of WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="9ea89-110">Viene fornita una rapida descrizione dei dettagli di un documento WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="9ea89-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="9ea89-111">Creazione del documento Office Open XML di origine (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-111">Creating the Source Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="9ea89-112">Vengono fornite istruzioni dettagliate per la creazione del documento di origine per le query riportate nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="9ea89-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="9ea89-113">Ricerca dello stile di paragrafo predefinito (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-113">Finding the Default Paragraph Style (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="9ea89-114">Viene illustrata una query eseguita per trovare il nome dello stile predefinito per un documento.</span><span class="sxs-lookup"><span data-stu-id="9ea89-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="9ea89-115">Recupero dei paragrafi e dei relativi stili (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-115">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="9ea89-116">Viene illustrata una query eseguita per recuperare una raccolta dei paragrafi di un documento.</span><span class="sxs-lookup"><span data-stu-id="9ea89-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="9ea89-117">Recupero del testo dei paragrafi (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-117">Retrieving the Text of the Paragraphs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="9ea89-118">Argomenti della query precedente per recuperare il testo di ogni paragrafo.</span><span class="sxs-lookup"><span data-stu-id="9ea89-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="9ea89-119">Refactoring usando un metodo di estensione (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-119">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="9ea89-120">Viene eseguito il refactoring tramite un metodo di estensione per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="9ea89-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="9ea89-121">Refactoring con una funzione pura (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-121">Refactoring Using a Pure Function (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="9ea89-122">Viene eseguito il refactoring con una funzione pura per semplificare ulteriormente il codice.</span><span class="sxs-lookup"><span data-stu-id="9ea89-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="9ea89-123">Proiezione di XML in una forma diversa (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-123">Projecting XML in a Different Shape (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="9ea89-124">Viene completata una trasformazione XML proiettando XML in una forma diversa rispetto al documento originale.</span><span class="sxs-lookup"><span data-stu-id="9ea89-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="9ea89-125">Ricerca di testo nei documenti di Word (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-125">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="9ea89-126">Viene usata la query precedente per trovare una stringa di testo specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="9ea89-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="9ea89-127">Dettagli di documenti WordprocessingML Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-127">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="9ea89-128">Vengono forniti dettagli sui documenti WordprocessingML di Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="9ea89-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ea89-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ea89-129">See Also</span></span>  
 <span data-ttu-id="9ea89-130">[Trasformazioni funzionali pure di XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9ea89-130">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
 [<span data-ttu-id="9ea89-131">Introduzione alle trasformazioni funzionali pure (C#)</span><span class="sxs-lookup"><span data-stu-id="9ea89-131">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)

