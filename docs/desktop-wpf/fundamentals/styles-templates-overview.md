---
title: Stili e modelli
description: Informazioni sulle risorse XAML in Windows Presentation Foundation (WPF) per .NET Core. Informazioni sui tipi di risorse XAML correlati a stili e temi.
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

Gli stili e i modelli Windows Presentation Foundation (WPF) fanno riferimento a una suite di funzionalità che consentono agli sviluppatori e ai progettisti di creare effetti visivamente accattivanti e un aspetto coerente per il proprio prodotto. Quando si Personalizza l'aspetto di un'app, si desidera un modello di stili e modelli sicuro che consente la manutenzione e la condivisione dell'aspetto all'interno e tra le app. WPF fornisce tale modello.

Un'altra funzionalità del modello di stile WPF è la separazione tra presentazione e logica. I progettisti possono lavorare sull'aspetto di un'app usando solo XAML nello stesso momento in cui gli sviluppatori lavorano sulla logica di programmazione usando C# o Visual Basic.

Questa panoramica è incentrata sugli aspetti relativi allo stile e alla creazione di modelli dell'app e non descrive alcun concetto di associazione dati. Per informazioni sul data binding, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).

È importante comprendere le risorse, che consentono di riutilizzare gli stili e i modelli. Per altre informazioni sulle risorse, vedere [Risorse XAML](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Esempio

Il codice di esempio fornito in questa panoramica si basa su una [semplice applicazione di esplorazione foto](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) mostrata nella figura seguente.

![ListView con stile](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

Questo esempio usa stili e modelli per creare un'esperienza utente visivamente accattivante. Nell'esempio sono presenti <xref:System.Windows.Controls.TextBlock> due elementi e <xref:System.Windows.Controls.ListBox> un controllo associato a un elenco di immagini.

Per l'esempio completo, vedere [Introduzione a un esempio di applicazione di stili e di modelli](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Stili

È possibile considerare un <xref:System.Windows.Style> come un modo pratico per applicare un set di valori di proprietà a più elementi. È possibile usare uno stile su qualsiasi elemento che deriva <xref:System.Windows.FrameworkElement> da o <xref:System.Windows.FrameworkContentElement> , ad esempio <xref:System.Windows.Window> o. <xref:System.Windows.Controls.Button>

Il modo più comune per dichiarare uno stile è come una risorsa nella `Resources` sezione di un file XAML. Poiché gli stili sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. Inserire semplicemente, dove si dichiara uno stile influiscono sul punto in cui è possibile applicare lo stile. Se ad esempio si dichiara lo stile nell'elemento radice del file XAML della definizione dell'app, lo stile può essere usato in qualsiasi punto dell'app.

Il codice XAML seguente, ad esempio, dichiara due stili per un `TextBlock`oggetto, uno applicato automaticamente a `TextBlock` tutti gli elementi e un altro a cui è necessario fare riferimento in modo esplicito.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Di seguito è riportato un esempio degli stili dichiarati sopra usati.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![TextBlock con stile](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Per altre informazioni, vedere [creare uno stile per un controllo](styles-templates-create-apply-style.md).

## <a name="controltemplates"></a>ControlTemplates

In WPF, l' <xref:System.Windows.Controls.ControlTemplate> oggetto di un controllo definisce l'aspetto del controllo. Per modificare la struttura e l'aspetto di un controllo, è possibile definire <xref:System.Windows.Controls.ControlTemplate> un nuovo oggetto e assegnarlo a un controllo. In molti casi, i modelli offrono una flessibilità sufficiente, in modo da non dover scrivere controlli personalizzati.

Ogni controllo ha un modello predefinito assegnato alla proprietà [Control. template](xref:System.Windows.Controls.Control.Template) . Il modello connette la presentazione visiva del controllo con le funzionalità del controllo. Poiché si definisce un modello in XAML, è possibile modificare l'aspetto del controllo senza scrivere codice. Ogni modello è progettato per un controllo specifico, ad esempio <xref:System.Windows.Controls.Button>.

In genere si dichiara un modello come risorsa nella `Resources` sezione di un file XAML. Come per tutte le risorse, si applicano le regole di ambito.

I modelli di controllo sono molto più interessati rispetto a uno stile. Questo perché il modello di controllo riscrive l'aspetto visivo dell'intero controllo, mentre uno stile applica semplicemente le modifiche alle proprietà al controllo esistente. Tuttavia, poiché il modello di un controllo viene applicato impostando la proprietà [Control. template](xref:System.Windows.Controls.Control.Template) , è possibile usare uno stile per definire o impostare un modello.

Le finestre di progettazione consentono in genere di creare una copia di un modello esistente e di modificarla. Ad esempio, nella finestra di progettazione WPF di Visual Studio selezionare `CheckBox` un controllo, quindi fare clic con il pulsante destro del mouse e scegliere **modifica modello** > **Crea una copia**. Questo comando genera uno *stile che definisce un modello*.

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

La modifica di una copia di un modello è un ottimo modo per apprendere il funzionamento dei modelli. Anziché creare un nuovo modello vuoto, è più semplice modificare una copia e modificare alcuni aspetti della presentazione visiva.

Per un esempio, vedere [creare un modello per un controllo](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Si può notare che la risorsa modello definita nella sezione precedente usa l'estensione di [markup TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md). Un `TemplateBinding` è una forma ottimizzata di un'associazione per gli scenari di modello, analoga a `{Binding RelativeSource={RelativeSource TemplatedParent}}`un'associazione costruita con. `TemplateBinding`è utile per l'associazione di parti del modello alle proprietà del controllo. Ogni controllo dispone ad esempio di una <xref:System.Windows.Controls.Control.BorderThickness> proprietà. Utilizzare un `TemplateBinding` oggetto per gestire l'elemento del modello interessato da questa impostazione del controllo.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl e ItemsControl

Se un <xref:System.Windows.Controls.ContentPresenter> oggetto viene dichiarato in <xref:System.Windows.Controls.ControlTemplate> di un <xref:System.Windows.Controls.ContentControl>oggetto, <xref:System.Windows.Controls.ContentPresenter> l'oggetto verrà associato automaticamente <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> alle <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà e. Analogamente, <xref:System.Windows.Controls.ItemsPresenter> un oggetto che si <xref:System.Windows.Controls.ControlTemplate> trova in <xref:System.Windows.Controls.ItemsControl> di un oggetto verrà associato <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> automaticamente <xref:System.Windows.Controls.ItemsControl.Items%2A> alle proprietà e.

## <a name="datatemplates"></a>DataTemplate

In questa app di esempio è presente un <xref:System.Windows.Controls.ListBox> controllo associato a un elenco di foto.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Questo <xref:System.Windows.Controls.ListBox> aspetto è attualmente simile al seguente.

![ListBox prima dell'applicazione del modello](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

La maggior parte dei controlli include un tipo di contenuto che spesso deriva da dati che si sceglie di associare. In questo esempio i dati sono l'elenco di foto. In WPF si usa un oggetto <xref:System.Windows.DataTemplate> per definire la rappresentazione visiva dei dati. In sostanza, ciò che si inserisce <xref:System.Windows.DataTemplate> in un oggetto determina l'aspetto dei dati nell'app di cui è stato eseguito il rendering.

Nell'app di esempio ogni oggetto personalizzato `Photo` ha una `Source` proprietà di tipo stringa che specifica il percorso del file dell'immagine. Gli oggetti foto in questo momento appaiono come percorsi file.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Per visualizzare le foto come immagini, creare un <xref:System.Windows.DataTemplate> come risorsa.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Si noti che <xref:System.Windows.DataTemplate.DataType%2A> la proprietà è simile alla <xref:System.Windows.Style.TargetType%2A> proprietà di <xref:System.Windows.Style>. Se si <xref:System.Windows.DataTemplate> trova nella sezione Resources, quando si specifica <xref:System.Windows.DataTemplate.DataType%2A> la proprietà su un tipo e si `x:Key`omette un <xref:System.Windows.DataTemplate> oggetto, l'oggetto viene applicato ogni volta che il tipo viene visualizzato. È sempre possibile assegnare l' <xref:System.Windows.DataTemplate> oggetto con un oggetto `x:Key` e impostarlo come `StaticResource` per le proprietà che accettano <xref:System.Windows.DataTemplate> i tipi, ad esempio la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà o la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.

<xref:System.Windows.DataTemplate> In pratica, nell'esempio precedente viene definito che, ogni volta che `Photo` è presente un oggetto, deve essere <xref:System.Windows.Controls.Image> visualizzato come <xref:System.Windows.Controls.Border>all'interno di un oggetto. A questo <xref:System.Windows.DataTemplate>punto, l'app ha un aspetto simile al seguente.

![Foto](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Il modello di applicazione di modelli di dati fornisce altre funzionalità. Se, ad esempio, si visualizzano dati della raccolta che contengono altre raccolte <xref:System.Windows.Controls.HeaderedItemsControl> che usano un tipo <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.TreeView>, ad esempio o, è <xref:System.Windows.HierarchicalDataTemplate>presente l'oggetto. Un'altra funzionalità per la <xref:System.Windows.Controls.DataTemplateSelector>creazione di modelli di dati è, che <xref:System.Windows.DataTemplate> consente di scegliere un da usare in base alla logica personalizzata. Per altre informazioni, vedere [Cenni preliminari sui modelli di dati](../../framework/wpf/data/data-templating-overview.md), in cui vengono discusse più dettagliatamente le diverse caratteristiche dei modelli di dati.

## <a name="triggers"></a>Trigger

Un trigger imposta proprietà o avvia azioni, ad esempio un'animazione, quando un valore di proprietà cambia o quando viene generato un evento. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>e <xref:System.Windows.DataTemplate> dispongono di una `Triggers` proprietà che può contenere un set di trigger. Esistono diversi tipi di trigger.

### <a name="propertytriggers"></a>PropertyTriggers

Un <xref:System.Windows.Trigger> oggetto che imposta i valori delle proprietà o avvia azioni in base al valore di una proprietà viene chiamato trigger di proprietà.

Per illustrare come usare i trigger di proprietà, è possibile <xref:System.Windows.Controls.ListBoxItem> rendere ogni parte parzialmente trasparente a meno che non sia selezionata. Lo stile seguente imposta il <xref:System.Windows.UIElement.Opacity%2A> valore di <xref:System.Windows.Controls.ListBoxItem> su `0.5`. Quando la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> proprietà è `true`, tuttavia, l' <xref:System.Windows.UIElement.Opacity%2A> oggetto è impostato `1.0`su.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

Questo esempio usa un <xref:System.Windows.Trigger> oggetto per impostare un valore di proprietà, ma si <xref:System.Windows.Trigger> noti che la classe <xref:System.Windows.TriggerBase.EnterActions%2A> dispone <xref:System.Windows.TriggerBase.ExitActions%2A> anche delle proprietà e che consentono a un trigger di eseguire le azioni.

Si noti che <xref:System.Windows.FrameworkElement.MaxHeight%2A> la proprietà di viene impostata su `75` <xref:System.Windows.Controls.ListBoxItem> Nella figura seguente il terzo elemento è l'elemento selezionato.

![ListView con stile](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger e storyboard

Un altro tipo di trigger è <xref:System.Windows.EventTrigger>, che avvia un set di azioni in base all'occorrenza di un evento. Ad esempio, gli oggetti <xref:System.Windows.EventTrigger> seguenti specificano che quando il puntatore del mouse <xref:System.Windows.Controls.ListBoxItem>entra nell' <xref:System.Windows.FrameworkElement.MaxHeight%2A> oggetto, la proprietà aggiunge un'animazione `90` a un `0.2` valore di in un secondo punto. Quando il puntatore del mouse viene spostato dall'elemento, la proprietà torna al valore originale in un `1` secondo. Si noti che non è necessario specificare un <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valore per l' <xref:System.Windows.ContentElement.MouseLeave> animazione. L'animazione è infatti in grado di tenere traccia del valore originale.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Per ulteriori informazioni, vedere [Cenni preliminari sugli storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

Nella figura seguente il mouse punta al terzo elemento.

![Schermata di esempio dello stile](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger e MultiDataTrigger

Oltre a <xref:System.Windows.Trigger> e <xref:System.Windows.EventTrigger>, esistono altri tipi di trigger. <xref:System.Windows.MultiTrigger>consente di impostare i valori delle proprietà in base a più condizioni. Usare <xref:System.Windows.DataTrigger> e <xref:System.Windows.MultiDataTrigger> quando la proprietà della condizione è associata a dati.

## <a name="visual-states"></a>Stati di visualizzazione

I controlli sono sempre in uno **stato**specifico. Ad esempio, quando il mouse viene spostato sulla superficie di un controllo, il controllo viene considerato in uno stato comune di `MouseOver`. Un controllo senza uno stato specifico viene considerato nello stato comune `Normal` . Gli Stati sono suddivisi in gruppi e gli stati citati in precedenza fanno parte del `CommonStates`gruppo di Stati. La maggior parte dei controlli dispone di `CommonStates` due `FocusStates`gruppi di stati: e. Di ogni gruppo di stati applicato a un controllo, un controllo è sempre in uno stato di ogni gruppo, ad `CommonStates.MouseOver` esempio `FocusStates.Unfocused`e. Tuttavia, un controllo non può trovarsi in due stati diversi all'interno dello stesso gruppo `CommonStates.Normal` , `CommonStates.Disabled`ad esempio e. Ecco una tabella di Stati che la maggior parte dei controlli riconosce e USA.

| Nome VisualState | Nome VisualStateGroup | Descrizione |
| ---------------- | --------------------- | ----------- |
| Normale           | CommonStates          | Lo stato predefinito. |
| MouseOver        | CommonStates          | Il puntatore del mouse è posizionato sul controllo. |
| Premuto          | CommonStates          | Il controllo è premuto. |
| Disabled         | CommonStates          | Il controllo è disabilitato. |
| Con stato attivo          | FocusStates           | Il controllo ha lo stato attivo. |
| Con stato non attivo        | FocusStates           | Il controllo non ha lo stato attivo. |

Definendo un oggetto <xref:System.Windows.VisualStateManager?displayProperty=fullName> sull'elemento radice di un modello di controllo, è possibile attivare animazioni quando un controllo entra in uno stato specifico. Dichiara `VisualStateManager` le combinazioni di <xref:System.Windows.VisualStateGroup> e <xref:System.Windows.VisualState> da controllare. Quando il controllo entra in uno stato controllato, `VisaulStateManager` viene avviata l'animazione definita da.

Il codice XAML seguente, ad esempio, controlla `CommonStates.MouseOver` lo stato per animare il colore di riempimento dell'elemento `backgroundElement`denominato. Quando il controllo torna allo `CommonStates.Normal` stato, viene ripristinato il colore di riempimento dell' `backgroundElement` elemento denominato.

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

Per ulteriori informazioni sugli storyboard, vedere [Cenni preliminari sugli storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Risorse condivise e temi

Una tipica app WPF potrebbe avere più risorse dell'interfaccia utente che vengono applicate nell'app. Collettivamente, questo set di risorse può essere considerato il tema per l'app. WPF fornisce supporto per la creazione di pacchetti di risorse dell'interfaccia utente come tema usando un dizionario risorse incapsulato come <xref:System.Windows.ResourceDictionary> classe.

I temi WPF vengono definiti utilizzando il meccanismo di applicazione di stili e modelli esposto da WPF per la personalizzazione degli oggetti visivi di qualsiasi elemento.

Le risorse del tema WPF sono archiviate in dizionari risorse incorporati. Questi dizionari risorse devono essere incorporati all'interno di un assembly firmato e possono essere incorporati nello stesso assembly come codice o in un assembly affiancato. Per PresentationFramework. dll, l'assembly che contiene i controlli WPF, le risorse del tema si trovano in una serie di assembly affiancati.

Il tema diventa l'ultimo posto in cui cercare lo stile di un elemento. In genere, la ricerca inizia con l'analisi dell'albero degli elementi che cerca una risorsa appropriata, quindi Cerca nella raccolta di risorse dell'app e infine esegue una query nel sistema. Ciò offre agli sviluppatori di app la possibilità di ridefinire lo stile per qualsiasi oggetto a livello di albero o di app prima di raggiungere il tema.

È possibile definire dizionari risorse come singoli file che consentono di riutilizzare un tema in più app. È inoltre possibile creare temi scambiabili definendo più dizionari risorse che forniscono gli stessi tipi di risorse ma con valori diversi. La ridefinizione di questi stili o altre risorse a livello di app è l'approccio consigliato per la scuoiatura di un'app.

Per condividere un set di risorse, inclusi stili e modelli, tra le app, è possibile creare un file XAML e definire <xref:System.Windows.ResourceDictionary> un che includa un `shared.xaml` riferimento a un file.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Si tratta della condivisione di `shared.xaml`, che a sua volta <xref:System.Windows.ResourceDictionary> definisce un oggetto che contiene un set di risorse di stile e pennello, che consente ai controlli di un'app di avere un aspetto coerente.

Per altre informazioni, vedere [dizionari risorse Uniti](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Se si sta creando un tema per il controllo personalizzato, vedere la sezione **definizione delle risorse a livello di tema** di [Cenni preliminari](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)sulla creazione di controlli.

## <a name="see-also"></a>Vedere anche

- [URI di tipo pack in WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Procedura: trovare elementi generati da un oggetto ControlTemplate](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Trovare elementi generati da un oggetto DataTemplate](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
