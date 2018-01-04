---
title: Attributo mc:ProcessContent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="4eefa-102">Attributo mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="4eefa-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="4eefa-103">Specifica quale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi dovrebbero disporre ancora elaborato il contenuto da elementi padre rilevanti, anche se l'elemento padre immediato può essere ignorato da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore a causa dell'impostazione [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="4eefa-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="4eefa-104">Il `mc:ProcessContent` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati e per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="4eefa-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="4eefa-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="4eefa-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4eefa-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="4eefa-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4eefa-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="4eefa-107">*ignorablePrefix*</span></span>|<span data-ttu-id="4eefa-108">Qualsiasi stringa prefisso valido per la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="4eefa-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4eefa-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="4eefa-109">*ignorableUri*</span></span>|<span data-ttu-id="4eefa-110">Qualsiasi URI valido per la definizione di uno spazio dei nomi per la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="4eefa-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4eefa-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="4eefa-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="4eefa-112">Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="4eefa-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="4eefa-113">*[contenuto]*</span><span class="sxs-lookup"><span data-stu-id="4eefa-113">*[content]*</span></span>|<span data-ttu-id="4eefa-114">*ThisElementCanBeIgnored* è contrassegnato come ignorable.</span><span class="sxs-lookup"><span data-stu-id="4eefa-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="4eefa-115">Se il processore ignora tale elemento, *[contenuto]* viene elaborato da *oggetto*.</span><span class="sxs-lookup"><span data-stu-id="4eefa-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4eefa-116">Note</span><span class="sxs-lookup"><span data-stu-id="4eefa-116">Remarks</span></span>  
 <span data-ttu-id="4eefa-117">Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="4eefa-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="4eefa-118">È possibile specificare un elemento specifico da `mc:ProcessContent`e un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore continuerà a elaborare il contenuto all'interno dell'elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="4eefa-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="4eefa-119">Questo viene in genere utilizzato se il contenuto viene nidificato all'interno di altri tag, almeno uno dei quali è ignorable e almeno uno dei quali non lo sia.</span><span class="sxs-lookup"><span data-stu-id="4eefa-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="4eefa-120">Più prefissi possono essere specificati nell'attributo, utilizzando un separatore, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="4eefa-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="4eefa-121">Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eefa-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="4eefa-122">Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="4eefa-122">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eefa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eefa-123">See Also</span></span>  
 [<span data-ttu-id="4eefa-124">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="4eefa-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="4eefa-125">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="4eefa-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
