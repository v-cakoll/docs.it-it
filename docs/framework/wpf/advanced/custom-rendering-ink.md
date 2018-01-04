---
title: Personalizzare il rendering dell'input penna
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 481990acdf2f5b8f798144d36434569b9e2cd481
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-rendering-ink"></a>Personalizzare il rendering dell'input penna
Il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà di un tratto consente di specificare l'aspetto di un tratto, ad esempio colore, dimensioni e forma, ma è possibile talvolta che si desidera personalizzare l'aspetto oltre a quelle <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> consentire. È possibile personalizzare l'aspetto dell'input penna eseguendo il rendering con l'aspetto di un aerografo, di una pittura a olio e di molti altri effetti. Il [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] consente di personalizzare il rendering dell'input penna implementando un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e <xref:System.Windows.Ink.Stroke> oggetto.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   [Architettura](#Architecture)  
  
-   [Implementazione di un renderer dinamico](#ImplementingADynamicRenderer)  
  
-   [Implementazione di tratti personalizzati](#ImplementingCustomStrokes)  
  
-   [Implementazione di un oggetto InkCanvas personalizzato](#ImplementingACustomInkCanvas)  
  
-   [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architettura  
 Il rendering dell'input penna viene eseguito due volte: quando l'utente scrive tramite una penna su un'apposita superficie e dopo l'aggiunta del tratto alla superficie abilitata per l'input penna. Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> viene eseguito il rendering quando l'utente sposta la penna di Tablet PC sul digitalizzatore, l'input penna e <xref:System.Windows.Ink.Stroke> esegue il rendering di se stessa dopo essere stato aggiunto a un elemento.  
  
 Per il rendering dinamico dell'input penna è necessario implementare tre classi.  
  
1.  **DynamicRenderer**: implementare una classe che deriva da <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. Questa classe è un oggetto specializzato <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> che esegue il rendering del tratto mentre viene disegnato. Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering in un thread separato, pertanto viene visualizzata l'area di input penna per raccogliere input penna anche quando il thread di interfaccia utente dell'applicazione è bloccato. Per altre informazioni sul modello di threading, vedere [Modello di threading dell'input penna](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md). Per personalizzare dinamicamente il rendering di un tratto, eseguire l'override di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> metodo.  
  
2.  **Stroke**: implementare una classe che deriva da <xref:System.Windows.Ink.Stroke>. Questa classe è responsabile per il rendering statico del <xref:System.Windows.Input.StylusPoint> dati dopo che è stata convertita in un <xref:System.Windows.Ink.Stroke> oggetto. Eseguire l'override di <xref:System.Windows.Ink.Stroke.DrawCore%2A> metodo per assicurarsi che il rendering statico del tratto sia coerenza con il rendering dinamico.  
  
3.  **Oggetto InkCanvas:** implementare una classe che deriva da <xref:System.Windows.Controls.InkCanvas>. Assegnare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà. Eseguire l'override di <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> (metodo) e aggiungere un tratto personalizzato per il <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà. In questo modo, è possibile assicurarsi che l'aspetto dell'input penna sia coerente.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>Implementazione di un renderer dinamico  
 Sebbene il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> classe è una parte standard di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], per eseguire più specializzato per il rendering, è necessario creare un renderer dinamico personalizzato che deriva dal <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ed eseguire l'override di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> (metodo).  
  
 Nell'esempio seguente viene illustrato un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> che disegna l'input penna con un effetto sfumatura lineare.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>Implementazione di tratti personalizzati  
 Implementare una classe che derivi da <xref:System.Windows.Ink.Stroke>. Questa classe è responsabile per il rendering <xref:System.Windows.Input.StylusPoint> dati dopo che è stata convertita in un <xref:System.Windows.Ink.Stroke> oggetto. Eseguire l'override di <xref:System.Windows.Ink.Stroke.DrawCore%2A> classe per eseguire il disegno effettivo.  
  
 La classe di traccia possa inoltre archiviare dati personalizzati utilizzando il <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> metodo. Questi dati vengono archiviati con i dati del tratto quando sono resi persistenti.  
  
 La <xref:System.Windows.Ink.Stroke> classe può anche eseguire l'hit test. È anche possibile implementare il proprio algoritmo di hit testing eseguendo l'override di <xref:System.Windows.Ink.Stroke.HitTest%2A> metodo nella classe corrente.  
  
 Il codice c# seguente viene illustrato un personalizzato <xref:System.Windows.Ink.Stroke> classe che esegue il rendering <xref:System.Windows.Input.StylusPoint> dati come tratto 3D.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>Implementazione di un oggetto InkCanvas personalizzato  
 Il modo più semplice per utilizzare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e tratto consiste nell'implementare una classe che deriva da <xref:System.Windows.Controls.InkCanvas> e utilizza queste classi. Il <xref:System.Windows.Controls.InkCanvas> ha un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà che specifica la modalità di rendering del tratto quando l'utente lo disegna.  
  
 Personalizzato rendering tratti in un <xref:System.Windows.Controls.InkCanvas> eseguire le operazioni seguenti:  
  
-   Creare una classe che deriva dal <xref:System.Windows.Controls.InkCanvas>.  
  
-   Assegnare l'oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> per il <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> proprietà.  
  
-   Eseguire l'override del metodo <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>. In questo metodo, rimuovere il tratto originale aggiunto all'oggetto InkCanvas. Creare quindi un tratto personalizzato, aggiungerlo al <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà e chiamare la classe base con un nuovo <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> che contiene il tratto personalizzato.  
  
 Il codice c# seguente viene illustrato un personalizzato <xref:System.Windows.Controls.InkCanvas> classe che utilizza un oggetto personalizzato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> e raccoglie tratti personalizzati.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 Un <xref:System.Windows.Controls.InkCanvas> può avere più <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>. È possibile aggiungere più <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> oggetti per il <xref:System.Windows.Controls.InkCanvas> aggiungendoli al file il <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 È possibile personalizzare l'aspetto dell'input penna derivando <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, e <xref:System.Windows.Controls.InkCanvas> classi. Insieme, queste classi assicurano che il tratto abbia un aspetto coerente quando l'utente lo disegna e dopo che viene raccolto.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione avanzata dell'input penna](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)
