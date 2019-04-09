---
title: Personalizzare il rendering dell'input penna
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: fead6e28949726bef46fe2be46e976fb47c3e9a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125658"
---
# <a name="custom-rendering-ink"></a>Personalizzare il rendering dell'input penna
Il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà di un tratto consente di specificare l'aspetto di un tratto, ad esempio dimensioni, colore e forma, ma potrebbe capitare che si desidera personalizzare l'aspetto oltre ciò che <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> consentire. È possibile personalizzare l'aspetto dell'input penna eseguendo il rendering con l'aspetto di un aerografo, di una pittura a olio e di molti altri effetti. Windows Presentation Foundation (WPF) consente di personalizzare il rendering dell'input penna implementando una classe personalizzata <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e <xref:System.Windows.Ink.Stroke> oggetto.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   [Architettura](#Architecture)  
  
-   [Implementazione di un renderer dinamico](#ImplementingADynamicRenderer)  
  
-   [Implementazione di tratti personalizzati](#ImplementingCustomStrokes)  
  
-   [Implementazione di un oggetto InkCanvas personalizzato](#ImplementingACustomInkCanvas)  
  
-   [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architettura  
 Il rendering dell'input penna viene eseguito due volte: quando l'utente scrive tramite una penna su un'apposita superficie e dopo l'aggiunta del tratto alla superficie abilitata per l'input penna. Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering dell'input penna quando l'utente sposta la penna del tablet sul digitalizzatore e il <xref:System.Windows.Ink.Stroke> esegue il rendering di se stesso dopo essere stato aggiunto a un elemento.  
  
 Per il rendering dinamico dell'input penna è necessario implementare tre classi.  
  
1.  **DynamicRenderer**: Implementare una classe che derivi da <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Questa classe è un'oggetto specifico <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> che esegue il rendering del tratto mentre viene tracciato. Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering su un thread separato, in modo che la superficie di input penna sembra raccogliere l'input penna anche quando viene bloccato il thread dell'interfaccia utente dell'applicazione. Per altre informazioni sul modello di threading, vedere [Modello di threading dell'input penna](the-ink-threading-model.md). Per personalizzare il rendering dinamico di un tratto, eseguire l'override di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> (metodo).  
  
2.  **Stroke**: Implementare una classe che derivi da <xref:System.Windows.Ink.Stroke>. Questa classe è responsabile del rendering statico del <xref:System.Windows.Input.StylusPoint> dati dopo che è stato convertito in un <xref:System.Windows.Ink.Stroke> oggetto. Eseguire l'override di <xref:System.Windows.Ink.Stroke.DrawCore%2A> metodo per assicurarsi che il rendering statico del tratto sia coerenza con il rendering dinamico.  
  
3.  **InkCanvas:** Implementare una classe che derivi da <xref:System.Windows.Controls.InkCanvas>. Assegnare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà. Eseguire l'override di <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> metodo e aggiungere un tratto personalizzato per il <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà. In questo modo, è possibile assicurarsi che l'aspetto dell'input penna sia coerente.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementazione di un renderer dinamico  
 Anche se il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> classe è una parte standard del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], per eseguire più specializzato per il rendering, è necessario creare un renderer dinamico personalizzato che deriva dalle <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ed eseguire l'override di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> (metodo).  
  
 L'esempio seguente illustra un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> che disegna l'input penna con un effetto pennello a sfumatura lineare.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementazione di tratti personalizzati  
 Implementare una classe che derivi da <xref:System.Windows.Ink.Stroke>. Questa classe è responsabile del rendering <xref:System.Windows.Input.StylusPoint> dati dopo che è stato convertito in un <xref:System.Windows.Ink.Stroke> oggetto. Eseguire l'override di <xref:System.Windows.Ink.Stroke.DrawCore%2A> classe per eseguire il disegno effettivo.  
  
 Nella classe Stroke può anche archiviare dati personalizzati usando il <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> (metodo). Questi dati vengono archiviati con i dati del tratto quando sono resi persistenti.  
  
 Il <xref:System.Windows.Ink.Stroke> classe può anche eseguire l'hit testing. È anche possibile implementare il proprio algoritmo di hit testing eseguendo l'override di <xref:System.Windows.Ink.Stroke.HitTest%2A> metodo nella classe corrente.  
  
 Il seguente C# codice illustra una classe personalizzata <xref:System.Windows.Ink.Stroke> classe che esegue il rendering <xref:System.Windows.Input.StylusPoint> dati come tratto 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementazione di un oggetto InkCanvas personalizzato  
 Il modo più semplice per usare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> tratto e implementare una classe che deriva da <xref:System.Windows.Controls.InkCanvas> e Usa queste classi. Il <xref:System.Windows.Controls.InkCanvas> ha un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà che specifica la modalità di rendering del tratto mentre l'utente lo disegna.  
  
 Su custom rendering tratti su un <xref:System.Windows.Controls.InkCanvas> eseguire le operazioni seguenti:  
  
-   Creare una classe che deriva dal <xref:System.Windows.Controls.InkCanvas>.  
  
-   Assegnare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> proprietà.  
  
-   Eseguire l'override del metodo <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> . In questo metodo, rimuovere il tratto originale aggiunto all'oggetto InkCanvas. Creare quindi un tratto personalizzato, aggiungerlo al <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà e chiamare la classe di base con un nuovo <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> che contiene il tratto personalizzato.  
  
 Il seguente C# codice illustra una classe personalizzata <xref:System.Windows.Controls.InkCanvas> classe che utilizza un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e raccoglie tratti personalizzati.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un' <xref:System.Windows.Controls.InkCanvas> può avere più di uno <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. È possibile aggiungere più <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> gli oggetti per il <xref:System.Windows.Controls.InkCanvas> aggiungendole al <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 È possibile personalizzare l'aspetto dell'input penna derivando <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, e <xref:System.Windows.Controls.InkCanvas> classi. Insieme, queste classi assicurano che il tratto abbia un aspetto coerente quando l'utente lo disegna e dopo che viene raccolto.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
