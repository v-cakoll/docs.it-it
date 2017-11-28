---
title: Modifica elementi, attributi e nodi in un Tree1 XML
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c769885d958abeaa92e19ef0b20d695fbcc4b96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="50052-102">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="50052-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="50052-103">Nella tabella seguente sono riepilogati i metodi e le proprietà che è possibile usare per modificare un elemento, i relativi elementi figlio o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="50052-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="50052-104">I metodi seguenti modificano <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="50052-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="50052-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="50052-105">Method</span></span>|<span data-ttu-id="50052-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50052-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-107">Sostituisce un elemento con XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="50052-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-108">Rimuove tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="50052-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-109">Rimuove gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="50052-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-110">Sostituisce tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="50052-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-111">Sostituisce gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="50052-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-112">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="50052-112">Sets the value of an attribute.</span></span> <span data-ttu-id="50052-113">Crea l'attributo se non esiste.</span><span class="sxs-lookup"><span data-stu-id="50052-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="50052-114">Se il valore è impostato su `null`, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="50052-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-115">Imposta il valore di un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="50052-115">Sets the value of a child element.</span></span> <span data-ttu-id="50052-116">Crea l'elemento se non esiste.</span><span class="sxs-lookup"><span data-stu-id="50052-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="50052-117">Se il valore è impostato su `null`, rimuove l'elemento.</span><span class="sxs-lookup"><span data-stu-id="50052-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-118">Sostituisce il contenuto (nodi figlio) di un elemento con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="50052-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-119">Imposta il valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="50052-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="50052-120">I metodi seguenti modificano <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="50052-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="50052-121">Metodo</span><span class="sxs-lookup"><span data-stu-id="50052-121">Method</span></span>|<span data-ttu-id="50052-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50052-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-123">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="50052-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-124">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="50052-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="50052-125">I metodi seguenti modificano <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="50052-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="50052-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="50052-126">Method</span></span>|<span data-ttu-id="50052-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50052-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-128">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="50052-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="50052-129">I metodi seguenti modificano <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="50052-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="50052-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="50052-130">Method</span></span>|<span data-ttu-id="50052-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50052-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="50052-132">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="50052-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50052-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50052-133">See Also</span></span>  
 [<span data-ttu-id="50052-134">Modifica degli alberi XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50052-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
