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
ms.openlocfilehash: 105a44f90c1c654a21fc8920a149ad63b2dabc99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323850"
---
# <a name="creating-an-ink-input-control"></a>Creazione di un controllo di input penna
È possibile creare un controllo personalizzato che in modo dinamico e in modo statico viene eseguito il rendering dell'input penna. Vale a dire, eseguire il rendering dell'input penna come un utente consente di disegnare un tratto, causando l'input penna venga visualizzato "fluire" dalla penna del tablet PC e visualizzarlo dopo che viene aggiunto al controllo, tramite la penna del tablet PC, incollato dagli Appunti o caricato da un file. Per eseguire il rendering dinamico, è necessario usare il controllo un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Per eseguire il rendering statico, è necessario eseguire l'override dei metodi di evento dello stilo (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, e <xref:System.Windows.UIElement.OnStylusUp%2A>) per raccogliere <xref:System.Windows.Input.StylusPoint> dati, creare i tratti e aggiungerle a un <xref:System.Windows.Controls.InkPresenter> (che esegue il rendering dell'input penna in del controllo).  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   [Procedura: Raccogliere dati di punti dello stilo e creare tratti input penna](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [Procedura: Abilitare il controllo accettare l'Input da Mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [Uso combinato](#PuttingItTogether)  
  
-   [Utilizzo di Plug-in aggiuntivi e oggetti DynamicRenderer](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [Conclusione](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Procedura: Raccogliere dati di punti dello stilo e creare tratti input penna  
 Per creare un controllo che consente di raccogliere e gestisce l'input penna tratti di eseguire le operazioni seguenti:  
  
1. Derivare una classe dalla classe <xref:System.Windows.Controls.Control> o una delle classi derivate da <xref:System.Windows.Controls.Control>, ad esempio <xref:System.Windows.Controls.Label>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Aggiungere un <xref:System.Windows.Controls.InkPresenter> alla classe e un set di <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà al nuovo <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Collegare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.Controls.InkPresenter> chiamando il <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> metodo e aggiungere il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. In questo modo il <xref:System.Windows.Controls.InkPresenter> per visualizzare l'input penna, come i dati del punto dello stilo raccolti dal controllo.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusDown%2A> .  In questo metodo acquisisce lo stilo con una chiamata a <xref:System.Windows.Input.Stylus.Capture%2A>. Per acquisire lo stilo, si verifica il controllo per continuare a ricevere <xref:System.Windows.UIElement.StylusMove> e <xref:System.Windows.UIElement.StylusUp> eventi anche se lo stilo esce i limiti del controllo. Ciò non è obbligatoria, ma quasi sempre desiderato per un'esperienza utente soddisfacente. Creare una nuova <xref:System.Windows.Input.StylusPointCollection> raccogliere <xref:System.Windows.Input.StylusPoint> dei dati. Infine, aggiungere il set iniziale di <xref:System.Windows.Input.StylusPoint> dei dati per il <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Eseguire l'override di <xref:System.Windows.UIElement.OnStylusMove%2A> (metodo) e aggiungere il <xref:System.Windows.Input.StylusPoint> dei dati per il <xref:System.Windows.Input.StylusPointCollection> oggetto creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Eseguire l'override di <xref:System.Windows.UIElement.OnStylusUp%2A> (metodo) e creare un nuovo <xref:System.Windows.Ink.Stroke> con il <xref:System.Windows.Input.StylusPointCollection> dati. Aggiungere il nuovo <xref:System.Windows.Ink.Stroke> creato per il <xref:System.Windows.Controls.InkPresenter.Strokes%2A> insieme del <xref:System.Windows.Controls.InkPresenter> e rilascia l'acquisizione dello stilo.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Procedura: Abilitare il controllo accettare l'Input da Mouse  
 Se si aggiungere il controllo precedente all'applicazione, eseguirla e utilizza il mouse come un dispositivo di input, si noterà che i tratti non sono persistenti. Per rendere persistenti i tratti quando il puntatore del mouse viene usato come dispositivo di input le operazioni seguenti:  
  
1. Eseguire l'override di <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> e creare un nuovo <xref:System.Windows.Input.StylusPointCollection> ottenere la posizione del mouse quando si è verificato l'evento e creare un <xref:System.Windows.Input.StylusPoint> usando i dati del punto e aggiungere il <xref:System.Windows.Input.StylusPoint> per il <xref:System.Windows.Input.StylusPointCollection>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseMove%2A> . Ottenere la posizione del mouse quando si è verificato l'evento e creare un <xref:System.Windows.Input.StylusPoint> usando i dati del punto.  Aggiungere il <xref:System.Windows.Input.StylusPoint> per il <xref:System.Windows.Input.StylusPointCollection> oggetto creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Creare un nuovo <xref:System.Windows.Ink.Stroke> con il <xref:System.Windows.Input.StylusPointCollection> dei dati e aggiungere i nuovi <xref:System.Windows.Ink.Stroke> creato per il <xref:System.Windows.Controls.InkPresenter.Strokes%2A> raccolta del <xref:System.Windows.Controls.InkPresenter>.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>Uso combinato  
 Nell'esempio seguente è un controllo personalizzato che consente di raccogliere input penna quando l'utente usa il mouse o la penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Utilizzo di Plug-in aggiuntivi e oggetti DynamicRenderer  
 Come oggetto InkCanvas, il controllo personalizzato può avere custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aggiuntive e <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> oggetti. Aggiungere questi elementi di <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. L'ordine dei <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> influisce sull'aspetto dell'input penna quando ne viene eseguito il rendering. Si supponga di avere una <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> chiamati `dynamicRenderer` e un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> chiamato `translatePlugin` che viene eseguito l'offset di input penna del tablet PC. Se `translatePlugin` è il primo <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, e `dynamicRenderer` è il secondo, l'input penna "flusso" compenserà quando l'utente sposta la penna. Se `dynamicRenderer` è il primo e `translatePlugin` è in secondo luogo, l'input penna non compensata fino a quando l'utente solleva la penna.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 È possibile creare un controllo che consente di raccogliere ed esegue il rendering dell'input penna eseguendo l'override dei metodi di evento dello stilo. Tramite la creazione di un controllo personalizzato, derivare il proprio <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserire le informazioni di in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, è possibile implementare qualsiasi comportamento immaginabile con input penna. È possibile utilizzare il <xref:System.Windows.Input.StylusPoint> dati man mano che viene generati, offrendo la possibilità di personalizzare <xref:System.Windows.Input.Stylus> input ed eseguirne il rendering sullo schermo come appropriato per l'applicazione. Perché si dispone di accesso di basso livello per il <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare una raccolta dell'input penna ed eseguirne il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [L'accesso e modifica dell'Input penna](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
