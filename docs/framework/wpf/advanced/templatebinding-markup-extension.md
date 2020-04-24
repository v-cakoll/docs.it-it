---
title: Estensione del markup TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 8c631a5a78db90187f0375181d4d4d1832159b7d
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646176"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="8019e-102">Estensione del markup TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="8019e-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="8019e-103">Collega il valore di una proprietà in un modello di controllo come valore di un'altra proprietà sul controllo basato su modelli.</span><span class="sxs-lookup"><span data-stu-id="8019e-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="8019e-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="8019e-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="8019e-105">Utilizzo dell'attributo XAML (per proprietà Set in modelli o stili)</span><span class="sxs-lookup"><span data-stu-id="8019e-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="8019e-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="8019e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="8019e-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> della proprietà impostata nella sintassi del setter.</span><span class="sxs-lookup"><span data-stu-id="8019e-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="8019e-108">Altra proprietà di dipendenza esistente nel tipo basato su modelli, specificata da <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8019e-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="8019e-109">- oppure -</span><span class="sxs-lookup"><span data-stu-id="8019e-109">- or -</span></span><br /><br /> <span data-ttu-id="8019e-110">Nome della proprietà puntato definito da un tipo diverso rispetto al tipo di destinazione basato su modelli.</span><span class="sxs-lookup"><span data-stu-id="8019e-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="8019e-111">Si tratta in effetti di un oggetto <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="8019e-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="8019e-112">Vedere [Sintassi XAML PropertyPath](propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="8019e-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8019e-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8019e-113">Remarks</span></span>  
 <span data-ttu-id="8019e-114">A `TemplateBinding` è una forma ottimizzata di [un'associazione](binding-markup-extension.md) `Binding` per `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`gli scenari di modello, analoga a un oggetto costruito con .</span><span class="sxs-lookup"><span data-stu-id="8019e-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`.</span></span> <span data-ttu-id="8019e-115">`TemplateBinding` è sempre un'associazione unidirezionale, anche se le proprietà implicano come impostazione predefinita l'associazione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="8019e-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="8019e-116">Entrambe le proprietà in questione devono essere proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="8019e-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="8019e-117">Per ottenere l'associazione bidirezionale a un elemento padre `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`basato su modelli, utilizzare invece l'istruzione binding seguente.</span><span class="sxs-lookup"><span data-stu-id="8019e-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span>
  
 <span data-ttu-id="8019e-118">[RelativeSource](relativesource-markupextension.md) è un'altra estensione di markup che `TemplateBinding` viene talvolta utilizzata in combinazione con o anziché per eseguire l'associazione di proprietà relative all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="8019e-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="8019e-119">La descrizione dei modelli di controllo come concetto non è trattata in questo caso; Per ulteriori informazioni, consultate Stili e modelli di [controllo.](../controls/control-styles-and-templates.md)</span><span class="sxs-lookup"><span data-stu-id="8019e-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="8019e-120">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="8019e-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="8019e-121">Il token di stringa fornito dopo la stringa dell'identificatore `TemplateBinding` viene assegnato come valore <xref:System.Windows.TemplateBindingExtension.Property%2A> della classe dell'estensione <xref:System.Windows.TemplateBindingExtension> sottostante.</span><span class="sxs-lookup"><span data-stu-id="8019e-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="8019e-122">La sintassi di elementi oggetto è possibile, ma non viene mostrata poiché non ha applicazioni realistiche.</span><span class="sxs-lookup"><span data-stu-id="8019e-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="8019e-123">`TemplateBinding` viene utilizzato per inserire valori all'interno dei setter, tramite espressioni valutate e l'utilizzo della sintassi dell'elemento oggetto per `TemplateBinding` per riempire la sintassi dell'elemento di proprietà `<Setter.Property>` è inutilmente dettagliata.</span><span class="sxs-lookup"><span data-stu-id="8019e-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="8019e-124">L'oggetto `TemplateBinding` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.TemplateBindingExtension.Property%2A> come coppia proprietà=valore:</span><span class="sxs-lookup"><span data-stu-id="8019e-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="8019e-125">L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative.</span><span class="sxs-lookup"><span data-stu-id="8019e-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="8019e-126">Poiché `TemplateBinding` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.</span><span class="sxs-lookup"><span data-stu-id="8019e-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="8019e-127">Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processore XAML, la gestione <xref:System.Windows.TemplateBindingExtension> per questa estensione di markup è definita dalla classe .</span><span class="sxs-lookup"><span data-stu-id="8019e-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="8019e-128">`TemplateBinding` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="8019e-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="8019e-129">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="8019e-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="8019e-130">Tutte le estensioni `{` di `}` markup in XAML usano i caratteri e nella sintassi degli attributi, ovvero la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve elaborare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="8019e-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="8019e-131">Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="8019e-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8019e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8019e-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8019e-133">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8019e-133">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8019e-134">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8019e-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="8019e-135">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="8019e-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="8019e-136">Estensione del markup RelativeSource</span><span class="sxs-lookup"><span data-stu-id="8019e-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="8019e-137">Associazione dell'estensione di markup</span><span class="sxs-lookup"><span data-stu-id="8019e-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
