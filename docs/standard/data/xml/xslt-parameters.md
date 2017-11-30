---
title: Parametri XSLT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e66d98501bb0bd3a5d5cd5eacc0b09405c158522
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-parameters"></a><span data-ttu-id="90aad-102">Parametri XSLT</span><span class="sxs-lookup"><span data-stu-id="90aad-102">XSLT Parameters</span></span>
<span data-ttu-id="90aad-103">I parametri XSLT vengono aggiunti all'elenco <xref:System.Xml.Xsl.XsltArgumentList> mediante il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="90aad-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="90aad-104">Un nome qualificato e un URI dello spazio dei nomi sono associati all'oggetto parametro in quel momento.</span><span class="sxs-lookup"><span data-stu-id="90aad-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="90aad-105">Per usare un parametro XSLT</span><span class="sxs-lookup"><span data-stu-id="90aad-105">To use an XSLT parameter</span></span>  
  
1.  <span data-ttu-id="90aad-106">Creare un oggetto <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere il parametro usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="90aad-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2.  <span data-ttu-id="90aad-107">Richiamare il parametro dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="90aad-107">Call the parameter from the style sheet.</span></span>  
  
3.  <span data-ttu-id="90aad-108">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="90aad-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="90aad-109">Tipi di parametro</span><span class="sxs-lookup"><span data-stu-id="90aad-109">Parameter Types</span></span>  
 <span data-ttu-id="90aad-110">L'oggetto parametro dovrebbe corrispondere a un tipo W3C.</span><span class="sxs-lookup"><span data-stu-id="90aad-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="90aad-111">Nella tabella seguente sono illustrati i tipi W3C corrispondenti e le classi Microsoft .NET equivalenti (tipo) e viene indicato se il tipo W3C è un tipo XPath o XSLT.</span><span class="sxs-lookup"><span data-stu-id="90aad-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="90aad-112">Tipo W3C</span><span class="sxs-lookup"><span data-stu-id="90aad-112">W3C type</span></span>|<span data-ttu-id="90aad-113">Classe .NET equivalente (tipo)</span><span class="sxs-lookup"><span data-stu-id="90aad-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="90aad-114">Tipo XPath o XSLT</span><span class="sxs-lookup"><span data-stu-id="90aad-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="90aad-115">XPath</span><span class="sxs-lookup"><span data-stu-id="90aad-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="90aad-116">XPath</span><span class="sxs-lookup"><span data-stu-id="90aad-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="90aad-117">XPath</span><span class="sxs-lookup"><span data-stu-id="90aad-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="90aad-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="90aad-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="90aad-119">XPath</span><span class="sxs-lookup"><span data-stu-id="90aad-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="90aad-120">**XPathNavigator]**</span><span class="sxs-lookup"><span data-stu-id="90aad-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="90aad-121">XPath</span><span class="sxs-lookup"><span data-stu-id="90aad-121">XPath</span></span>|  
  
 <span data-ttu-id="90aad-122">*Questo è equivalente a un set di nodi che contiene un unico nodo.</span><span class="sxs-lookup"><span data-stu-id="90aad-122">*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="90aad-123">Se l'oggetto parametro non appartiene a una delle classi indicate sopra, viene convertito in base alle seguenti regole.</span><span class="sxs-lookup"><span data-stu-id="90aad-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="90aad-124">I tipi numerici CLR vengono convertiti nel tipo <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="90aad-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="90aad-125">Il tipo <xref:System.DateTime> viene convertito in <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="90aad-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="90aad-126">e i tipi <xref:System.Xml.XPath.IXPathNavigable> in <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="90aad-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="90aad-127">**XPathNavigator []** viene convertito in <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="90aad-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="90aad-128">Per tutti gli altri tipi verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="90aad-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90aad-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="90aad-129">Example</span></span>  
 <span data-ttu-id="90aad-130">Nell'esempio seguente il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> viene usato per creare un parametro per contenere una data di sconto calcolata.</span><span class="sxs-lookup"><span data-stu-id="90aad-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="90aad-131">La data di sconto è calcolata dopo 20 giorni dalla data dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="90aad-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="90aad-132">Input</span><span class="sxs-lookup"><span data-stu-id="90aad-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="90aad-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="90aad-133">order.xml</span></span>  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="90aad-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="90aad-134">discount.xsl</span></span>  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="90aad-135">Output</span><span class="sxs-lookup"><span data-stu-id="90aad-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90aad-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90aad-136">See Also</span></span>  
 [<span data-ttu-id="90aad-137">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="90aad-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
