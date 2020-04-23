---
title: Creare un modello in WPF-desktop .NET
description: Informazioni su come creare e fare riferimento a un modello di controllo in Windows Presentation Foundation e .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "82071248"
---
# <a name="create-a-template-for-a-control"></a>Creare un modello per un controllo

Con Windows Presentation Foundation (WPF), è possibile personalizzare la struttura visiva e il comportamento di un controllo esistente con un modello riutilizzabile. I modelli possono essere applicati a livello globale per l'applicazione, le finestre e le pagine o direttamente ai controlli. La maggior parte degli scenari che richiedono la creazione di un nuovo controllo può essere analizzata creando invece un nuovo modello per un controllo esistente.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

In questo articolo si esaminerà la creazione di <xref:System.Windows.Controls.ControlTemplate> un nuovo <xref:System.Windows.Controls.Button> oggetto per il controllo.

## <a name="when-to-create-a-controltemplate"></a>Quando creare un oggetto ControlTemplate

I controlli hanno molte proprietà, ad <xref:System.Windows.Controls.Border.Background%2A>esempio <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>. Queste proprietà controllano aspetti diversi dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate. Ad esempio, è possibile impostare la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà su blu e <xref:System.Windows.Controls.Control.FontStyle%2A> su corsivo in un <xref:System.Windows.Controls.CheckBox>oggetto. Quando si desidera personalizzare l'aspetto del controllo oltre a ciò che è possibile impostare per le altre proprietà del controllo, è necessario <xref:System.Windows.Controls.ControlTemplate>creare un oggetto.

Nella maggior parte delle interfacce utente, un pulsante ha lo stesso aspetto generale: un rettangolo con testo. Se si desidera creare un pulsante arrotondato, è possibile creare un nuovo controllo che eredita dal pulsante o ricrea la funzionalità del pulsante. Inoltre, il nuovo controllo utente fornirebbe l'oggetto visivo circolare.

È possibile evitare di creare nuovi controlli personalizzando il layout visivo di un controllo esistente. Con un pulsante arrotondato è possibile creare <xref:System.Windows.Controls.ControlTemplate> un oggetto con il layout visivo desiderato.

D'altra parte, se è necessario un controllo con nuove funzionalità, proprietà diverse e nuove impostazioni, creare un nuovo <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Prerequisiti

