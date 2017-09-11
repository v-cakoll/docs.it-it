---
title: La serializzazione di strutture ad albero XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
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
ms.openlocfilehash: a63e875b1c1391ec1bb2b0ae64be9f9cff28d87d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="9f438-102">La serializzazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f438-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="9f438-103">Per serializzazione di un albero XML si intende la generazione di codice XML dall'albero XML.</span><span class="sxs-lookup"><span data-stu-id="9f438-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="9f438-104">È possibile serializzare in un file, a un'implementazione concreta della <xref:System.IO.TextWriter>classe, o a un'implementazione concreta di un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="9f438-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="9f438-105">È possibile controllare vari aspetti della serializzazione,</span><span class="sxs-lookup"><span data-stu-id="9f438-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="9f438-106">ad esempio se impostare i rientri per il codice XML serializzato e se scrivere una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="9f438-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f438-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9f438-107">In This Section</span></span>  
  
|<span data-ttu-id="9f438-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="9f438-108">Topic</span></span>|<span data-ttu-id="9f438-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f438-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9f438-110">Conservazione di spazi vuoti durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="9f438-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="9f438-111">Viene descritto come controllare il comportamento dello spazio vuoto durante la serializzazione di strutture ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="9f438-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="9f438-112">Serializzazione con una dichiarazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f438-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="9f438-113">Viene descritto come serializzare una struttura ad albero XML che include una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="9f438-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="9f438-114">Serializzazione in base a File, TextWriter e XmlWriter</span><span class="sxs-lookup"><span data-stu-id="9f438-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="9f438-115">Viene descritto come serializzare un documento in un <xref:System.IO.File>, <xref:System.IO.TextWriter>, o un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="9f438-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="9f438-116">La serializzazione di un XmlReader (richiamo di XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f438-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="9f438-117">Viene descritto come creare un <xref:System.Xml.XmlReader>che consente a un altro modulo di leggere il contenuto di una struttura ad albero XML.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9f438-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f438-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f438-118">See Also</span></span>  
 [<span data-ttu-id="9f438-119">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f438-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
