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
ms.openlocfilehash: 40c1a8513608728a84b6b605f9ad18603123ea2e
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401538"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="228dc-102">Attributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="228dc-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="228dc-103">Specifica quali [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefissi di spazio dei nomi rilevati in un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup possono essere ignorati da un processore.</span><span class="sxs-lookup"><span data-stu-id="228dc-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="228dc-104">L' `mc:Ignorable` attributo supporta la compatibilità del markup sia per il mapping dello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] spazio dei nomi personalizzato che per il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="228dc-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="228dc-105">Utilizzo degli attributi XAML (prefisso singolo)</span><span class="sxs-lookup"><span data-stu-id="228dc-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="228dc-106">Utilizzo degli attributi XAML (due prefissi)</span><span class="sxs-lookup"><span data-stu-id="228dc-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="228dc-107">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="228dc-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="228dc-108">*ignorablePrefix, ignorablePrefix1, etc.*</span><span class="sxs-lookup"><span data-stu-id="228dc-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="228dc-109">Qualsiasi stringa di prefisso valida, in base alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="228dc-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="228dc-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="228dc-110">*ignorableUri*</span></span>|<span data-ttu-id="228dc-111">Qualsiasi URI valido per la designazione di uno spazio dei nomi, in base alla specifica XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="228dc-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="228dc-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="228dc-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="228dc-113">Elemento che può essere ignorato dalle [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementazioni del processore, se il tipo sottostante non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="228dc-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="228dc-114">Note</span><span class="sxs-lookup"><span data-stu-id="228dc-114">Remarks</span></span>  
 <span data-ttu-id="228dc-115">Il `mc` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]prefisso dello spazio dei nomi è la convenzione di prefisso consigliata da usare per il mapping dello spazio dei nomi Compatibility. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="228dc-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="228dc-116">Gli elementi o gli attributi in `mc:Ignorable` cui viene identificata la parte prefisso del nome dell'elemento non generano errori quando vengono elaborati da un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore.</span><span class="sxs-lookup"><span data-stu-id="228dc-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="228dc-117">Se tale attributo non può essere risolto in un tipo o un costrutto di programmazione sottostante, l'elemento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="228dc-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="228dc-118">Si noti tuttavia che gli elementi ignorati possono comunque generare errori di analisi aggiuntivi per ulteriori requisiti degli elementi che sono effetti collaterali dell'elemento non elaborato.</span><span class="sxs-lookup"><span data-stu-id="228dc-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="228dc-119">Ad esempio, un modello di contenuto dell'elemento specifico potrebbe richiedere esattamente un elemento figlio, ma se l'elemento figlio specificato si `mc:Ignorable` trovava in un prefisso e non è stato possibile risolvere l'elemento figlio specificato in un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tipo, il processore potrebbe genera un errore.</span><span class="sxs-lookup"><span data-stu-id="228dc-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="228dc-120">`mc:Ignorable`si applica solo ai mapping dello spazio dei nomi alle stringhe identificatore.</span><span class="sxs-lookup"><span data-stu-id="228dc-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="228dc-121">`mc:Ignorable`non si applica ai mapping dello spazio dei nomi negli assembly, che specificano uno spazio dei nomi CLR e un assembly (o l'eseguibile predefinito come assembly).</span><span class="sxs-lookup"><span data-stu-id="228dc-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="228dc-122">Se si implementa un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, l'implementazione del processore non deve generare errori di analisi o elaborazione sulla risoluzione del tipo per qualsiasi elemento o attributo qualificato da un prefisso identificato come. `mc:Ignorable`</span><span class="sxs-lookup"><span data-stu-id="228dc-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="228dc-123">Tuttavia, l'implementazione del processore può comunque generare eccezioni che sono un risultato secondario di un errore di caricamento o elaborazione di un elemento, ad esempio un elemento figlio di esempio specificato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="228dc-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="228dc-124">Per impostazione predefinita, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un processore ignorerà il contenuto all'interno di un elemento ignorato.</span><span class="sxs-lookup"><span data-stu-id="228dc-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="228dc-125">Tuttavia, è possibile specificare un attributo aggiuntivo, [MC: ProcessContent](mc-processcontent-attribute.md), per richiedere l'elaborazione continua del contenuto all'interno di un elemento ignorato dal successivo elemento padre disponibile.</span><span class="sxs-lookup"><span data-stu-id="228dc-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="228dc-126">È possibile specificare più prefissi nell'attributo, usando uno o più caratteri di spazio vuoto come separatore, ad esempio: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="228dc-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="228dc-127">Lo [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] spazio dei nomi definisce altri elementi e attributi che non sono documentati in questa [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]area di.</span><span class="sxs-lookup"><span data-stu-id="228dc-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="228dc-128">Per ulteriori informazioni, vedere [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="228dc-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228dc-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="228dc-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="228dc-130">Attributo PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="228dc-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="228dc-131">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="228dc-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="228dc-132">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="228dc-132">Documents in WPF</span></span>](documents-in-wpf.md)
