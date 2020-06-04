---
title: Serializzazione di strutture ad albero XML
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 640dc49134e869b60b4fa1fcd9a71fb1d61d39db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411818"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="68d43-102">Serializzazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d43-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="68d43-103">Per serializzazione di un albero XML si intende la generazione di codice XML dall'albero XML.</span><span class="sxs-lookup"><span data-stu-id="68d43-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="68d43-104">È possibile eseguire la serializzazione in un file, in un'implementazione concreta della classe <xref:System.IO.TextWriter> o in un'implementazione concreta di un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="68d43-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="68d43-105">È possibile controllare vari aspetti della serializzazione,</span><span class="sxs-lookup"><span data-stu-id="68d43-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="68d43-106">ad esempio se impostare i rientri per il codice XML serializzato e se scrivere una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="68d43-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68d43-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="68d43-107">In This Section</span></span>  
  
|<span data-ttu-id="68d43-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="68d43-108">Topic</span></span>|<span data-ttu-id="68d43-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68d43-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="68d43-110">Conservazione di spazi vuoti durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="68d43-110">Preserving White Space While Serializing</span></span>](preserving-white-space-while-serializing.md)|<span data-ttu-id="68d43-111">Viene descritto come controllare il comportamento dello spazio vuoto durante la serializzazione di strutture ad albero XML.</span><span class="sxs-lookup"><span data-stu-id="68d43-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="68d43-112">Serializzazione con una dichiarazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d43-112">Serializing with an XML Declaration (Visual Basic)</span></span>](serializing-with-an-xml-declaration.md)|<span data-ttu-id="68d43-113">Viene descritto come serializzare una struttura ad albero XML che include una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="68d43-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="68d43-114">Serializzazione in base a File, TextWriter e XmlWriter</span><span class="sxs-lookup"><span data-stu-id="68d43-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="68d43-115">Viene descritto come serializzare un documento in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="68d43-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="68d43-116">Serializzazione in un XmlReader (richiamo di XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d43-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="68d43-117">Viene descritto come creare un oggetto <xref:System.Xml.XmlReader> che consente a un altro modulo di leggere il contenuto di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="68d43-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68d43-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68d43-118">See also</span></span>

- [<span data-ttu-id="68d43-119">Guida per programmatori (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d43-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](programming-guide-linq-to-xml.md)
