---
title: Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: fda7ed12d232af5a7cfb8eb43cbb09eb793da171
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141199"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre due meccanismi paralleli per modificare l'aspetto visivo di un controllo che riceve lo stato attivo della tastiera. Il primo meccanismo consiste nell'utilizzare <xref:System.Windows.UIElement.IsKeyboardFocused%2A> i setter di proprietà per le proprietà, ad esempio all'interno dello stile o del modello applicato al controllo. Il secondo meccanismo consiste nel fornire uno <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> stile separato come valore della proprietà; lo "stile di visualizzazione dello stato attivo" crea una struttura ad albero visuale separata per uno strumento decorativo visuale che disegna sopra il controllo, anziché modificare la struttura ad albero visuale del controllo o di un altro elemento dell'interfaccia utente sostituendolo. Questo argomento descrive gli scenari appropriati a ogni meccanismo.  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>Scopo dello stile di visualizzazione dello stato attivo  
 La funzionalità dello stile di visualizzazione dello stato attivo offre un "modello a oggetti" comune per introdurre un feedback utente visivo, basato sul passaggio tramite tastiera a un qualsiasi elemento dell'interfaccia utente. Questo è possibile senza bisogno di applicare un nuovo modello al controllo, né di conoscere la composizione specifica del modello.  
  
 Dal momento però che la funzionalità dello stile di visualizzazione dello stato attivo funziona a prescindere dai modelli di controllo, il feedback visivo che è possibile visualizzare per un controllo usando uno stile di visualizzazione dello stato attivo è necessariamente limitato. La funzionalità sovrappone una struttura ad albero visuale diversa (uno strumento decorativo visuale) sulla struttura ad albero visuale creata dal rendering di un controllo tramite il relativo modello. Definire questa struttura ad albero visuale <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> separata utilizzando uno stile che riempie la proprietà.  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>Comportamento predefinito dello stile di visualizzazione dello stato attivo  
 Gli stili di visualizzazione dello stato attivo funzionano solo quando l'azione di impostazione dello stato attivo è stata iniziata dalla tastiera. Qualsiasi azione del mouse o modifica dello stato attivo a livello di codice disabilita la modalità degli stili di visualizzazione dello stato attivo. Per altre informazioni sulle differenze tra le modalità dello stato attivo, vedere [Cenni preliminari sullo stato attivo](focus-overview.md).  
  
 I temi dei controlli includono un comportamento predefinito dello stile di visualizzazione dello stato attivo che diventa lo stile di visualizzazione dello stato attivo per tutti i controlli del tema. Questo stile di tema è identificato dal <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>valore della chiave statica . Quando si dichiara uno stile di visualizzazione dello stato attivo personalizzato a livello di applicazione, questo sostituisce il comportamento dello stile predefinito dei temi. In alternativa, se si definisce l'intero tema, è necessario usare questa stessa chiave per definire lo stile del comportamento predefinito per tutto il tema.  
  
 Nei temi, lo stile di visualizzazione dello stato attivo predefinito in genere è molto semplice. Di seguito è riportata un'approssimazione generica:  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>
