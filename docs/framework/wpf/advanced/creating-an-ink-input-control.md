---
title: Creazione di un controllo di input penna
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095216"
---
# <a name="creating-an-ink-input-control"></a>Creazione di un controllo di input penna
È possibile creare un controllo personalizzato che esegue il rendering dell'input penna in modo dinamico e statico. Ovvero il rendering dell'input penna quando un utente disegna un tratto, causando la visualizzazione dell'input penna in "Flow" dalla penna del tablet e la visualizzazione dell'input penna dopo l'aggiunta al controllo, tramite la penna del tablet, incollato dagli Appunti o caricato da un file. Per eseguire dinamicamente il rendering dell'input penna, il controllo deve usare un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Per eseguire il rendering statico dell'input penna, è necessario eseguire l'override dei metodi di evento stilo (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>e <xref:System.Windows.UIElement.OnStylusUp%2A>) per raccogliere dati di <xref:System.Windows.Input.StylusPoint>, creare tratti e aggiungerli a un <xref:System.Windows.Controls.InkPresenter> (che esegue il rendering dell'input penna sul controllo).  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Procedura: raccogliere dati dei punti dello stilo e creare tratti di input penna](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Procedura: abilitare il controllo per accettare l'input dal mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Riunendoli](#PuttingItTogether)  
  
- [Uso di plug-in aggiuntivi e DynamicRenderers](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Conclusioni](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Procedura: raccogliere dati dei punti dello stilo e creare tratti di input penna  
 Per creare un controllo che raccoglie e gestisce i tratti di input penna, effettuare le operazioni seguenti:  
  
1. Derivare una classe da <xref:System.Windows.Controls.Control> o da una delle classi derivate da <xref:System.Windows.Controls.Control>, ad esempio <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Aggiungere un <xref:System.Windows.Controls.InkPresenter> alla classe e impostare la proprietà <xref:System.Windows.Controls.ContentControl.Content%2A> sul nuovo <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Allineare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> della <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> al <xref:System.Windows.Controls.InkPresenter> chiamando il metodo <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> e aggiungere il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> alla raccolta di <xref:System.Windows.UIElement.StylusPlugIns%2A>. Ciò consente all'<xref:System.Windows.Controls.InkPresenter> di visualizzare l'input penna quando i dati del punto dello stilo vengono raccolti dal controllo.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusDown%2A> .  In questo metodo acquisire lo stilo con una chiamata a <xref:System.Windows.Input.Stylus.Capture%2A>. Acquisendo lo stilo, il controllo continuerà a ricevere <xref:System.Windows.UIElement.StylusMove> e <xref:System.Windows.UIElement.StylusUp> eventi anche se lo stilo lascia i limiti del controllo. Questa operazione non è strettamente obbligatoria, ma è quasi sempre necessaria per un'esperienza utente ottimale. Creare una nuova <xref:System.Windows.Input.StylusPointCollection> per raccogliere i dati <xref:System.Windows.Input.StylusPoint>. Infine, aggiungere il set iniziale di dati di <xref:System.Windows.Input.StylusPoint> al <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusMove%2A> e aggiungere i dati <xref:System.Windows.Input.StylusPoint> all'oggetto <xref:System.Windows.Input.StylusPointCollection> creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusUp%2A> e creare una nuova <xref:System.Windows.Ink.Stroke> con i dati di <xref:System.Windows.Input.StylusPointCollection>. Aggiungere il nuovo <xref:System.Windows.Ink.Stroke> creato alla raccolta <xref:System.Windows.Controls.InkPresenter.Strokes%2A> della <xref:System.Windows.Controls.InkPresenter> e acquisire lo stilo di rilascio.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Procedura: abilitare il controllo per accettare l'input dal mouse  
 Se si aggiunge il controllo precedente all'applicazione, lo si esegue e si usa il mouse come dispositivo di input, si noterà che i tratti non sono salvati in modo permanente. Per salvare in modo permanente i tratti quando il mouse viene usato come dispositivo di input, eseguire le operazioni seguenti:  
  
1. Eseguire l'override del <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> e creare una nuova <xref:System.Windows.Input.StylusPointCollection> ottenere la posizione del mouse quando si è verificato l'evento e creare un <xref:System.Windows.Input.StylusPoint> usando i dati del punto e aggiungere il <xref:System.Windows.Input.StylusPoint> alla <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseMove%2A> . Ottiene la posizione del mouse quando si è verificato l'evento e crea un <xref:System.Windows.Input.StylusPoint> usando i dati del punto.  Aggiungere la <xref:System.Windows.Input.StylusPoint> all'oggetto <xref:System.Windows.Input.StylusPointCollection> creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Creare una nuova <xref:System.Windows.Ink.Stroke> con i dati <xref:System.Windows.Input.StylusPointCollection> e aggiungere il nuovo <xref:System.Windows.Ink.Stroke> creato alla raccolta <xref:System.Windows.Controls.InkPresenter.Strokes%2A> del <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Riunendoli  
 L'esempio seguente è un controllo personalizzato che raccoglie l'input penna quando l'utente usa il mouse o la penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Uso di plug-in aggiuntivi e DynamicRenderers  
 Analogamente a InkCanvas, il controllo personalizzato può disporre di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzati e oggetti <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> aggiuntivi. Aggiungerli alla raccolta di <xref:System.Windows.UIElement.StylusPlugIns%2A>. L'ordine degli oggetti <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> influiscono sull'aspetto dell'input penna quando ne viene eseguito il rendering. Si supponga di avere un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> denominato `dynamicRenderer` e un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzato denominato `translatePlugin` che compensa l'input penna dalla penna del tablet. Se `translatePlugin` è il primo <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>e `dynamicRenderer` è il secondo, l'input penna "Flows" verrà sfalsato quando l'utente sposta la penna. Se `dynamicRenderer` è il primo e `translatePlugin` è il secondo, l'input penna non verrà sfalsato fino a quando l'utente non solleva la penna.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Conclusioni  
 È possibile creare un controllo che raccoglie ed esegue il rendering dell'input penna eseguendo l'override dei metodi di evento dello stilo. Creando un controllo personalizzato, derivando le proprie classi di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e inserendole in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, è possibile implementare praticamente qualsiasi comportamento immaginabile con l'input penna digitale. È possibile accedere ai dati <xref:System.Windows.Input.StylusPoint> durante la generazione, offrendo la possibilità di personalizzare <xref:System.Windows.Input.Stylus> input e di eseguirne il rendering sullo schermo in base alle esigenze dell'applicazione. Poiché si dispone di un accesso di basso livello ai dati <xref:System.Windows.Input.StylusPoint>, è possibile implementare la raccolta di input penna ed eseguirne il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e modifica dell'input penna](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
