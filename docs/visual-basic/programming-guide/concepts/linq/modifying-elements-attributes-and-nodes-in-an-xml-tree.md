---
title: Modifica di elementi, attributi e nodi in un tree1 XML
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: 002e87d58ad1a3730889225bf4b3e50448431f2d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360930"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="9e308-102">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="9e308-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="9e308-103">Nella tabella seguente sono riepilogati i metodi e le proprietà che è possibile usare per modificare un elemento, i relativi elementi figlio o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="9e308-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="9e308-104">I metodi seguenti modificano <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9e308-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="9e308-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9e308-105">Method</span></span>|<span data-ttu-id="9e308-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e308-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-107">Sostituisce un elemento con XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="9e308-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-108">Rimuove tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="9e308-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-109">Rimuove gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="9e308-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-110">Sostituisce tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="9e308-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-111">Sostituisce gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="9e308-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-112">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="9e308-112">Sets the value of an attribute.</span></span> <span data-ttu-id="9e308-113">Crea l'attributo se non esiste.</span><span class="sxs-lookup"><span data-stu-id="9e308-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="9e308-114">Se il valore è impostato su `null`, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e308-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-115">Imposta il valore di un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="9e308-115">Sets the value of a child element.</span></span> <span data-ttu-id="9e308-116">Crea l'elemento se non esiste.</span><span class="sxs-lookup"><span data-stu-id="9e308-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="9e308-117">Se il valore è impostato su `null`, rimuove l'elemento.</span><span class="sxs-lookup"><span data-stu-id="9e308-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-118">Sostituisce il contenuto (nodi figlio) di un elemento con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="9e308-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-119">Imposta il valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="9e308-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="9e308-120">I metodi seguenti modificano <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9e308-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="9e308-121">Metodo</span><span class="sxs-lookup"><span data-stu-id="9e308-121">Method</span></span>|<span data-ttu-id="9e308-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e308-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-123">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="9e308-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-124">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="9e308-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="9e308-125">I metodi seguenti modificano <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="9e308-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="9e308-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="9e308-126">Method</span></span>|<span data-ttu-id="9e308-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e308-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-128">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="9e308-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="9e308-129">I metodi seguenti modificano <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="9e308-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="9e308-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="9e308-130">Method</span></span>|<span data-ttu-id="9e308-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e308-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="9e308-132">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="9e308-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e308-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e308-133">See also</span></span>

- [<span data-ttu-id="9e308-134">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e308-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
