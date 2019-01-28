---
title: Conservazione di spazi vuoti durante la serializzazione
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 1b2a7f3ab2dcad200d6985e6b7bd91637d27dde8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741363"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="60862-102">Conservazione di spazi vuoti durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="60862-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="60862-103">In questo argomento viene descritto come controllare lo spazio vuoto durante la serializzazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="60862-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="60862-104">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni sul codice XML e quindi il codice XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="60862-104">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="60862-105">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="60862-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="60862-106">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60862-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="60862-107">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="60862-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="60862-108">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="60862-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="60862-109">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="60862-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="60862-110">Comportamento dello spazio vuoto di metodi che serializzano strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="60862-110">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="60862-111">I metodi seguenti delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> serializzano un albero XML.</span><span class="sxs-lookup"><span data-stu-id="60862-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="60862-112">È possibile serializzare un albero XML in un file, in un oggetto <xref:System.IO.TextReader> o in un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="60862-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="60862-113">Il metodo `ToString` consente di eseguire la serializzazione in una stringa.</span><span class="sxs-lookup"><span data-stu-id="60862-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="60862-114">Se il metodo non accetta <xref:System.Xml.Linq.SaveOptions> come argomento, formatterà il codice XML serializzato, ovvero ne imposterà il rientro.</span><span class="sxs-lookup"><span data-stu-id="60862-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="60862-115">In questo caso tutto lo spazio vuoto non significativo nella struttura ad albero XML verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="60862-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="60862-116">Se il metodo accetta <xref:System.Xml.Linq.SaveOptions> come argomento, è possibile specificare di non formattare il codice XML serializzato, ovvero il metodo non ne imposterà il rientro.</span><span class="sxs-lookup"><span data-stu-id="60862-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="60862-117">In questo caso tutto lo spazio vuoto nella struttura ad albero XML verrà mantenuto.</span><span class="sxs-lookup"><span data-stu-id="60862-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60862-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60862-118">See also</span></span>

- [<span data-ttu-id="60862-119">Serializzazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="60862-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
