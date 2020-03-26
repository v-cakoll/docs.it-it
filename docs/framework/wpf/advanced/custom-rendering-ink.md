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
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111829"
---
# <a name="custom-rendering-ink"></a>Personalizzare il rendering dell'input penna
La <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà di un tratto consente di specificare l'aspetto di un tratto, ad esempio le dimensioni, il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> colore e la forma, ma in alcuni casi può essere necessario personalizzare l'aspetto oltre a quanto consentito. È possibile personalizzare l'aspetto dell'input penna eseguendo il rendering con l'aspetto di un aerografo, di una pittura a olio e di molti altri effetti. Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) consente di personalizzare l'input penna di rendering implementando un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e. <xref:System.Windows.Ink.Stroke>  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Architettura](#Architecture)  
  
- [Implementazione di un renderer dinamico](#ImplementingADynamicRenderer)  
  
- [Implementazione di tratti personalizzati](#ImplementingCustomStrokes)  
  
- [Implementazione di un oggetto InkCanvas personalizzato](#ImplementingACustomInkCanvas)  
  
- [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 Il rendering dell'input penna viene eseguito due volte: quando l'utente scrive tramite una penna su un'apposita superficie e dopo l'aggiunta del tratto alla superficie abilitata per l'input penna. Esegue <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> il rendering dell'input penna quando l'utente sposta <xref:System.Windows.Ink.Stroke> la penna del Tablet PC sul digitalizzatore e viene eseguito il rendering stesso una volta aggiunto a un elemento.  
  
 Per il rendering dinamico dell'input penna è necessario implementare tre classi.  
  
1. **DynamicRenderer**: implementare una <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>classe che deriva da . Questa classe è <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> specializzata che esegue il rendering del tratto mentre viene disegnato. Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering in un thread separato, in modo che la superficie di input penna sembra raccogliere l'input penna anche quando il thread dell'interfaccia utente dell'applicazione è bloccato. Per altre informazioni sul modello di threading, vedere [Modello di threading dell'input penna](the-ink-threading-model.md). Per personalizzare il rendering dinamico di un tratto, eseguire l'override del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> metodo .  
  
2. **Stroke**: implementa una classe <xref:System.Windows.Ink.Stroke>che deriva da . Questa classe è responsabile <xref:System.Windows.Input.StylusPoint> del rendering statico dei <xref:System.Windows.Ink.Stroke> dati dopo che sono stati convertiti in un oggetto. Eseguire <xref:System.Windows.Ink.Stroke.DrawCore%2A> l'override del metodo per garantire che il rendering statico del tratto sia coerente con il rendering dinamico.  
  
3. **InkCanvas:** Implementare una classe <xref:System.Windows.Controls.InkCanvas>che deriva da . Assegnare <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> l'personalizzato <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> alla proprietà. Eseguire <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> l'override del metodo <xref:System.Windows.Controls.InkCanvas.Strokes%2A> e aggiungere un tratto personalizzato alla proprietà. In questo modo, è possibile assicurarsi che l'aspetto dell'input penna sia coerente.  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>Implementazione di un renderer dinamico  
 Sebbene <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la classe sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]una parte standard di , per eseguire un rendering più <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> specializzato, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> è necessario creare un renderer dinamico personalizzato che derivi dal metodo e ne esegua l'override.  
  
 Nell'esempio seguente viene <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> illustrato un oggetto personalizzato che disegna input penna con un effetto pennello sfumato lineare.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>Implementazione di tratti personalizzati  
 Implementare una classe che derivi da <xref:System.Windows.Ink.Stroke>. Questa classe è <xref:System.Windows.Input.StylusPoint> responsabile del rendering dei <xref:System.Windows.Ink.Stroke> dati dopo che sono stati convertiti in un oggetto. Eseguire <xref:System.Windows.Ink.Stroke.DrawCore%2A> l'override della classe per eseguire il disegno effettivo.  
  
 La classe Stroke può anche archiviare dati personalizzati utilizzando il <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> metodo . Questi dati vengono archiviati con i dati del tratto quando sono resi persistenti.  
  
 La <xref:System.Windows.Ink.Stroke> classe può anche eseguire l'hit testing. È anche possibile implementare il proprio <xref:System.Windows.Ink.Stroke.HitTest%2A> algoritmo di hit testing eseguendo l'override del metodo nella classe corrente.  
  
 Il seguente codice in <xref:System.Windows.Ink.Stroke> C, <xref:System.Windows.Input.StylusPoint> viene illustrato una classe personalizzata che esegue il rendering dei dati come tratto 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>Implementazione di un oggetto InkCanvas personalizzato  
 Il modo più semplice per <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> usare la proprietà personalizzata e <xref:System.Windows.Controls.InkCanvas> stroke consiste nell'implementare una classe che deriva da e utilizza queste classi. La <xref:System.Windows.Controls.InkCanvas> dispone <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> di una proprietà che specifica come viene eseguito il rendering del tratto quando l'utente lo sta disegnando.  
  
 Per personalizzare i tratti <xref:System.Windows.Controls.InkCanvas> di rendering su un'operazione, effettuate le seguenti operazioni:  
  
- Creare una classe che <xref:System.Windows.Controls.InkCanvas>deriva da .  
  
- Assegnare la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> personalizzazione alla <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> proprietà.  
  
- Eseguire l'override del metodo <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> . In questo metodo, rimuovere il tratto originale aggiunto all'oggetto InkCanvas. Creare quindi un tratto personalizzato, <xref:System.Windows.Controls.InkCanvas.Strokes%2A> aggiungerlo alla proprietà e <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> chiamare la classe base con un nuovo che contiene il tratto personalizzato.  
  
 Il codice c'è <xref:System.Windows.Controls.InkCanvas> riportato di seguito <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> viene illustrato una classe personalizzata che utilizza un personalizzato e raccoglie tratti personalizzati.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un <xref:System.Windows.Controls.InkCanvas> oggetto può <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>avere più di uno file . È possibile <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> aggiungere più <xref:System.Windows.Controls.InkCanvas> oggetti a <xref:System.Windows.UIElement.StylusPlugIns%2A> aggiungendoli alla proprietà .  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Conclusioni  
 È possibile personalizzare l'aspetto dell'input <xref:System.Windows.Ink.Stroke>penna <xref:System.Windows.Controls.InkCanvas> derivando classi <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, e , e . Insieme, queste classi assicurano che il tratto abbia un aspetto coerente quando l'utente lo disegna e dopo che viene raccolto.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