## <a name="when-to-use-focus-visual-styles"></a>Quando usare gli stili di visualizzazione dello stato attivo  
 Dal punto di vista concettuale, l'aspetto degli stili di visualizzazione dello stato attivo applicati ai controlli deve essere coerente da un controllo all'altro. Un modo per garantire la coerenza consiste nel modificare lo stile di visualizzazione dello stato attivo solo se si sta componendo un tema completo, in cui ogni controllo definito nel tema ottiene lo stesso stile di visualizzazione dello stato attivo o una variazione di uno stile visivamente coerente tra i vari controlli. In alternativa, si può usare lo stesso stile (o stili simili) per assegnare uno stile a ogni elemento della pagina o di un'interfaccia utente in grado di ricevere lo stato attivo tramite tastiera.  
  
 L'impostazione <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> su singoli stili di controllo che non fanno parte di un tema non è l'utilizzo previsto degli stili di visualizzazione dello stato attivo. Un comportamento visivo incoerente tra controlli può infatti creare confusione nell'esperienza utente relativamente allo stato attivo. Se si intendono comportamenti specifici del controllo per lo stato attivo della tastiera che non sono deliberatamente coerenti in <xref:System.Windows.UIElement.IsFocused%2A> <xref:System.Windows.UIElement.IsKeyboardFocused%2A>un tema, un approccio molto migliore consiste nell'utilizzare i trigger negli stili per le singole proprietà dello stato di input, ad esempio o .  
  
 Gli stili di visualizzazione dello stato attivo funzionano esclusivamente per lo stato attivo da tastiera. Come tali, costituiscono un tipo di funzionalità di accessibilità. Se si vogliono apportare modifiche all'interfaccia utente per qualsiasi tipo di stato attivo, tramite mouse, tastiera o a livello di codice, è preferibile usare non gli stili di visualizzazione dello stato attivo, bensì setter e trigger all'interno degli stili oppure modelli che funzionino in base al valore delle proprietà generali dello stato attivo, ad esempio <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>Come creare uno stile di visualizzazione dello stato attivo  
 Lo stile creato per uno stile di <xref:System.Windows.Style.TargetType%2A> <xref:System.Windows.Controls.Control>visualizzazione dello stato attivo deve sempre avere il valore di . Lo stile dovrebbe essere <xref:System.Windows.Controls.ControlTemplate>costituito principalmente da un . Non si specifica il tipo di destinazione come tipo in <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>cui lo stile di visualizzazione dello stato attivo viene assegnato all'oggetto .  
  
 Poiché il tipo <xref:System.Windows.Controls.Control>di destinazione è sempre , è necessario applicare uno <xref:System.Windows.Controls.Control> stile utilizzando proprietà comuni a tutti i controlli (utilizzando le proprietà della classe e delle relative classi base). È necessario creare un modello che funzioni correttamente come sovrapposizione a un elemento dell'interfaccia utente e che non nasconda le aree funzionali del controllo. In generale, questo vuol dire che il feedback visivo deve essere visualizzato all'esterno dei margini del controllo o sotto forma di effetti temporanei o non intrusivi, che non blocchino l'hit testing sul controllo a cui viene applicato lo stile di visualizzazione dello stato attivo. Le proprietà che è possibile utilizzare nell'associazione di modelli utili per <xref:System.Windows.FrameworkElement.ActualHeight%2A> <xref:System.Windows.FrameworkElement.ActualWidth%2A>determinare <xref:System.Windows.FrameworkElement.Margin%2A>il <xref:System.Windows.Controls.Control.Padding%2A>ridimensionamento e il posizionamento del modello di sovrapposizione includono , , e .  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternative all'uso di uno stile di visualizzazione dello stato attivo  
 Per le situazioni in cui non è appropriato usare uno stile di visualizzazione dello stato attivo, perché si sta assegnando uno stile solo a singoli controlli o perché si vuole un controllo maggiore sul modello del controllo, sono disponibili molte altre proprietà e tecniche accessibili che creano un comportamento visivo in risposta alle modifiche apportate allo stato attivo.  
  
 Trigger, setter e setter di eventi sono illustrati in dettaglio in [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md). La gestione degli eventi indirizzati è illustrata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Se si è interessati in <xref:System.Windows.UIElement.IsKeyboardFocused%2A> modo specifico allo stato <xref:System.Windows.Trigger>attivo della tastiera, la proprietà di dipendenza può essere utilizzata per una proprietà . Un trigger di proprietà in uno stile o in un modello rappresenta una tecnica più appropriata per la definizione di un comportamento dello stato attivo della tastiera specifico per un singolo controllo, che potrebbe non corrispondere visivamente al comportamento dello stato attivo della tastiera di altri controlli.  
  
 Un'altra proprietà <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>di dipendenza simile è , che potrebbe essere appropriata da usare se si desidera richiamare visivamente lo stato attivo della tastiera, in un punto qualsiasi della composizione o all'interno dell'area funzionale del controllo. Ad esempio, è <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> possibile inserire un trigger in modo che un pannello che raggruppa più controlli venga visualizzato in modo diverso, anche se lo stato attivo della tastiera potrebbe trovarsi in modo più preciso su un singolo elemento all'interno di tale pannello.  
  
 È inoltre possibile <xref:System.Windows.UIElement.GotKeyboardFocus> utilizzare <xref:System.Windows.UIElement.LostKeyboardFocus> gli eventi e (così come i loro equivalenti di anteprima). È possibile utilizzare questi eventi <xref:System.Windows.EventSetter>come base per un oggetto , oppure è possibile scrivere gestori per gli eventi nel code-behind.  
  
### <a name="other-focus-properties"></a>Altre proprietà dello stato attivo  
 Se si desidera che tutte le possibili cause della modifica dello stato attivo <xref:System.Windows.UIElement.IsFocused%2A> producano un comportamento <xref:System.Windows.UIElement.GotFocus> visivo, è necessario basare un setter o un trigger sulla proprietà di dipendenza oppure in alternativa sugli eventi o <xref:System.Windows.UIElement.LostFocus> utilizzati per un <xref:System.Windows.EventSetter>oggetto .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Cenni preliminari sullo stato attivo](focus-overview.md)
- [Cenni preliminari sull'input](input-overview.md)
