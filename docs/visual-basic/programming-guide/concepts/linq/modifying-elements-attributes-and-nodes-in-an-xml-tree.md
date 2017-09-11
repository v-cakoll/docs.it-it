---
title: Modifica elementi, attributi e nodi in un Tree1 XML | Documenti di Microsoft
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
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88531f2af88074f4406c4859354860829efda69f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="789b4-102">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="789b4-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="789b4-103">Nella tabella seguente sono riepilogati i metodi e le proprietà che è possibile usare per modificare un elemento, i relativi elementi figlio o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="789b4-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="789b4-104">I metodi seguenti modificano un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="789b4-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="789b4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="789b4-105">Method</span></span>|<span data-ttu-id="789b4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="789b4-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="789b4-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-108">Sostituisce un elemento con XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="789b4-108">Replaces an element with parsed XML.</span></span>|  
|<span data-ttu-id="789b4-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-110">Rimuove tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="789b4-110">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="789b4-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-112">Rimuove gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="789b4-112">Removes the attributes of an element.</span></span>|  
|<span data-ttu-id="789b4-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-114">Sostituisce tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="789b4-114">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="789b4-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-116">Sostituisce gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="789b4-116">Replaces the attributes of an element.</span></span>|  
|<span data-ttu-id="789b4-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-118">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="789b4-118">Sets the value of an attribute.</span></span> <span data-ttu-id="789b4-119">Crea l'attributo se non esiste.</span><span class="sxs-lookup"><span data-stu-id="789b4-119">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="789b4-120">Se il valore è impostato su `null`, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="789b4-120">If the value is set to `null`, removes the attribute.</span></span>|  
|<span data-ttu-id="789b4-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-122">Imposta il valore di un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="789b4-122">Sets the value of a child element.</span></span> <span data-ttu-id="789b4-123">Crea l'elemento se non esiste.</span><span class="sxs-lookup"><span data-stu-id="789b4-123">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="789b4-124">Se il valore è impostato su `null`, rimuove l'elemento.</span><span class="sxs-lookup"><span data-stu-id="789b4-124">If the value is set to `null`, removes the element.</span></span>|  
|<span data-ttu-id="789b4-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-126">Sostituisce il contenuto (nodi figlio) di un elemento con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="789b4-126">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<span data-ttu-id="789b4-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-128">Imposta il valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="789b4-128">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="789b4-129">I metodi seguenti modificano un <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="789b4-129">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="789b4-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="789b4-130">Method</span></span>|<span data-ttu-id="789b4-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="789b4-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="789b4-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-133">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="789b4-133">Sets the value of an attribute.</span></span>|  
|<span data-ttu-id="789b4-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-135">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="789b4-135">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="789b4-136">I metodi seguenti modificano un <xref:System.Xml.Linq.XNode>(incluso un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="789b4-136">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="789b4-137">Metodo</span><span class="sxs-lookup"><span data-stu-id="789b4-137">Method</span></span>|<span data-ttu-id="789b4-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="789b4-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="789b4-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-140">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="789b4-140">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="789b4-141">I metodi seguenti modificano un <xref:System.Xml.Linq.XContainer>(un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="789b4-141">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="789b4-142">Metodo</span><span class="sxs-lookup"><span data-stu-id="789b4-142">Method</span></span>|<span data-ttu-id="789b4-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="789b4-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="789b4-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="789b4-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="789b4-145">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="789b4-145">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="789b4-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="789b4-146">See Also</span></span>  
 [<span data-ttu-id="789b4-147">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="789b4-147">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
