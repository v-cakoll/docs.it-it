---
title: Estensione del markup RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 47117d684a981f31e22cf513fc78e1e2dda73f8a
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141259"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="9afdd-102">Estensione del markup RelativeSource</span><span class="sxs-lookup"><span data-stu-id="9afdd-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="9afdd-103">Specifica le proprietà di <xref:System.Windows.Data.RelativeSource> un'origine di associazione, da usare all'interno di un' [estensione di markup](binding-markup-extension.md)di associazione <xref:System.Windows.Data.Binding.RelativeSource%2A> o quando si <xref:System.Windows.Data.Binding> imposta la proprietà di un elemento definito in XAML.</span><span class="sxs-lookup"><span data-stu-id="9afdd-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="9afdd-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="9afdd-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="9afdd-105">Utilizzo della sintassi XAML per gli attributi (annidati nell'estensione Binding)</span><span class="sxs-lookup"><span data-stu-id="9afdd-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="9afdd-106">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="9afdd-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="9afdd-107">-oppure-</span><span class="sxs-lookup"><span data-stu-id="9afdd-107">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="9afdd-108">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="9afdd-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="9afdd-109">I tipi validi sono:</span><span class="sxs-lookup"><span data-stu-id="9afdd-109">One of the following:</span></span><br /><br /> <span data-ttu-id="9afdd-110">: Token `Self`di stringa. corrisponde a un <xref:System.Windows.Data.RelativeSource> oggetto creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.Self>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="9afdd-111">: Token `TemplatedParent`di stringa. corrisponde a un <xref:System.Windows.Data.RelativeSource> oggetto creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="9afdd-112">: Token `PreviousData`di stringa. corrisponde a un <xref:System.Windows.Data.RelativeSource> oggetto creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="9afdd-113">Per informazioni sulla `FindAncestor` modalità, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="9afdd-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="9afdd-114">Token stringa `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="9afdd-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="9afdd-115">L'utilizzo di questo token consente di accedere a una modalità in cui `RelativeSource` specifica un tipo predecessore e facoltativamente un livello predecessore.</span><span class="sxs-lookup"><span data-stu-id="9afdd-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="9afdd-116">Corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la proprietà <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="9afdd-117">Obbligatorio per la modalità `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="9afdd-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="9afdd-118">Nome di un tipo che riempie la proprietà <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="9afdd-119">Facoltativo per la modalità `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="9afdd-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="9afdd-120">Livello predecessore (valutato nella direzione padre dell'albero logico).</span><span class="sxs-lookup"><span data-stu-id="9afdd-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="9afdd-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9afdd-121">Remarks</span></span>

<span data-ttu-id="9afdd-122">`{RelativeSource TemplatedParent}`gli utilizzi di binding sono una tecnica essenziale che risolve un concetto più ampio della separazione tra l'interfaccia utente di un controllo e la logica di un controllo.</span><span class="sxs-lookup"><span data-stu-id="9afdd-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="9afdd-123">Ciò consente l'associazione dall'interno della definizione del modello al padre basato su modelli (istanza dell'oggetto in fase di esecuzione alla quale è applicato il modello).</span><span class="sxs-lookup"><span data-stu-id="9afdd-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="9afdd-124">Per questo caso, l' [estensione di markup TemplateBinding](templatebinding-markup-extension.md) è in realtà una sintassi abbreviata per la seguente `{Binding RelativeSource={RelativeSource TemplatedParent}}`espressione di associazione:.</span><span class="sxs-lookup"><span data-stu-id="9afdd-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="9afdd-125">`TemplateBinding`gli `{RelativeSource TemplatedParent}` utilizzi o sono entrambi rilevanti solo all'interno del codice XAML che definisce un modello.</span><span class="sxs-lookup"><span data-stu-id="9afdd-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="9afdd-126">Per ulteriori informazioni, vedere [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="9afdd-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="9afdd-127">`{RelativeSource FindAncestor}`viene usato principalmente nei modelli di controllo o nelle composizioni dell'interfaccia utente autonomia prevedibile, per i casi in cui un controllo deve essere sempre incluso in una struttura ad albero visuale di un determinato tipo di predecessore.</span><span class="sxs-lookup"><span data-stu-id="9afdd-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="9afdd-128">Ad esempio, gli elementi di un controllo di elementi potrebbero utilizzare `FindAncestor` per associarsi alle proprietà del relativo predecessore padre del controllo di elementi.</span><span class="sxs-lookup"><span data-stu-id="9afdd-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="9afdd-129">In alternativa, gli elementi che fanno parte della composizione del controllo in un modello possono utilizzare le associazioni `FindAncestor` agli elementi padre nella stessa struttura della composizione.</span><span class="sxs-lookup"><span data-stu-id="9afdd-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="9afdd-130">Nella sintassi dell'elemento oggetto per la modalità `FindAncestor` illustrata nelle sezioni sulla sintassi XAML, la sintassi del secondo elemento oggetto viene utilizzata specificamente per la modalità `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="9afdd-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="9afdd-131">La modalità `FindAncestor` richiede un valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="9afdd-132">È necessario impostare <xref:System.Windows.Data.RelativeSource.AncestorType%2A> come attributo utilizzando un riferimento all' [estensione di markup x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) al tipo di predecessore da cercare.</span><span class="sxs-lookup"><span data-stu-id="9afdd-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="9afdd-133">Il valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A> viene utilizzato quando la richiesta di associazione viene elaborata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9afdd-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="9afdd-134">Per la modalità `FindAncestor`, la proprietà facoltativa <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> consente di rendere meno ambigua la ricerca del predecessore laddove vi sono più predecessori di questo tipo nella struttura ad albero dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="9afdd-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="9afdd-135">Per ulteriori informazioni su come utilizzare la modalità `FindAncestor`, vedere <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="9afdd-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="9afdd-136">`{RelativeSource Self}`è utile per gli scenari in cui una proprietà di un'istanza deve dipendere dal valore di un'altra proprietà della stessa istanza e non esiste già una relazione di proprietà di dipendenza generale, ad esempio la coercizione, tra queste due proprietà.</span><span class="sxs-lookup"><span data-stu-id="9afdd-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="9afdd-137">Sebbene sia raro che esistano due proprietà su un oggetto in modo che i valori siano letteralmente identici (e siano tipizzati in modo identico), `Converter` è anche possibile applicare un parametro `{RelativeSource Self}`a un'associazione che dispone di e usare il convertitore per eseguire la conversione tra i tipi di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9afdd-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="9afdd-138">Un altro scenario `{RelativeSource Self}` per è come parte di <xref:System.Windows.MultiDataTrigger>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="9afdd-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="9afdd-139">Ad esempio, nel codice XAML seguente viene definito un elemento <xref:System.Windows.Shapes.Rectangle> in modo che, indipendentemente dal valore inserito per <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sia sempre un quadrato: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="9afdd-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="9afdd-140">`{RelativeSource PreviousData}`è utile nei modelli di dati oppure nei casi in cui le associazioni utilizzano una raccolta come origine dati.</span><span class="sxs-lookup"><span data-stu-id="9afdd-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="9afdd-141">È possibile utilizzare `{RelativeSource PreviousData}` per evidenziare le relazioni tra gli elementi di dati adiacenti nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9afdd-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="9afdd-142">Una tecnica correlata consiste nel porre un oggetto <xref:System.Windows.Data.MultiBinding> tra l'elemento corrente e quello precedente nell'origine dati e utilizzare un convertitore su quell'associazione per determinare la differenza tra i due elementi e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="9afdd-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="9afdd-143">Nell'esempio riportato di seguito, il primo <xref:System.Windows.Controls.TextBlock> in un modello di elementi visualizza il numero corrente.</span><span class="sxs-lookup"><span data-stu-id="9afdd-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="9afdd-144">Il secondo <xref:System.Windows.Controls.TextBlock> binding è un <xref:System.Windows.Data.MultiBinding> oggetto che ha nominalmente <xref:System.Windows.Data.Binding> due costituenti: il record corrente e un'associazione che utilizza intenzionalmente il record di dati precedente tramite `{RelativeSource PreviousData}`.</span><span class="sxs-lookup"><span data-stu-id="9afdd-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="9afdd-145">Quindi, un convertitore applicato a <xref:System.Windows.Data.MultiBinding> calcola la differenza e la restituisce all'associazione.</span><span class="sxs-lookup"><span data-stu-id="9afdd-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
</ListBox>
```

<span data-ttu-id="9afdd-146">La descrizione di data binding come concetto non è illustrata in questo articolo, vedere [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9afdd-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="9afdd-147">Nell'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del processore XAML, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.Data.RelativeSource> classe.</span><span class="sxs-lookup"><span data-stu-id="9afdd-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="9afdd-148">`RelativeSource` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="9afdd-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="9afdd-149">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="9afdd-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="9afdd-150">Tutte le estensioni di markup in XAML `{` usano `}` i caratteri e nella relativa sintassi di attributo, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve elaborare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9afdd-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="9afdd-151">Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="9afdd-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9afdd-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9afdd-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="9afdd-153">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="9afdd-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9afdd-154">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9afdd-154">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="9afdd-155">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="9afdd-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="9afdd-156">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="9afdd-156">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9afdd-157">Cenni preliminari sulle dichiarazioni di associazione</span><span class="sxs-lookup"><span data-stu-id="9afdd-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="9afdd-158">Estensione del markup x:Type</span><span class="sxs-lookup"><span data-stu-id="9afdd-158">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
