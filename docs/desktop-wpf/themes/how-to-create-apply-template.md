---
title: Creare un modello in WPF - .NET Desktop
description: Informazioni su come creare e fare riferimento a un modello di controllo in Windows Presentation Foundation e .NET Core.Learn how to create and reference a control template in Windows Presentation Foundation and .NET Core.
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
# <a name="create-a-template-for-a-control"></a>Creare un modello per un controlloCreate a template for a control

Con Windows Presentation Foundation (WPF), è possibile personalizzare la struttura visiva e il comportamento di un controllo esistente con il proprio modello riutilizzabile. I modelli possono essere applicati globalmente all'applicazione, alle finestre e alle pagine o direttamente ai controlli. La maggior parte degli scenari che richiedono la creazione di un nuovo controllo possono essere coperti creando invece un nuovo modello per un controllo esistente.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

In questo articolo verrà esaminata <xref:System.Windows.Controls.ControlTemplate> la <xref:System.Windows.Controls.Button> creazione di una nuova per il controllo.

## <a name="when-to-create-a-controltemplate"></a>Quando creare un ControlTemplateWhen to create a ControlTemplate

I controlli hanno molte <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>proprietà, <xref:System.Windows.Controls.Control.FontFamily%2A>ad esempio , , e . Queste proprietà controllano diversi aspetti dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate. Ad esempio, è <xref:System.Windows.Controls.Control.Foreground%2A> possibile impostare <xref:System.Windows.Controls.Control.FontStyle%2A> la proprietà <xref:System.Windows.Controls.CheckBox>su blu e corsivo su un oggetto . Quando si desidera personalizzare l'aspetto del controllo oltre a quanto l'impostazione delle altre proprietà del controllo, creare un <xref:System.Windows.Controls.ControlTemplate>oggetto .

Nella maggior parte delle interfacce utente, un pulsante ha lo stesso aspetto generale: un rettangolo con del testo. Se si desidera creare un pulsante arrotondato, è possibile creare un nuovo controllo che eredita dal pulsante o ricrea la funzionalità del pulsante. Inoltre, il nuovo controllo utente fornirebbe l'oggetto visivo circolare.

È possibile evitare di creare nuovi controlli personalizzando il layout visivo di un controllo esistente. Con un pulsante arrotondato, si crea un <xref:System.Windows.Controls.ControlTemplate> con il layout visivo desiderato.

D'altra parte, se è necessario un controllo con nuove funzionalità, proprietà <xref:System.Windows.Controls.UserControl>diverse e nuove impostazioni, è necessario creare un nuovo file .

## <a name="prerequisites"></a>Prerequisiti

