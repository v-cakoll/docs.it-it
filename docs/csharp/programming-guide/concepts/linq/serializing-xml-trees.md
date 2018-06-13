---
title: Serializzazione di alberi XML (C#)
ms.date: 07/20/2015
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
ms.openlocfilehash: 8f372a05bd69b801085cba9d9a3b11ae01841a2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338351"
---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="158d5-102">Serializzazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="158d5-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="158d5-103">Per serializzazione di un albero XML si intende la generazione di codice XML dall'albero XML.</span><span class="sxs-lookup"><span data-stu-id="158d5-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="158d5-104">È possibile eseguire la serializzazione in un file, in un'implementazione concreta della classe <xref:System.IO.TextWriter> o in un'implementazione concreta di un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="158d5-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="158d5-105">È possibile controllare vari aspetti della serializzazione,</span><span class="sxs-lookup"><span data-stu-id="158d5-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="158d5-106">ad esempio se impostare i rientri per il codice XML serializzato e se scrivere una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="158d5-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="158d5-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="158d5-107">In This Section</span></span>  
  
|<span data-ttu-id="158d5-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="158d5-108">Topic</span></span>|<span data-ttu-id="158d5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="158d5-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="158d5-110">Conservazione di spazi vuoti durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="158d5-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="158d5-111">Viene descritto come controllare il comportamento dello spazio vuoto durante la serializzazione di strutture ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="158d5-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="158d5-112">Serializzazione con una dichiarazione XML (C#)</span><span class="sxs-lookup"><span data-stu-id="158d5-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="158d5-113">Viene descritto come serializzare una struttura ad albero XML che include una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="158d5-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="158d5-114">Serializzazione in base a File, TextWriter e XmlWriter</span><span class="sxs-lookup"><span data-stu-id="158d5-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="158d5-115">Viene descritto come serializzare un documento in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="158d5-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="158d5-116">Serializzazione in base a un XmlReader (richiamo di XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="158d5-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="158d5-117">Viene descritto come creare un oggetto <xref:System.Xml.XmlReader> che consente a un altro modulo di leggere il contenuto di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="158d5-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="158d5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="158d5-118">See Also</span></span>  
 [<span data-ttu-id="158d5-119">Guida per programmatori (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="158d5-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
