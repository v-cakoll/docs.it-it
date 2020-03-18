---
title: Modifica di elementi, attributi e nodi in un albero XML
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 93a4d67129e22d0bbeef464c1d4d8758439edb7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "66484227"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="52c49-102">Modifica di elementi, attributi e nodi in un albero XML</span><span class="sxs-lookup"><span data-stu-id="52c49-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="52c49-103">Nella tabella seguente sono riepilogati i metodi e le proprietà che è possibile usare per modificare un elemento, i relativi elementi figlio o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="52c49-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="52c49-104">I metodi seguenti modificano <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="52c49-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="52c49-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="52c49-105">Method</span></span>|<span data-ttu-id="52c49-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c49-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-107">Sostituisce un elemento con XML analizzato.</span><span class="sxs-lookup"><span data-stu-id="52c49-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-108">Rimuove tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="52c49-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-109">Rimuove gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="52c49-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-110">Sostituisce tutto il contenuto di un elemento (nodi figlio e attributi).</span><span class="sxs-lookup"><span data-stu-id="52c49-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-111">Sostituisce gli attributi di un elemento.</span><span class="sxs-lookup"><span data-stu-id="52c49-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-112">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="52c49-112">Sets the value of an attribute.</span></span> <span data-ttu-id="52c49-113">Crea l'attributo se non esiste.</span><span class="sxs-lookup"><span data-stu-id="52c49-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="52c49-114">Se il valore è impostato su `null`, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="52c49-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-115">Imposta il valore di un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="52c49-115">Sets the value of a child element.</span></span> <span data-ttu-id="52c49-116">Crea l'elemento se non esiste.</span><span class="sxs-lookup"><span data-stu-id="52c49-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="52c49-117">Se il valore è impostato su `null`, rimuove l'elemento.</span><span class="sxs-lookup"><span data-stu-id="52c49-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-118">Sostituisce il contenuto (nodi figlio) di un elemento con il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="52c49-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-119">Imposta il valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="52c49-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="52c49-120">I metodi seguenti modificano <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52c49-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="52c49-121">Metodo</span><span class="sxs-lookup"><span data-stu-id="52c49-121">Method</span></span>|<span data-ttu-id="52c49-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c49-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-123">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="52c49-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-124">Imposta il valore di un attributo.</span><span class="sxs-lookup"><span data-stu-id="52c49-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="52c49-125">I metodi seguenti modificano <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="52c49-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="52c49-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="52c49-126">Method</span></span>|<span data-ttu-id="52c49-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c49-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-128">Sostituisce un nodo con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="52c49-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="52c49-129">I metodi seguenti modificano <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="52c49-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="52c49-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="52c49-130">Method</span></span>|<span data-ttu-id="52c49-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52c49-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="52c49-132">Sostituisce i nodi figlio con nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="52c49-132">Replaces the children nodes with new content.</span></span>|  