Creare una nuova applicazione WPF WPF e in *MainWindow.xaml* (o un'altra finestra di propria scelta) impostare le proprietà seguenti nell'elemento ** \<>Window:**

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

Impostare il ** \<** contenuto dell'elemento>Window sul codice XAML seguente:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Alla fine, il file *MainWindow.xaml* dovrebbe essere simile al seguente:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Se si esegue l'applicazione, è simile al seguente:

![Finestra WPF con due pulsanti senza stileWPF window with two unstyled buttons](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Creare un ControlTemplate

Il modo più comune <xref:System.Windows.Controls.ControlTemplate> per dichiarare un `Resources` è come risorsa nella sezione in un file XAML. Poiché i modelli sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. In parole povere, in cui si dichiara un modello influisce sulla posizione in cui il modello può essere applicato. Ad esempio, se si dichiara il modello nell'elemento radice del file XAML di definizione dell'applicazione, il modello può essere utilizzato in qualsiasi punto dell'applicazione. Se si definisce il modello in una finestra, solo i controlli in tale finestra possono utilizzare il modello.

Per iniziare, aggiungi `Window.Resources` un elemento al file *MainWindow.xaml:*

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Creare un nuovo ** \<controllo ControlTemplate>** con le proprietà seguenti impostate:Create a new ControlTemplate>with the following properties set:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Questo modello di controllo sarà semplice:This control template will be simple:

- un elemento radice per il controllo, un<xref:System.Windows.Controls.Grid>
- an <xref:System.Windows.Shapes.Ellipse> per disegnare l'aspetto arrotondato del pulsante
- a <xref:System.Windows.Controls.ContentPresenter> per visualizzare il contenuto del pulsante specificato dall'utente

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Quando si crea <xref:System.Windows.Controls.ControlTemplate>un nuovo oggetto , è comunque possibile utilizzare le proprietà pubbliche per modificare l'aspetto del controllo. Il [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup associa una proprietà <xref:System.Windows.Controls.ControlTemplate> di un elemento che si trova in un a una proprietà pubblica definita dal controllo. Quando si utilizza un [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), si abilitano le proprietà del controllo in modo che fungano da parametri per il modello. Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).

### <a name="ellipse"></a>Ellipse

Si **:::no-loc text="Fill":::** noti **:::no-loc text="Stroke":::** che le proprietà e dell'elemento ** \<** <xref:System.Windows.Controls.Control.Foreground> Ellipse>sono associate alle proprietà e <xref:System.Windows.Controls.Control.Background> del controllo.

### <a name="contentpresenter"></a>ContentPresenter

Un [ \<elemento ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) viene aggiunto anche al modello. Poiché questo modello è progettato per un pulsante, prendere in considerazione che il pulsante eredita da <xref:System.Windows.Controls.ContentControl>. Il pulsante presenta il contenuto dell'elemento. È possibile impostare qualsiasi elemento all'interno del pulsante, ad esempio testo normale o anche un altro controllo. Entrambi i pulsanti validi sono entrambi i seguenti:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

In entrambi gli esempi precedenti, il testo e la casella di controllo sono impostati come proprietà [Button.Content.](xref:System.Windows.Controls.ContentControl.Content) Qualunque sia il contenuto può essere presentato tramite un ** \<ContentPresenter>**, che è ciò che fa il modello.

Se <xref:System.Windows.Controls.ControlTemplate> l'oggetto <xref:System.Windows.Controls.ContentControl> viene applicato a `Button`un <xref:System.Windows.Controls.ContentPresenter> tipo, ad esempio un oggetto , viene eseguita la ricerca di a nella struttura ad albero dell'elemento. Se `ContentPresenter` l'oggetto viene trovato, il modello <xref:System.Windows.Controls.ContentControl.Content> associa `ContentPresenter`automaticamente la proprietà del controllo all'oggetto .

## <a name="use-the-template"></a>Modello

Trovare i pulsanti dichiarati all'inizio di questo articolo.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Impostare la proprietà <xref:System.Windows.Controls.Control.Template> del `roundbutton` secondo pulsante sulla risorsa:Set the second button's property to the resource:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Se si esegue il progetto e si guarda il risultato, si noterà che il pulsante ha uno sfondo arrotondato.

![Finestra WPF con un pulsante ovale del modelloWPF window with one template oval button](media/create-apply-template/styled-button.png)

Avrete notato che il pulsante non è un cerchio, ma è inclinato. A causa del funzionamento dell'elemento ** \<>Ellipse,** si espande sempre per riempire lo spazio disponibile. Rendere uniforme il cerchio modificando **:::no-loc text="width":::** le **:::no-loc text="height":::** proprietà e del pulsante sullo stesso valore:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Finestra WPF con un pulsante circolare del modelloWPF window with one template circular button](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Aggiungere un triggerAdd a Trigger

Anche se un pulsante con un modello applicato ha un aspetto diverso, si comporta come qualsiasi altro pulsante. Se si preme <xref:System.Windows.Controls.Primitives.ButtonBase.Click> il pulsante, viene generato l'evento. Tuttavia, avrete notato che quando si sposta il mouse sul pulsante, gli oggetti visivi del pulsante non cambiano. Queste interazioni visive sono tutte definite dal modello.

Con i sistemi di proprietà e eventi dinamici forniti da WPFWPF, è possibile controllare una proprietà specifica per un valore e quindi ridefinire lo stile del modello quando appropriato. In questo esempio, si guarderà <xref:System.Windows.UIElement.IsMouseOver> la proprietà del pulsante. Quando il mouse si trova ** \<** sopra il controllo, applicare uno stile al>Ellipse con un nuovo colore. Questo tipo di trigger è noto come *PropertyTrigger*.

Affinché questo funzioni, è necessario aggiungere un nome al ** \<>Ellipse** a cui è possibile fare riferimento. Assegnare il nome di **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Successivamente, aggiungere <xref:System.Windows.Trigger> un nuovo per il [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) insieme. Il trigger guarderà l'evento `IsMouseOver` per il valore `true`.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Successivamente, aggiungere un ** \<>Setter** al ** \<>Trigger** che modifica il **Fill** proprietà del ** \<>Ellipse** in un nuovo colore.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Eseguire il progetto. Si noti che quando si sposta il mouse sul pulsante, il colore ** \<dell'>Ellipse** cambia.

![il mouse si sposta sul pulsante WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Usare un VisualStateUse a VisualState

Gli stati di visualizzazione vengono definiti e attivati da un controllo. Ad esempio, quando il mouse viene spostato `CommonStates.MouseOver` sopra il controllo, lo stato viene attivato. È possibile animare le modifiche delle proprietà in base allo stato corrente del controllo. Nella sezione precedente, `IsMouseOver` un `true` ** \<>PropertyTrigger** è stato utilizzato `AliceBlue` per modificare il primo piano del pulsante quando la proprietà era . Creare invece uno stato di visualizzazione che anima la modifica di questo colore, fornendo una transizione uniforme. Per ulteriori informazioni su *VisualStates*, vedere [Stili e modelli in WPF.](../fundamentals/styles-templates-overview.md#visual-states)

Per convertire il ** \<PropertyTrigger>** in uno stato di visualizzazione animato, First, rimuovere il ** \<ControlTemplate.Triggers>elemento** dal modello.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Successivamente, nella ** \<griglia>** radice del modello di controllo, aggiungere il `CommonStates` ** \<VisualStateManager.VisualStateGroups>** elemento con un ** \<VisualStateGroup>** per . Definire due `Normal` stati `MouseOver`e .

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Tutte le animazioni definite in un ** \<VisualState>** vengono applicate quando tale stato viene attivato. Creare animazioni per ogni stato. Le animazioni vengono ** \<** inserite all'interno di un Storyboard>elemento. Per altre informazioni sugli storyboard, vedere [Cenni preliminari](../../framework/wpf/graphics-multimedia/storyboards-overview.md)sugli storyboard.

- Normale

  Questo stato anima il riempimento dell'ellisse, ripristinandolo nel colore del `Background` controllo.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Questo stato aggiunge `Background` un'animazione al `Yellow`colore dell'ellisse su un nuovo colore: .

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

Il ** \<ControlTemplate>** dovrebbe essere simile al seguente.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Eseguire il progetto. Si noti che quando si sposta il mouse sul pulsante, il colore del ** \<Ellipse>** aggiunge un'animazione.

![il mouse si sposta sul pulsante WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Passaggi successivi

- [Creare uno stile per un controllo in WPFCreate a style for a control in WPFWPF](../fundamentals/styles-templates-create-apply-style.md)
- [Stili e modelli in WPF](../fundamentals/styles-templates-overview.md)
- [Panoramica delle risorse XAMLOverview of XAML Resources](../fundamentals/xaml-resources-define.md)
