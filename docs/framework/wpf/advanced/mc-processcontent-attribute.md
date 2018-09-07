---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 59097959ff4b3efaba4e4ee63d308eb21f91529d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070095"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="4867e-102">Attributo mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="4867e-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="4867e-103">Specifica quale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi ancora il contenuto sarà elaborato da elementi padre pertinente, anche se l'elemento padre immediato può essere ignorato da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore a causa di specificando [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="4867e-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="4867e-104">Il `mc:ProcessContent` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati sia per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="4867e-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="4867e-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="4867e-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="4867e-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="4867e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4867e-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="4867e-107">*ignorablePrefix*</span></span>|<span data-ttu-id="4867e-108">Qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="4867e-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4867e-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="4867e-109">*ignorableUri*</span></span>|<span data-ttu-id="4867e-110">Qualsiasi URI valido per la designazione di uno spazio dei nomi, secondo la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="4867e-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="4867e-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="4867e-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="4867e-112">Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="4867e-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="4867e-113">*[contenuto]*</span><span class="sxs-lookup"><span data-stu-id="4867e-113">*[content]*</span></span>|<span data-ttu-id="4867e-114">*ThisElementCanBeIgnored* è contrassegnato come può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="4867e-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="4867e-115">Se il processore ignora questo elemento, *[contenuto]* viene elaborato dal *oggetto*.</span><span class="sxs-lookup"><span data-stu-id="4867e-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4867e-116">Note</span><span class="sxs-lookup"><span data-stu-id="4867e-116">Remarks</span></span>  
 <span data-ttu-id="4867e-117">Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="4867e-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="4867e-118">È possibile specificare un elemento specifico dal `mc:ProcessContent`e un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore continuerà a elaborare il contenuto all'interno dell'elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="4867e-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="4867e-119">Ciò in genere vengono usato se il contenuto è annidato all'interno dei tag diversi, almeno uno dei quali è possibile ignorare e almeno uno dei quali non è possibile ignorare.</span><span class="sxs-lookup"><span data-stu-id="4867e-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="4867e-120">Più prefissi possono essere specificati nell'attributo, mediante uno spazio separatore, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="4867e-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="4867e-121">Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4867e-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="4867e-122">Per altre informazioni, vedere [specifica la compatibilità del Markup XML](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="4867e-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4867e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4867e-123">See Also</span></span>  
 [<span data-ttu-id="4867e-124">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="4867e-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="4867e-125">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="4867e-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
