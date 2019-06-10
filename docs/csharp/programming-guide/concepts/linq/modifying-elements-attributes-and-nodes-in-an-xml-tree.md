---
title: Modifica di elementi, attributi e nodi in un albero XML
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 93a4d67129e22d0bbeef464c1d4d8758439edb7b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484227"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="2400b-102">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="2400b-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="2400b-103">Nella tabella seguente sono riepilogati i metodi e le proprietà che è possibile usare per modificare un elemento, i relativi elementi figlio o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="2400b-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="2400b-104">I metodi seguenti modificano <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2400b-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="2400b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2400b-105">Method</span></span>|<span data-ttu-id="2400b-106">Description</span><span class="sxs-lookup"><span data-stu-id="2400b-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-107">Sostituisce un elemento con XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="2400b-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-108">Rimuove tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="2400b-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-109">Rimuove gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2400b-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-110">Sostituisce tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="2400b-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-111">Sostituisce gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2400b-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-112">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="2400b-112">Sets the value of an attribute.</span></span> <span data-ttu-id="2400b-113">Crea l'attributo se non esiste.</span><span class="sxs-lookup"><span data-stu-id="2400b-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="2400b-114">Se il valore è impostato su `null`, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="2400b-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-115">Imposta il valore di un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="2400b-115">Sets the value of a child element.</span></span> <span data-ttu-id="2400b-116">Crea l'elemento se non esiste.</span><span class="sxs-lookup"><span data-stu-id="2400b-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="2400b-117">Se il valore è impostato su `null`, rimuove l'elemento.</span><span class="sxs-lookup"><span data-stu-id="2400b-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-118">Sostituisce il contenuto (nodi figlio) di un elemento con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="2400b-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-119">Imposta il valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2400b-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="2400b-120">I metodi seguenti modificano <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2400b-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="2400b-121">Metodo</span><span class="sxs-lookup"><span data-stu-id="2400b-121">Method</span></span>|<span data-ttu-id="2400b-122">Description</span><span class="sxs-lookup"><span data-stu-id="2400b-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-123">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="2400b-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-124">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="2400b-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="2400b-125">I metodi seguenti modificano <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="2400b-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="2400b-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="2400b-126">Method</span></span>|<span data-ttu-id="2400b-127">Description</span><span class="sxs-lookup"><span data-stu-id="2400b-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-128">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="2400b-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="2400b-129">I metodi seguenti modificano <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="2400b-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="2400b-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="2400b-130">Method</span></span>|<span data-ttu-id="2400b-131">Description</span><span class="sxs-lookup"><span data-stu-id="2400b-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="2400b-132">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="2400b-132">Replaces the children nodes with new content.</span></span>|  
