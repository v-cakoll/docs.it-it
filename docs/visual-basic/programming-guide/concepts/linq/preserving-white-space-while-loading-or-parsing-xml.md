---
title: Conservando lo spazio vuoto durante il caricamento o l&quot;analisi XML2 | Documenti di Microsoft
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2872c1e2354c0a0bd106f7fb945542ce37e7774
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="75d68-102">Conservazione di spazi vuoti durante il caricamento o l'analisi di dati XML</span><span class="sxs-lookup"><span data-stu-id="75d68-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="75d68-103">In questo argomento viene descritto come controllare il comportamento dello spazio vuoto di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75d68-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="75d68-104">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni su XML e quindi l'XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="75d68-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="75d68-105">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="75d68-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="75d68-106">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="75d68-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="75d68-107">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="75d68-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="75d68-108">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="75d68-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="75d68-109">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="75d68-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="75d68-110">In questo argomento viene descritto il comportamento dello spazio vuoto dei metodi che popolano l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="75d68-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="75d68-111">Per informazioni su come controllare gli spazi vuoti durante la serializzazione di strutture ad albero XML, vedere [conservare gli spazi vuoti durante la serializzazione](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="75d68-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="75d68-112">Comportamento dei metodi che popolano gli alberi XML</span><span class="sxs-lookup"><span data-stu-id="75d68-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="75d68-113">I metodi seguenti di <xref:System.Xml.Linq.XElement>e <xref:System.Xml.Linq.XDocument>classi popolano un albero XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="75d68-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="75d68-114">È possibile popolare un albero XML da un file, un <xref:System.IO.TextReader>, un <xref:System.Xml.XmlReader>, o una stringa:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="75d68-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <span data-ttu-id="75d68-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="75d68-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="75d68-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="75d68-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="75d68-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="75d68-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="75d68-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="75d68-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="75d68-119">Se il metodo non accetta <xref:System.Xml.Linq.LoadOptions>come argomento, il metodo non mantiene gli spazi vuoti non significativi.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="75d68-119">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="75d68-120">Nella maggior parte dei casi, se il metodo accetta <xref:System.Xml.Linq.LoadOptions>come argomento, facoltativamente è possibile conservare spazio vuoto non significativo come nodi di testo nell'albero XML.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="75d68-120">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="75d68-121">Tuttavia, se il metodo carica il XML da un <xref:System.Xml.XmlReader>, il <xref:System.Xml.XmlReader>determina se lo spazio vuoto verrà conservato o meno.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="75d68-121">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="75d68-122">L'impostazione <xref:System.Xml.Linq.LoadOptions>avrà alcun effetto.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="75d68-122">Setting <xref:System.Xml.Linq.LoadOptions> will have no effect.</span></span>  
  
 <span data-ttu-id="75d68-123">Con questi metodi, se lo spazio vuoto viene conservato, spazio vuoto non significativo viene inserito nell'albero XML come <xref:System.Xml.Linq.XText>nodi.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="75d68-123">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="75d68-124">Se non viene conservato, i nodi di testo non vengono inseriti.</span><span class="sxs-lookup"><span data-stu-id="75d68-124">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="75d68-125">È possibile creare una struttura ad albero XML utilizzando un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="75d68-125">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="75d68-126">I nodi che vengono scritti i <xref:System.Xml.XmlWriter>vengono popolati nell'albero.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="75d68-126">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="75d68-127">Tuttavia, quando si compila un albero XML usando questo metodo, vengono conservati tutti i nodi, a prescindere che corrispondano o meno a spazio vuoto e indipendentemente dal fatto che lo spazio vuoto sia o meno significativo.</span><span class="sxs-lookup"><span data-stu-id="75d68-127">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d68-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d68-128">See Also</span></span>  
 [<span data-ttu-id="75d68-129">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75d68-129">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
