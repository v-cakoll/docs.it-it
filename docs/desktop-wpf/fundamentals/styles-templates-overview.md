---
title: Stili e modelli
description: Informazioni sulle risorse XAML in Windows Presentation Foundation (WPF) per .NET Core.Learn about XAML resources in Windows Presentation Foundation (WPF) for .NET Core. Comprendere i tipi di risorse XAML correlati a stili e temi.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "82071885"
---
# <a name="styles-and-templates-in-wpf"></a>Stili e modelli in WPF

L'applicazione di stili e i modelli di Windows Presentation Foundation (WPF) si riferiscono a una suite di funzionalità che consentono a sviluppatori e progettisti di creare effetti visivamente accattivanti e un aspetto coerente per il prodotto. Quando si personalizza l'aspetto di un'app, si vuole un modello di stile e modelli forte che consenta la manutenzione e la condivisione dell'aspetto all'interno e tra le app. WPFWPF fornisce tale modello.

Un'altra funzionalità del modello di stile WPFWPF è la separazione tra presentazione e logica. Le finestre di progettazione possono lavorare sull'aspetto di un'app usando solo XAML nello stesso momento in cui gli sviluppatori lavorano sulla logica di programmazione usando C'è o Visual Basic.

Questa panoramica è incentrata sugli aspetti di applicazione di stili e modelli dell'app e non illustra alcun concetto di associazione dati. Per informazioni sul data binding, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).

