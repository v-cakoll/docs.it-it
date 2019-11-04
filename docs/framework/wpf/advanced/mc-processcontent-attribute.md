---
title: Attributo mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: dde304cc2b9db9cb01f9264ca1359b8979512cfa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458789"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="7610f-102">Attributo mc:ProcessContent</span><span class="sxs-lookup"><span data-stu-id="7610f-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="7610f-103">Specifica quali elementi di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] devono ancora avere contenuto elaborato da elementi padre pertinenti, anche se l'elemento padre diretto può essere ignorato da un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a causa della specifica dell' [attributo MC: Ignorable](mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="7610f-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="7610f-104">L'attributo `mc:ProcessContent` supporta la compatibilità del markup sia per il mapping dello spazio dei nomi personalizzato che per il controllo delle versioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7610f-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7610f-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="7610f-105">XAML Attribute Usage</span></span>  
  
```xaml  
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
  
## <a name="xaml-values"></a><span data-ttu-id="7610f-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="7610f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7610f-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="7610f-107">*ignorablePrefix*</span></span>|<span data-ttu-id="7610f-108">Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="7610f-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="7610f-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="7610f-109">*ignorableUri*</span></span>|<span data-ttu-id="7610f-110">Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="7610f-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="7610f-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="7610f-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="7610f-112">Elemento che può essere ignorato dalle implementazioni del processore [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se non è possibile risolvere il tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="7610f-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="7610f-113">*contenuto*</span><span class="sxs-lookup"><span data-stu-id="7610f-113">*[content]*</span></span>|<span data-ttu-id="7610f-114">*ThisElementCanBeIgnored* è contrassegnato come ignorable.</span><span class="sxs-lookup"><span data-stu-id="7610f-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="7610f-115">Se il processore ignora tale elemento, *[content]* viene elaborato dall' *oggetto*.</span><span class="sxs-lookup"><span data-stu-id="7610f-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7610f-116">Note</span><span class="sxs-lookup"><span data-stu-id="7610f-116">Remarks</span></span>  
 <span data-ttu-id="7610f-117">Per impostazione predefinita, un processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ignorerà il contenuto all'interno di un elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="7610f-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="7610f-118">È possibile specificare un elemento specifico per `mc:ProcessContent`e un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] continuerà a elaborare il contenuto all'interno dell'elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="7610f-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="7610f-119">Questa operazione viene in genere usata se il contenuto è annidato all'interno di diversi tag, almeno uno dei quali è ignorabile e almeno uno di questi non è ignorabile.</span><span class="sxs-lookup"><span data-stu-id="7610f-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="7610f-120">È possibile specificare più prefissi nell'attributo, usando un separatore di spazio, ad esempio: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="7610f-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="7610f-121">Lo spazio dei nomi `http://schemas.openxmlformats.org/markup-compatibility/2006` definisce altri elementi e attributi non documentati in questa area dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="7610f-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="7610f-122">Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="7610f-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7610f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7610f-123">See also</span></span>

- [<span data-ttu-id="7610f-124">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="7610f-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="7610f-125">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7610f-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
