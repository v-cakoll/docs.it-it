---
title: Estensione del markup x:Type
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4d645d5c953c0ff33435a5648024ace099455e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="5784f-102">Estensione del markup x:Type</span><span class="sxs-lookup"><span data-stu-id="5784f-102">x:Type Markup Extension</span></span>
<span data-ttu-id="5784f-103">CLR fornisce <xref:System.Type> oggetto che rappresenta il tipo sottostante per un tipo XAML specificato.</span><span class="sxs-lookup"><span data-stu-id="5784f-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5784f-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="5784f-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="5784f-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="5784f-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5784f-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="5784f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="5784f-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5784f-107">Optional.</span></span> <span data-ttu-id="5784f-108">Un prefisso che esegue il mapping di uno spazio dei nomi XAML non predefinito.</span><span class="sxs-lookup"><span data-stu-id="5784f-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="5784f-109">Specifica un prefisso è spesso non necessaria.</span><span class="sxs-lookup"><span data-stu-id="5784f-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="5784f-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="5784f-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="5784f-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5784f-111">Required.</span></span> <span data-ttu-id="5784f-112">Un nome di tipo risolvibile in nomi XAML predefinito corrente; o specificato mappati prefisso se `prefix` viene fornito.</span><span class="sxs-lookup"><span data-stu-id="5784f-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5784f-113">Note</span><span class="sxs-lookup"><span data-stu-id="5784f-113">Remarks</span></span>  
 <span data-ttu-id="5784f-114">Il `x:Type` estensione di markup è una funzione simile per la `typeof()` operatore in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] o `GetType` operatore in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5784f-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] or the `GetType` operator in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].</span></span>  
  
 <span data-ttu-id="5784f-115">Il `x:Type` estensione di markup fornisce un comportamento di conversione da stringa per le proprietà che accettano il tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="5784f-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="5784f-116">L'input è un tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="5784f-116">The input is a XAML type.</span></span> <span data-ttu-id="5784f-117">La relazione tra il tipo di sintassi XAML per gli input e output CLR <xref:System.Type> è che l'output <xref:System.Type> è il <xref:System.Xaml.XamlType.UnderlyingType%2A> dell'input <xref:System.Xaml.XamlType>, dopo avere cercato necessari <xref:System.Xaml.XamlType> basato sul contesto dello schema XAML e il <xref:System.Windows.Markup.IXamlTypeResolver>servizio fornisce il contesto.</span><span class="sxs-lookup"><span data-stu-id="5784f-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="5784f-118">Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.TypeExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="5784f-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="5784f-119">In implementazioni framework specifiche, alcune proprietà che accettano <xref:System.Type> come un valore può accettare direttamente il nome del tipo (il valore di stringa del tipo `Name`).</span><span class="sxs-lookup"><span data-stu-id="5784f-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="5784f-120">Tuttavia, l'implementazione di questo comportamento è uno scenario complesso.</span><span class="sxs-lookup"><span data-stu-id="5784f-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="5784f-121">Per esempi, vedere la sezione "Note sull'utilizzo di WPF" di seguito.</span><span class="sxs-lookup"><span data-stu-id="5784f-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="5784f-122">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="5784f-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="5784f-123">Il token di stringa fornito dopo la stringa dell'identificatore `x:Type` viene assegnato come valore <xref:System.Windows.Markup.TypeExtension.TypeName%2A> della classe dell'estensione <xref:System.Windows.Markup.TypeExtension> sottostante.</span><span class="sxs-lookup"><span data-stu-id="5784f-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="5784f-124">Nel contesto dello schema XAML predefinito per i servizi XAML di .NET Framework, che è basato su tipi CLR, il valore di questo attributo può essere il <xref:System.Reflection.MemberInfo.Name%2A> del tipo desiderato, o che contiene <xref:System.Reflection.MemberInfo.Name%2A> preceduto da un prefisso per uno spazio dei nomi XAML non predefinito. mapping.</span><span class="sxs-lookup"><span data-stu-id="5784f-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="5784f-125">Il `x:Type` estensione di markup può essere utilizzato nella sintassi dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="5784f-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="5784f-126">In questo caso, se si specifica il valore di <xref:System.Windows.Markup.TypeExtension.TypeName%2A> proprietà è necessaria per inizializzare correttamente l'estensione.</span><span class="sxs-lookup"><span data-stu-id="5784f-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="5784f-127">Il `x:Type` estensione di markup può essere utilizzato anche come attributo dettagliato; tuttavia questo utilizzo non è comune: `<``object``property``="{x:Type TypeName=``typeNameValue``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="5784f-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="5784f-128">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="5784f-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="5784f-129">Namespace XAML e Mapping dei tipi predefiniti</span><span class="sxs-lookup"><span data-stu-id="5784f-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="5784f-130">Spazio dei nomi XAML predefinito per la programmazione WPF contiene la maggior parte dei tipi di XAML, che è necessario per gli scenari tipici di XAML; Pertanto, è spesso possibile evitare i prefissi degli spazi quando si fa riferimento a valori di tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="5784f-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="5784f-131">Potrebbe essere necessario eseguire il mapping di un prefisso se si fa riferimento a un tipo da un assembly personalizzato o per i tipi presenti in un assembly WPF, ma sono compresi tra uno spazio dei nomi CLR che non è stato eseguito il mapping allo spazio dei nomi XAML predefinito.</span><span class="sxs-lookup"><span data-stu-id="5784f-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="5784f-132">Per ulteriori informazioni sui prefissi di spazi dei nomi XAML e spazi dei nomi CLR di mapping, vedere [spazi dei nomi XAML e Mapping Namespace per XAML WPF](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="5784f-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="5784f-133">Proprietà di tale supporto Typename come stringa di tipo</span><span class="sxs-lookup"><span data-stu-id="5784f-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="5784f-134">WPF supporta tecniche che consentono di specificare il valore di alcune proprietà del tipo <xref:System.Type> senza richiedere un `x:Type` utilizzo dell'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="5784f-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="5784f-135">In alternativa, è possibile specificare il valore sotto forma di stringa che corrisponde al nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="5784f-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="5784f-136">Esempi di questo approccio sono <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> e <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5784f-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5784f-137">Supporto per questo comportamento non viene fornito tramite le estensioni di markup o convertitori di tipi.</span><span class="sxs-lookup"><span data-stu-id="5784f-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="5784f-138">Al contrario, si tratta di un comportamento di rinvio implementato mediante <xref:System.Windows.FrameworkElementFactory>.</span><span class="sxs-lookup"><span data-stu-id="5784f-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="5784f-139">Silverlight supporta una convenzione simile.</span><span class="sxs-lookup"><span data-stu-id="5784f-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="5784f-140">In effetti, Silverlight attualmente non supporta `{x:Type}` nel supporto del linguaggio XAML e non accetta `{x:Type}` utilizzi di fuori di alcune condizioni che servono per supportare la migrazione di XAML di WPF e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="5784f-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="5784f-141">Pertanto, il comportamento di stringa come typename è incorporato in tutte le valutazioni delle proprietà native Silverlight in cui un <xref:System.Type> è il valore.</span><span class="sxs-lookup"><span data-stu-id="5784f-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="5784f-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="5784f-142">XAML 2009</span></span>  
 <span data-ttu-id="5784f-143">XAML 2009 fornisce supporto aggiuntivo per tipi generici e modifica il comportamento della funzionalità di `x:TypeArguments` e `x:Type` per fornire questo supporto.</span><span class="sxs-lookup"><span data-stu-id="5784f-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="5784f-144">`x:TypeArguments`e può essere l'elemento oggetto associato per un'istanza di oggetto generico su elementi diversi dalla radice.</span><span class="sxs-lookup"><span data-stu-id="5784f-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="5784f-145">Per ulteriori informazioni, vedere la sezione "XAML 2009" di [direttiva X:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span><span class="sxs-lookup"><span data-stu-id="5784f-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="5784f-146">XAML 2009 supporta una sintassi per specificare il vincolo del tipo generico nel markup.</span><span class="sxs-lookup"><span data-stu-id="5784f-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="5784f-147">Può essere utilizzato da `x:TypeArguments`, da `x:Type`, o dalle due funzionalità in combinazione.</span><span class="sxs-lookup"><span data-stu-id="5784f-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="5784f-148">Implementazione XAML di WPF durante l'elaborazione di XAML 2009 per il caricamento aggiunge anche questa funzionalità per il comportamento di conversione implicita del tipo per determinate proprietà del framework che utilizzano tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="5784f-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="5784f-149">In WPF, è possibile utilizzare le funzionalità di XAML 2009, ma solo per XAML separato (XAML non compilato dal markup).</span><span class="sxs-lookup"><span data-stu-id="5784f-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="5784f-150">Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="5784f-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5784f-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5784f-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="5784f-152">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="5784f-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="5784f-153">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="5784f-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="5784f-154">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="5784f-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