È importante comprendere le risorse, che consentono di riutilizzare stili e modelli. Per altre informazioni sulle risorse, vedere [Risorse XAML](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Esempio

Il codice di esempio fornito in questa panoramica si basa su una semplice applicazione di [esplorazione](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) delle foto illustrata nella figura seguente.

![ListView con stile](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

Questo esempio usa stili e modelli per creare un'esperienza utente visivamente accattivante. L'esempio <xref:System.Windows.Controls.TextBlock> include due <xref:System.Windows.Controls.ListBox> elementi e un controllo associato a un elenco di immagini.

Per l'esempio completo, vedere [Introduzione a un esempio di applicazione di stili e di modelli](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Stili

È possibile considerare <xref:System.Windows.Style> un modo pratico per applicare un set di valori di proprietà a più elementi. È possibile utilizzare uno stile su <xref:System.Windows.FrameworkElement> qualsiasi <xref:System.Windows.FrameworkContentElement> elemento <xref:System.Windows.Window> che <xref:System.Windows.Controls.Button>deriva da o, ad esempio a o a .

Il modo più comune per dichiarare uno `Resources` stile è come risorsa nella sezione in un file XAML. Poiché gli stili sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. In parole povere, dove si dichiara uno stile influisce sul punto in cui lo stile può essere applicato. Ad esempio, se dichiari lo stile nell'elemento radice del file XAML di definizione dell'app, lo stile può essere usato in qualsiasi punto dell'app.

Ad esempio, il codice XAML seguente `TextBlock`dichiara due stili `TextBlock` per un oggetto , uno applicato automaticamente a tutti gli elementi e un altro a cui è necessario fare riferimento in modo esplicito.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Di seguito è riportato un esempio degli stili dichiarati sopra utilizzati.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Blocchi di testo con stili](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Per ulteriori informazioni, consultate [Creare uno stile per un controllo.](styles-templates-create-apply-style.md)

## <a name="controltemplates"></a>ControlTemplates

In WPFWPF, il <xref:System.Windows.Controls.ControlTemplate> di un controllo definisce l'aspetto del controllo. È possibile modificare la struttura e l'aspetto di un controllo definendone uno nuovo <xref:System.Windows.Controls.ControlTemplate> e assegnandolo a un controllo. In molti casi, i modelli offrono sufficiente flessibilità in modo che non sia necessario scrivere controlli personalizzati.

Ogni controllo dispone di un modello predefinito assegnato al [Control.Template](xref:System.Windows.Controls.Control.Template) proprietà. Il modello connette la presentazione visiva del controllo con le funzionalità del controllo. Poiché definisci un modello in XAML, puoi modificare l'aspetto del controllo senza scrivere codice. Ogni modello è progettato per un <xref:System.Windows.Controls.Button>controllo specifico, ad esempio un oggetto .

In genere si dichiara un `Resources` modello come risorsa nella sezione di un file XAML. Come per tutte le risorse, vengono applicate le regole di ambito.

I modelli di controllo sono molto più coinvolti di uno stile. Ciò è dovuto al fatto che il modello di controllo riscrive l'aspetto visivo dell'intero controllo, mentre uno stile applica semplicemente le modifiche delle proprietà al controllo esistente. Tuttavia, poiché il modello di un controllo viene applicato impostando il [Control.Template](xref:System.Windows.Controls.Control.Template) proprietà, è possibile utilizzare uno stile per definire o impostare un modello.

I progettisti in genere consentono di creare una copia di un modello esistente e modificarlo. Ad esempio, nella finestra di progettazione WPF di Visual Studio `CheckBox` selezionare un controllo, quindi fare clic con il pulsante destro del mouse e scegliere Modifica **modello** > Crea una**copia**. Questo comando genera uno *stile che definisce un modello*.

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

La modifica di una copia di un modello è un ottimo modo per imparare a usare i modelli. Invece di creare un nuovo modello vuoto, è più facile modificare una copia e modificare alcuni aspetti della presentazione visiva.

Per un esempio, vedere [Creare un modello per un controllo](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Si sarà notato che la risorsa modello definita nella sezione precedente utilizza [templateBinding Markup Extension](../../framework/wpf/advanced/templatebinding-markup-extension.md). A `TemplateBinding` è una forma ottimizzata di un'associazione per gli `{Binding RelativeSource={RelativeSource TemplatedParent}}`scenari di modello, analoga a un'associazione costruita con . `TemplateBinding`è utile per l'associazione di parti del modello alle proprietà del controllo. Ad esempio, ogni <xref:System.Windows.Controls.Control.BorderThickness> controllo dispone di una proprietà. Utilizzare `TemplateBinding` un per gestire l'elemento nel modello interessato da questa impostazione di controllo.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl e ItemsControl

Se <xref:System.Windows.Controls.ContentPresenter> un oggetto <xref:System.Windows.Controls.ControlTemplate> viene <xref:System.Windows.Controls.ContentControl>dichiarato <xref:System.Windows.Controls.ContentPresenter> in un oggetto <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.Content%2A> , verrà associato automaticamente alle proprietà e . Analogamente, <xref:System.Windows.Controls.ItemsPresenter> un che <xref:System.Windows.Controls.ControlTemplate> si <xref:System.Windows.Controls.ItemsControl> trova in <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> un <xref:System.Windows.Controls.ItemsControl.Items%2A> di un verrà associato automaticamente alle proprietà e .

## <a name="datatemplates"></a>DataTemplates

In questa app di <xref:System.Windows.Controls.ListBox> esempio è presente un controllo associato a un elenco di foto.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Questo <xref:System.Windows.Controls.ListBox> al momento è simile al seguente.

![ListBox prima dell'applicazione del modello](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

La maggior parte dei controlli include un tipo di contenuto che spesso deriva da dati che si sceglie di associare. In questo esempio i dati sono l'elenco di foto. In WPFWPF si <xref:System.Windows.DataTemplate> usa un per definire la rappresentazione visiva dei dati. Fondamentalmente, ciò <xref:System.Windows.DataTemplate> che si inserisce in un determina l'aspetto dei dati nell'app sottoposta a rendering.

Nell'app di esempio `Photo` ogni `Source` oggetto personalizzato ha una proprietà di tipo stringa che specifica il percorso del file dell'immagine. Gli oggetti foto in questo momento appaiono come percorsi file.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Affinché le foto vengano visualizzate <xref:System.Windows.DataTemplate> come immagini, è necessario creare una risorsa.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Si noti che <xref:System.Windows.DataTemplate.DataType%2A> la <xref:System.Windows.Style.TargetType%2A> proprietà <xref:System.Windows.Style>è simile alla proprietà dell'oggetto . Se <xref:System.Windows.DataTemplate> si trova nella sezione resources, <xref:System.Windows.DataTemplate.DataType%2A> quando si specifica la `x:Key`proprietà <xref:System.Windows.DataTemplate> su un tipo e si ometti un oggetto , l'oggetto viene applicato ogni volta che tale tipo viene visualizzato. È sempre possibile assegnare <xref:System.Windows.DataTemplate> l'oggetto `x:Key` con e `StaticResource` quindi impostarlo come proprietà che accettano <xref:System.Windows.DataTemplate> tipi, ad esempio la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà o la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà .

Essenzialmente, <xref:System.Windows.DataTemplate> l'oggetto nell'esempio precedente definisce che ogni volta che è presente un `Photo` oggetto, deve essere visualizzato come un <xref:System.Windows.Controls.Image> oggetto all'interno di un <xref:System.Windows.Controls.Border>oggetto . Con <xref:System.Windows.DataTemplate>questo , la nostra applicazione ora si presenta così.

![Foto](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Il modello di applicazione di modelli di dati fornisce altre funzionalità. Ad esempio, se si visualizzano dati di <xref:System.Windows.Controls.HeaderedItemsControl> raccolta che <xref:System.Windows.Controls.Menu> contengono <xref:System.Windows.Controls.TreeView>altre raccolte <xref:System.Windows.HierarchicalDataTemplate>utilizzando un tipo, ad esempio a o , è presente l'opzione . Un'altra funzionalità di <xref:System.Windows.Controls.DataTemplateSelector>modelli di dati è <xref:System.Windows.DataTemplate> la , che consente di scegliere un da utilizzare in base alla logica personalizzata. Per altre informazioni, vedere [Cenni preliminari sui modelli di dati](../../framework/wpf/data/data-templating-overview.md), in cui vengono discusse più dettagliatamente le diverse caratteristiche dei modelli di dati.

## <a name="triggers"></a>Trigger

Un trigger imposta proprietà o avvia azioni, ad esempio un'animazione, quando un valore di proprietà cambia o quando viene generato un evento. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>e <xref:System.Windows.DataTemplate> tutti `Triggers` dispongono di una proprietà che può contenere un set di trigger. Esistono diversi tipi di trigger.

### <a name="propertytriggers"></a>PropertyTriggers

Oggetto <xref:System.Windows.Trigger> che imposta i valori delle proprietà o avvia azioni in base al valore di una proprietà viene definito trigger di proprietà.

Per illustrare come utilizzare i trigger <xref:System.Windows.Controls.ListBoxItem> di proprietà, è possibile rendere ognuno parzialmente trasparente a meno che non sia selezionato. Lo stile seguente <xref:System.Windows.UIElement.Opacity%2A> imposta <xref:System.Windows.Controls.ListBoxItem> il `0.5`valore di a su . Quando <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> la `true`proprietà è <xref:System.Windows.UIElement.Opacity%2A> , tuttavia, l'oggetto è impostato su `1.0`.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

In questo <xref:System.Windows.Trigger> esempio viene utilizzato un oggetto <xref:System.Windows.Trigger> per impostare <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> un valore di proprietà, ma si noti che la classe dispone anche delle proprietà e che consentono a un trigger di eseguire azioni.

Si noti che la <xref:System.Windows.FrameworkElement.MaxHeight%2A> proprietà dell'oggetto è impostata su <xref:System.Windows.Controls.ListBoxItem> `75`. Nella figura seguente, il terzo elemento è l'elemento selezionato.

![ListView con stile](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger e storyboard

Un altro tipo <xref:System.Windows.EventTrigger>di trigger è il , che avvia un set di azioni in base all'occorrenza di un evento. Ad esempio, <xref:System.Windows.EventTrigger> gli oggetti seguenti specificano che <xref:System.Windows.Controls.ListBoxItem>quando <xref:System.Windows.FrameworkElement.MaxHeight%2A> il puntatore del `90` mouse `0.2` entra in , la proprietà viene animata su un valore di in un secondo periodo. Quando il puntatore del mouse viene spostato dall'elemento, la proprietà torna al valore originale in un `1` secondo. Si noti come non <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> è necessario <xref:System.Windows.ContentElement.MouseLeave> specificare un valore per l'animazione. L'animazione è infatti in grado di tenere traccia del valore originale.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Per ulteriori informazioni, vedere [Panoramica degli storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

Nella figura seguente, il mouse punta al terzo elemento.

![Schermata di esempio di stile](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger e MultiDataTrigger

Inoltre, <xref:System.Windows.Trigger> esistono <xref:System.Windows.EventTrigger>altri tipi di trigger. <xref:System.Windows.MultiTrigger>consente di impostare i valori delle proprietà in base a più condizioni. È <xref:System.Windows.DataTrigger> possibile <xref:System.Windows.MultiDataTrigger> utilizzare e quando la proprietà della condizione è associata a dati.

## <a name="visual-states"></a>Stati visivi

I controlli sono sempre in uno **stato**specifico. Ad esempio, quando il mouse si sposta sulla superficie di un controllo, `MouseOver`il controllo viene considerato in uno stato comune di . Un controllo senza uno stato specifico viene `Normal` considerato nello stato comune. gli Stati sono suddivisi in gruppi e gli `CommonStates`stati menzionati in precedenza fanno parte del gruppo di stati. La maggior parte dei `CommonStates` `FocusStates`controlli dispone di due gruppi di stati: e . Di ogni gruppo di stato applicato a un controllo, un controllo `CommonStates.MouseOver` `FocusStates.Unfocused`si trova sempre in uno stato di ogni gruppo, ad esempio e . Tuttavia, un controllo non può trovarsi in due `CommonStates.Normal` stati `CommonStates.Disabled`diversi all'interno dello stesso gruppo, ad esempio e . Ecco una tabella di stati che la maggior parte dei controlli riconosce e usa.

| Nome VisualState | Nome VisualStateGroup | Descrizione |
| ---------------- | --------------------- | ----------- |
| Normale           | CommonStates          | Lo stato predefinito. |
| MouseOver        | CommonStates          | Il puntatore del mouse è posizionato sul controllo. |
| Premuto          | CommonStates          | Il controllo è premuto. |
| Disabled         | CommonStates          | Il controllo è disabilitato. |
| Con stato attivo          | FocusStates           | Il controllo ha lo stato attivo. |
| Con stato non attivo        | FocusStates           | Il controllo non ha lo stato attivo. |

Definendo <xref:System.Windows.VisualStateManager?displayProperty=fullName> un sull'elemento radice di un modello di controllo, è possibile attivare le animazioni quando un controllo entra in uno stato specifico. Il `VisualStateManager` dichiara quali combinazioni di <xref:System.Windows.VisualStateGroup> e <xref:System.Windows.VisualState> per guardare. Quando il controllo entra in uno stato di `VisaulStateManager` controllo, viene avviata l'animazione definita dall'oggetto.

Ad esempio, il codice `CommonStates.MouseOver` XAML seguente controlla lo stato `backgroundElement`per animare il colore di riempimento dell'elemento denominato . Quando il controllo `CommonStates.Normal` torna allo stato, viene `backgroundElement` ripristinato il colore di riempimento dell'elemento denominato.

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

Per altre informazioni sugli storyboard, vedere [Cenni preliminari](../../framework/wpf/graphics-multimedia/storyboards-overview.md)sugli storyboard.

## <a name="shared-resources-and-themes"></a>Risorse e temi condivisi

Un'app WPF tipica potrebbe avere più risorse dell'interfaccia utente che vengono applicate in tutta l'app. Collettivamente, questo set di risorse può essere considerato il tema per l'app. WPFWPF fornisce il supporto per la creazione di pacchetti di risorse <xref:System.Windows.ResourceDictionary> dell'interfaccia utente come tema usando un dizionario risorse incapsulato come classe.

I temi WPFWPF vengono definiti usando il meccanismo di stile e modelli esposto da WPFWPF per la personalizzazione degli oggetti visivi di qualsiasi elemento.

Le risorse del tema WPF vengono archiviate nei dizionari risorse incorporati. Questi dizionari risorse devono essere incorporati all'interno di un assembly firmato e possono essere incorporati nello stesso assembly come codice o in un assembly affiancato. Per PresentationFramework.dll, l'assembly che contiene controlli WPFWPF, le risorse del tema si trovano in una serie di assembly side-by-side.

Il tema diventa l'ultimo posto in cui cercare lo stile di un elemento. In genere, la ricerca inizierà alzando la struttura ad albero dell'elemento cercando una risorsa appropriata, quindi cerca nella raccolta di risorse dell'app e infine esegui una query nel sistema. Questo offre agli sviluppatori di app la possibilità di ridefinire lo stile per qualsiasi oggetto a livello di albero o app prima di raggiungere il tema.

È possibile definire i dizionari risorse come singoli file che consentono di riutilizzare un tema in più app. È inoltre possibile creare temi scambiabili definendo più dizionari risorse che forniscono gli stessi tipi di risorse ma con valori diversi. La ridefinizione di questi stili o di altre risorse a livello di app è l'approccio consigliato per l'skinning di un'app.

Per condividere un set di risorse, inclusi stili e modelli, tra <xref:System.Windows.ResourceDictionary> le app, `shared.xaml` puoi creare un file XAML e definire un file che includa il riferimento a un file.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

È la condivisione di `shared.xaml`, <xref:System.Windows.ResourceDictionary> che a sua volta definisce un che contiene un set di risorse di stile e pennello, che consente ai controlli in un'app di avere un aspetto coerente.

Per ulteriori informazioni, vedere [Dizionari risorse uniti](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Se si sta creando un tema per il controllo personalizzato, vedere la sezione **Definizione delle risorse a livello** di tema di [Cenni](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)preliminari sulla creazione di controlli .

## <a name="see-also"></a>Vedere anche

- [URI di tipo pack in WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Procedura: trovare elementi generati da un oggetto ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Trova elementi generati da DataTemplate](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