Creare una nuova applicazione WPF e in *MainWindow. XAML* (o in un'altra finestra di propria scelta) impostare le proprietà seguenti nell'elemento ** \<>della finestra** :

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

Impostare il contenuto dell'elemento ** \<>della finestra** sul seguente codice XAML:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Alla fine, il file *MainWindow. XAML* dovrebbe essere simile al seguente:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Se si esegue l'applicazione, l'aspetto sarà simile al seguente:

![Finestra WPF con due pulsanti senza stile](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Creare un ControlTemplate

Il modo più comune per dichiarare un <xref:System.Windows.Controls.ControlTemplate> è come una risorsa nella `Resources` sezione di un file XAML. Poiché i modelli sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. Inserire semplicemente, dove si dichiara un modello influiscono sul punto in cui è possibile applicare il modello. Se, ad esempio, si dichiara il modello nell'elemento radice del file XAML della definizione dell'applicazione, il modello può essere usato in qualsiasi punto dell'applicazione. Se si definisce il modello in una finestra, solo i controlli in tale finestra possono usare il modello.

Per iniziare, aggiungere un `Window.Resources` elemento al file *MainWindow. XAML* :

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Creare una nuova ** \<>ControlTemplate** con le seguenti proprietà impostate:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Questo modello di controllo sarà semplice:

- elemento radice per il controllo,<xref:System.Windows.Controls.Grid>
- oggetto <xref:System.Windows.Shapes.Ellipse> per creare l'aspetto arrotondato del pulsante
- oggetto <xref:System.Windows.Controls.ContentPresenter> per visualizzare il contenuto del pulsante specificato dall'utente

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate>, è comunque possibile usare le proprietà pubbliche per modificare l'aspetto del controllo. L'estensione di markup [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) associa una proprietà di un elemento che si trova in <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica definita dal controllo. Quando si utilizza un oggetto [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), si abilitano le proprietà del controllo in modo che fungano da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Ellipse

Si noti che **:::no-loc text="Fill":::** le **:::no-loc text="Stroke":::** proprietà e dell'elemento ** \<ellisse>** sono associate alle proprietà <xref:System.Windows.Controls.Control.Foreground> e <xref:System.Windows.Controls.Control.Background> del controllo.

### <a name="contentpresenter"></a>ContentPresenter

Al modello viene aggiunto anche un [ \<elemento>ContentPresenter](xref:System.Windows.Controls.ContentPresenter) . Poiché questo modello è progettato per un pulsante, prendere in considerazione che il pulsante eredita da <xref:System.Windows.Controls.ContentControl>. Il pulsante presenta il contenuto dell'elemento. È possibile impostare qualsiasi elemento all'interno del pulsante, ad esempio testo normale o anche un altro controllo. Entrambi i pulsanti validi sono i seguenti:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

In entrambi gli esempi precedenti, il testo e la casella di controllo vengono impostati come proprietà [Button. Content](xref:System.Windows.Controls.ContentControl.Content) . Qualsiasi elemento viene impostato in quanto il contenuto può essere presentato tramite un ** \<>ContentPresenter **, che corrisponde al modello.

Se l' <xref:System.Windows.Controls.ControlTemplate> oggetto viene applicato a <xref:System.Windows.Controls.ContentControl> un tipo, ad esempio `Button`, un <xref:System.Windows.Controls.ContentPresenter> oggetto viene cercato nell'albero degli elementi. Se `ContentPresenter` viene trovato, il modello associa automaticamente la <xref:System.Windows.Controls.ContentControl.Content> proprietà del controllo a. `ContentPresenter`

## <a name="use-the-template"></a>Modello

Trovare i pulsanti dichiarati all'inizio di questo articolo.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Impostare la <xref:System.Windows.Controls.Control.Template> proprietà del secondo pulsante sulla `roundbutton` risorsa:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Se si esegue il progetto e si osserva il risultato, si noterà che il pulsante ha uno sfondo arrotondato.

![Finestra WPF con un pulsante ovale del modello](media/create-apply-template/styled-button.png)

Si noterà che il pulsante non è un cerchio ma è inclinato. A causa della modalità di funzionamento dell' ** \<ellisse>** elemento, si espande sempre per riempire lo spazio disponibile. Rendere uniforme il cerchio modificando le proprietà **:::no-loc text="width":::** e **:::no-loc text="height":::** del pulsante sullo stesso valore:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Finestra WPF con un pulsante circolare del modello](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Aggiungere un trigger

Anche se un pulsante con un modello applicato è diverso, si comporta allo stesso modo di qualsiasi altro pulsante. Se si preme il pulsante, viene <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generato l'evento. Tuttavia, è possibile notare che quando si sposta il puntatore del mouse sul pulsante, gli oggetti visivi del pulsante non cambiano. Queste interazioni visive sono tutte definite dal modello.

Con l'evento dinamico e i sistemi di proprietà forniti da WPF, è possibile controllare una proprietà specifica per un valore e quindi ridefinire lo stile del modello quando appropriato. In questo esempio si osserverà la <xref:System.Windows.UIElement.IsMouseOver> proprietà del pulsante. Quando il mouse si trova sul controllo, applicare uno stile all' ** \<ellisse>** con un nuovo colore. Questo tipo di trigger è noto come *PropertyTrigger*.

Per eseguire questa operazione, è necessario aggiungere un nome al ** \<>ellisse** a cui è possibile fare riferimento. Assegnargli il nome di **BackgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Successivamente, aggiungere un nuovo <xref:System.Windows.Trigger> oggetto alla raccolta [ControlTemplate. Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) . Il trigger osserverà l' `IsMouseOver` evento per il valore `true`.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Aggiungere quindi un ** \<Setter>** al ** \<trigger>** che modifica la proprietà **Fill** dell' ** \<ellisse>** in un nuovo colore.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Eseguire il progetto. Si noti che quando si sposta il puntatore del mouse sul pulsante, il colore dell' ** \<ellisse>** cambia.

![pulsante di spostamento del mouse su WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Usare un VisualState

Gli Stati di visualizzazione vengono definiti e attivati da un controllo. Ad esempio, quando il mouse viene spostato sopra il controllo, lo `CommonStates.MouseOver` stato viene attivato. È possibile aggiungere un'animazione alle modifiche delle proprietà in base allo stato corrente del controllo. Nella sezione precedente è stato usato un ** \<>PropertyTrigger** per modificare il primo piano del pulsante in `AliceBlue` quando la `IsMouseOver` proprietà era. `true` In alternativa, creare uno stato di visualizzazione che aggiunge un'animazione alla modifica di questo colore, fornendo una transizione senza problemi. Per altre informazioni su *controlli VisualState*, vedere [stili e modelli in WPF](../fundamentals/styles-templates-overview.md#visual-states).

Per convertire il ** \<>PropertyTrigger** in uno stato di visualizzazione animato, rimuovere prima di tutto l' ** \<elemento ControlTemplate. Triggers>** dal modello.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Quindi, nella ** \<griglia>** radice del modello di controllo, aggiungere l' ** \<elemento VisualStateManager. VisualStateGroups>** con un ** \<>VisualStateGroup** per. `CommonStates` Definire due Stati, `Normal` e `MouseOver`.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Tutte le animazioni definite in un oggetto ** \<VisualState>** vengono applicate quando lo stato viene attivato. Creare animazioni per ogni stato. Le animazioni vengono inserite all'interno di uno ** \<storyboard>** elemento. Per ulteriori informazioni sugli storyboard, vedere [Cenni preliminari sugli storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Normale

  Questo stato aggiunge un'animazione al riempimento dell'ellisse, ripristinando il `Background` colore del controllo.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Questo stato aggiunge un'animazione al `Background` colore dell'ellisse a un `Yellow`nuovo colore:.

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

Il ** \<>ControlTemplate** dovrebbe ora essere simile al seguente.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Eseguire il progetto. Si noti che quando si sposta il puntatore del mouse sul pulsante, il colore dell' ** \<ellisse>** viene animato.

![pulsante di spostamento del mouse su WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Passaggi successivi

- [Creare uno stile per un controllo in WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Stili e modelli in WPF](../fundamentals/styles-templates-overview.md)
- [Panoramica delle risorse XAML](../fundamentals/xaml-resources-define.md)
