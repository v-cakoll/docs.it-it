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
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186290"
---
# <a name="creating-an-ink-input-control"></a>Creazione di un controllo di input penna
È possibile creare un controllo personalizzato che esegue il rendering dell'input penna in modo dinamico e statico. Ovvero, eseguire il rendering dell'input penna come un utente disegna un tratto, facendo in modo che l'input penna sembri "fluire" dalla penna del Tablet PC e visualizzare l'input penna dopo che è stato aggiunto al controllo, tramite la penna del Tablet PC, incollato dagli Appunti o caricato da un file. Per eseguire il rendering dinamico <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>dell'input penna, il controllo deve utilizzare un oggetto . Per eseguire il rendering statico dell'input<xref:System.Windows.UIElement.OnStylusDown%2A>penna, è necessario eseguire l'override dei metodi dell'evento dello stilo ( , <xref:System.Windows.UIElement.OnStylusMove%2A>, e <xref:System.Windows.UIElement.OnStylusUp%2A>) per raccogliere <xref:System.Windows.Input.StylusPoint> dati, creare tratti e aggiungerli a un <xref:System.Windows.Controls.InkPresenter> oggetto (che esegue il rendering dell'input penna nel controllo).  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Procedura: raccogliere dati del punto dello stilo e creare tratti input pennaHow to: Collect Stylus Point Data and Create Ink Strokes](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [Procedura: abilitare il controllo per accettare l'input dal mouseHow to: Enable Your Control to Accept Input from the Mouse](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [Riepilogo](#PuttingItTogether)  
  
- [Utilizzo di plug-in e DynamicRenderer aggiuntivi](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [Conclusione](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>Procedura: raccogliere dati del punto dello stilo e creare tratti input pennaHow to: Collect Stylus Point Data and Create Ink Strokes  
 Per creare un controllo che raccoglie e gestisce i tratti input penna, procedere come segue:  
  
1. Derivare una <xref:System.Windows.Controls.Control> classe da o <xref:System.Windows.Controls.Control>una delle <xref:System.Windows.Controls.Label>classi derivate da , ad esempio .  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. Aggiungere <xref:System.Windows.Controls.InkPresenter> un alla classe <xref:System.Windows.Controls.ContentControl.Content%2A> e impostare <xref:System.Windows.Controls.InkPresenter>la proprietà sul nuovo oggetto .  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. Associare <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> l'oggetto <xref:System.Windows.Controls.InkPresenter> a <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> chiamando il metodo <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e <xref:System.Windows.UIElement.StylusPlugIns%2A> aggiungere l'oggetto alla raccolta. In questo <xref:System.Windows.Controls.InkPresenter> modo è possibile visualizzare l'input penna quando i dati del punto dello stilo vengono raccolti dal controllo.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnStylusDown%2A> .  In questo metodo, acquisire lo <xref:System.Windows.Input.Stylus.Capture%2A>stilo con una chiamata a . Acquisendo lo stilo, <xref:System.Windows.UIElement.StylusMove> <xref:System.Windows.UIElement.StylusUp> il controllo continuerà a ricevere e gli eventi anche se lo stilo esce dai limiti del controllo. Questo non è strettamente obbligatorio, ma quasi sempre desiderato per una buona esperienza utente. Creare un <xref:System.Windows.Input.StylusPointCollection> nuovo <xref:System.Windows.Input.StylusPoint> per raccogliere i dati. Infine, aggiungere il <xref:System.Windows.Input.StylusPoint> set iniziale di dati al <xref:System.Windows.Input.StylusPointCollection>file .  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. Eseguire <xref:System.Windows.UIElement.OnStylusMove%2A> l'override <xref:System.Windows.Input.StylusPoint> del metodo <xref:System.Windows.Input.StylusPointCollection> e aggiungere i dati all'oggetto creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. Eseguire <xref:System.Windows.UIElement.OnStylusUp%2A> l'override del <xref:System.Windows.Ink.Stroke> metodo <xref:System.Windows.Input.StylusPointCollection> e crearne uno nuovo con i dati. Aggiungere il <xref:System.Windows.Ink.Stroke> nuovo creato <xref:System.Windows.Controls.InkPresenter.Strokes%2A> alla <xref:System.Windows.Controls.InkPresenter> raccolta dell'acquisizione dello stilo e release.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>Procedura: abilitare il controllo per accettare l'input dal mouseHow to: Enable Your Control to Accept Input from the Mouse  
 Se si aggiunge il controllo precedente all'applicazione, lo si esegue e si utilizza il mouse come dispositivo di input, si noterà che i tratti non sono persistenti. Per mantenere persistenti i tratti quando il mouse viene utilizzato come dispositivo di input, effettuare le seguenti operazioni:  
  
1. Eseguire <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> l'override <xref:System.Windows.Input.StylusPointCollection> di e creare un nuovo Get la <xref:System.Windows.Input.StylusPoint> posizione del mouse <xref:System.Windows.Input.StylusPoint> quando <xref:System.Windows.Input.StylusPointCollection>si è verificato l'evento e creare un utilizzando i dati punto e aggiungere il al .  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseMove%2A> . Ottenere la posizione del mouse quando si <xref:System.Windows.Input.StylusPoint> è verificato l'evento e creare un utilizzando i dati punto.  Aggiungere <xref:System.Windows.Input.StylusPoint> l'oggetto all'oggetto <xref:System.Windows.Input.StylusPointCollection> creato in precedenza.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. Eseguire l'override del metodo <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  Creare un <xref:System.Windows.Ink.Stroke> nuovo <xref:System.Windows.Input.StylusPointCollection> con i dati <xref:System.Windows.Ink.Stroke> e aggiungere <xref:System.Windows.Controls.InkPresenter.Strokes%2A> il <xref:System.Windows.Controls.InkPresenter>nuovo creato all'insieme del file .  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>Riepilogo  
 L'esempio seguente è un controllo personalizzato che raccoglie l'input penna quando l'utente utilizza il mouse o la penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>Utilizzo di plug-in e DynamicRenderer aggiuntivi  
 Come il InkCanvas, il controllo <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> può avere oggetti personalizzati e aggiuntivi. Aggiungerli alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. L'ordine <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> degli oggetti <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> nell'oggetto influisce sull'aspetto dell'input penna quando ne viene eseguito il rendering. Si supponga <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> di `dynamicRenderer` disporre <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> di `translatePlugin` un chiamato e un personalizzato chiamato che scosta l'input penna dalla penna del Tablet PC. Se `translatePlugin` è <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> il <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>primo `dynamicRenderer` nella stringa e viene il secondo, l'input penna che "scorre" verrà spostato quando l'utente sposta la penna. Se `dynamicRenderer` è il `translatePlugin` primo, ed è secondo, l'inchiostro non verrà sfalsato fino a quando l'utente non solleva la penna.  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>Conclusioni  
 È possibile creare un controllo che raccoglie ed esegue il rendering dell'input penna eseguendo l'override dei metodi dell'evento dello stilo. Creando il proprio controllo, derivando le proprie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>e inserendole in , è possibile implementare praticamente qualsiasi comportamento immaginabile con l'input penna digitale. Si ha accesso <xref:System.Windows.Input.StylusPoint> ai dati così come vengono <xref:System.Windows.Input.Stylus> generati, offrendo la possibilità di personalizzare l'input ed eseguirne il rendering sullo schermo in base alle esigenze dell'applicazione. Poiché si dispone di tale <xref:System.Windows.Input.StylusPoint> accesso di basso livello ai dati, è possibile implementare la raccolta dell'input penna ed eseguirne il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e manipolazione dell'input penna](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
