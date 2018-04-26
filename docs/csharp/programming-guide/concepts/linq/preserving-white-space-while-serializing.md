---
title: Conservazione di spazi vuoti durante la serializzazione
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a73c4ec01c1a4d2cebe71ae1afdcce0466762c9c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="05b69-102">Conservazione di spazi vuoti durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="05b69-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="05b69-103">In questo argomento viene descritto come controllare lo spazio vuoto durante la serializzazione di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="05b69-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="05b69-104">In uno scenario comune viene letto il codice XML rientrato, viene creata una struttura ad albero XML in memoria senza nodi di testo di tipo spazio vuoto (ossia senza conservare lo spazio vuoto), vengono eseguite alcune operazioni sul codice XML e quindi il codice XML viene salvato senza rientro.</span><span class="sxs-lookup"><span data-stu-id="05b69-104">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="05b69-105">Quando si serializza l'XML con la formattazione, nell'albero XML viene conservato solo lo spazio vuoto significativo.</span><span class="sxs-lookup"><span data-stu-id="05b69-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="05b69-106">Questo è il comportamento predefinito per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05b69-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="05b69-107">In un altro scenario comune viene letto e modificato codice XML che è già stato intenzionalmente rientrato.</span><span class="sxs-lookup"><span data-stu-id="05b69-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="05b69-108">È possibile che si desideri non modificare questo rientro in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="05b69-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="05b69-109">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile ottenere questo risultato conservando lo spazio vuoto durante il caricamento o l'analisi XML e disabilitando la formattazione durante la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="05b69-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="05b69-110">Comportamento dello spazio vuoto di metodi che serializzano strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="05b69-110">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="05b69-111">I metodi seguenti delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XDocument> serializzano un albero XML.</span><span class="sxs-lookup"><span data-stu-id="05b69-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="05b69-112">È possibile serializzare un albero XML in un file, in un oggetto <xref:System.IO.TextReader> o in un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="05b69-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="05b69-113">Il metodo `ToString` consente di eseguire la serializzazione in una stringa.</span><span class="sxs-lookup"><span data-stu-id="05b69-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="05b69-114">Se il metodo non accetta <xref:System.Xml.Linq.SaveOptions> come argomento, formatterà il codice XML serializzato, ovvero ne imposterà il rientro.</span><span class="sxs-lookup"><span data-stu-id="05b69-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="05b69-115">In questo caso tutto lo spazio vuoto non significativo nella struttura ad albero XML verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="05b69-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="05b69-116">Se il metodo accetta <xref:System.Xml.Linq.SaveOptions> come argomento, è possibile specificare di non formattare il codice XML serializzato, ovvero il metodo non ne imposterà il rientro.</span><span class="sxs-lookup"><span data-stu-id="05b69-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="05b69-117">In questo caso tutto lo spazio vuoto nella struttura ad albero XML verrà mantenuto.</span><span class="sxs-lookup"><span data-stu-id="05b69-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b69-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05b69-118">See Also</span></span>  
 [<span data-ttu-id="05b69-119">Serializzazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="05b69-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
