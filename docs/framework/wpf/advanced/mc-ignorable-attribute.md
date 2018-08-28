---
title: Attributo mc:Ignorable
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 45b9ee94b35f368a9d0c96381083aa58c9a23f77
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998411"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="c50ef-102">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="c50ef-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="c50ef-103">Specifica quale [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefissi dello spazio dei nomi rilevati in un file di markup possono essere ignorati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore.</span><span class="sxs-lookup"><span data-stu-id="c50ef-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="c50ef-104">Il `mc:Ignorable` attributo supporta la compatibilità dei markup per il mapping dello spazio dei nomi personalizzati sia per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="c50ef-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="c50ef-105">Utilizzo degli attributi XAML (singolo prefisso)</span><span class="sxs-lookup"><span data-stu-id="c50ef-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="c50ef-106">Utilizzo degli attributi XAML (due prefissi)</span><span class="sxs-lookup"><span data-stu-id="c50ef-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c50ef-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="c50ef-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c50ef-108">*ignorablePrefix ignorablePrefix1, e così via.*</span><span class="sxs-lookup"><span data-stu-id="c50ef-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="c50ef-109">Qualsiasi stringa di prefisso valida, secondo la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="c50ef-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="c50ef-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="c50ef-110">*ignorableUri*</span></span>|<span data-ttu-id="c50ef-111">Qualsiasi URI valido per la designazione di uno spazio dei nomi, secondo la specifica XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="c50ef-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="c50ef-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="c50ef-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="c50ef-113">Un elemento che può essere ignorato dagli [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] le implementazioni del processore, se il tipo sottostante non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="c50ef-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c50ef-114">Note</span><span class="sxs-lookup"><span data-stu-id="c50ef-114">Remarks</span></span>  
 <span data-ttu-id="c50ef-115">Il `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefisso dello spazio dei nomi è la convenzione di prefisso consigliato da usare durante il mapping di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello spazio dei nomi di compatibilità [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c50ef-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="c50ef-116">Gli elementi o attributi in cui la parte del prefisso del nome dell'elemento sono identificati come `mc:Ignorable` non genera errori durante l'elaborazione da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore.</span><span class="sxs-lookup"><span data-stu-id="c50ef-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="c50ef-117">Se tale attributo non può essere risolta in un tipo sottostante o il costrutto di programmazione, tale elemento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c50ef-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="c50ef-118">Si noti tuttavia che gli elementi ignorati comunque potrebbero generare ulteriori errori di analisi per i requisiti di elemento aggiuntivo che può avere effetti collaterali di tale elemento non vengono elaborate.</span><span class="sxs-lookup"><span data-stu-id="c50ef-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="c50ef-119">Ad esempio, un modello di contenuto di un elemento specifico potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato è stato un `mc:Ignorable` prefisso e l'elemento figlio specificato non può essere risolto in un tipo, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] potrebbe processore Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="c50ef-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="c50ef-120">`mc:Ignorable` si applica solo ai mapping dello spazio dei nomi alle stringhe dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="c50ef-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="c50ef-121">`mc:Ignorable` non si applica a mapping dello spazio dei nomi negli assembly, specificare un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] dello spazio dei nomi e un assembly (o predefinito per l'eseguibile dell'assembly corrente).</span><span class="sxs-lookup"><span data-stu-id="c50ef-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="c50ef-122">Se si implementa una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, il processore non deve generare l'analisi o la risoluzione del tipo per qualsiasi elemento o attributo che è qualificato da un prefisso che viene identificato come errori di elaborazione `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="c50ef-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="c50ef-123">Ma l'implementazione del processore può comunque generare eccezioni che sono il risultato secondario di un elemento riesce a caricare o essere elaborato, come illustrato nell'esempio solo elemento figlio riportato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c50ef-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="c50ef-124">Per impostazione predefinita, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore ignorerà il contenuto di un elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="c50ef-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="c50ef-125">Tuttavia, è possibile specificare un attributo aggiuntivo, [attributo mc: ProcessContent](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), richiede l'elaborazione di continuo del contenuto all'interno di un elemento ignorato dall'elemento padre disponibile successivo.</span><span class="sxs-lookup"><span data-stu-id="c50ef-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="c50ef-126">Più prefissi possono essere specificati nell'attributo, usando uno o più caratteri spazio come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="c50ef-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  
  
 <span data-ttu-id="c50ef-127">Il [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa area del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c50ef-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="c50ef-128">Per altre informazioni, vedere [specifica la compatibilità del Markup XML](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="c50ef-128">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50ef-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c50ef-129">See Also</span></span>  
 <xref:System.Windows.Markup.XamlReader>  
 [<span data-ttu-id="c50ef-130">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="c50ef-130">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [<span data-ttu-id="c50ef-131">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c50ef-131">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="c50ef-132">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="c50ef-132">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
