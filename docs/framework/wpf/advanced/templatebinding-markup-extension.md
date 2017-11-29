---
title: Estensione del markup TemplateBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ab8645de78a79f4bd47fa436699af002db99b9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="7441c-102">Estensione del markup TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="7441c-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="7441c-103">Collega il valore di una proprietà in un modello di controllo come valore di un'altra proprietà sul controllo basato su modelli.</span><span class="sxs-lookup"><span data-stu-id="7441c-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7441c-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="7441c-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="7441c-105">Utilizzo dell'attributo XAML (per proprietà Set in modelli o stili)</span><span class="sxs-lookup"><span data-stu-id="7441c-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7441c-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="7441c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="7441c-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> della proprietà impostata nella sintassi del setter.</span><span class="sxs-lookup"><span data-stu-id="7441c-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="7441c-108">Altra proprietà di dipendenza esistente nel tipo basato su modelli, specificata da <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7441c-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="7441c-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7441c-109">- or -</span></span><br /><br /> <span data-ttu-id="7441c-110">Nome della proprietà puntato definito da un tipo diverso rispetto al tipo di destinazione basato su modelli.</span><span class="sxs-lookup"><span data-stu-id="7441c-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="7441c-111">Si tratta in effetti di un oggetto <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="7441c-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="7441c-112">Vedere [sintassi di PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="7441c-112">See [PropertyPath XAML Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7441c-113">Note</span><span class="sxs-lookup"><span data-stu-id="7441c-113">Remarks</span></span>  
 <span data-ttu-id="7441c-114">Oggetto `TemplateBinding` è un formato ottimizzato di un [associazione](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) per gli scenari di modello, analogo a un `Binding` costruito con `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="7441c-114">A `TemplateBinding` is an optimized form of a [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="7441c-115">`TemplateBinding` è sempre un'associazione unidirezionale, anche se le proprietà implicano come impostazione predefinita l'associazione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7441c-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="7441c-116">Entrambe le proprietà in questione devono essere proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="7441c-116">Both properties involved must be dependency properties.</span></span>  
  
 <span data-ttu-id="7441c-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) è un'altra estensione di markup che a volte viene utilizzata in combinazione con o instead of `TemplateBinding` per eseguire l'associazione di proprietà all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="7441c-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="7441c-118">Che descrive i modelli di controllo come concetto non rientra in questo contesto. Per ulteriori informazioni, vedere [modelli e stili del controllo](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="7441c-118">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="7441c-119">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="7441c-119">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="7441c-120">Il token di stringa fornito dopo la stringa dell'identificatore `TemplateBinding` viene assegnato come valore <xref:System.Windows.TemplateBindingExtension.Property%2A> della classe dell'estensione <xref:System.Windows.TemplateBindingExtension> sottostante.</span><span class="sxs-lookup"><span data-stu-id="7441c-120">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="7441c-121">La sintassi di elementi oggetto è possibile, ma non viene mostrata poiché non ha applicazioni realistiche.</span><span class="sxs-lookup"><span data-stu-id="7441c-121">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="7441c-122">`TemplateBinding` viene utilizzato per inserire valori all'interno dei setter, tramite espressioni valutate e l'utilizzo della sintassi dell'elemento oggetto per `TemplateBinding` per riempire la sintassi dell'elemento di proprietà `<Setter.Property>` è inutilmente dettagliata.</span><span class="sxs-lookup"><span data-stu-id="7441c-122">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="7441c-123">L'oggetto `TemplateBinding` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.TemplateBindingExtension.Property%2A> come coppia proprietà=valore:</span><span class="sxs-lookup"><span data-stu-id="7441c-123">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="7441c-124">L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative.</span><span class="sxs-lookup"><span data-stu-id="7441c-124">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="7441c-125">Poiché `TemplateBinding` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.</span><span class="sxs-lookup"><span data-stu-id="7441c-125">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="7441c-126">Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'implementazione del processore XAML, la gestione di questa estensione di markup è definita per la <xref:System.Windows.TemplateBindingExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="7441c-126">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="7441c-127">`TemplateBinding` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="7441c-127">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="7441c-128">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="7441c-128">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="7441c-129">Tutte le estensioni di markup in XAML utilizzano il `{` e `}` caratteri nella relativa sintassi degli attributi, che corrisponde alla convenzione mediante il quale il processore XAML riconosce che l'attributo deve essere elaborato da un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="7441c-129">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="7441c-130">Per altre informazioni, vedere [Estensioni di markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7441c-130">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7441c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7441c-131">See Also</span></span>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="7441c-132">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="7441c-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7441c-133">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7441c-133">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="7441c-134">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="7441c-134">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="7441c-135">Estensione di markup RelativeSource</span><span class="sxs-lookup"><span data-stu-id="7441c-135">RelativeSource MarkupExtension</span></span>](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [<span data-ttu-id="7441c-136">Estensione di markup Binding</span><span class="sxs-lookup"><span data-stu-id="7441c-136">Binding Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
