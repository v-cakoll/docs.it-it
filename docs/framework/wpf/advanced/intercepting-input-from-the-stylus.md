---
title: Intercettazione dell'input dello stilo
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
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 611a2d2de56025e2f1b5add6106294834586f9af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo
Il <xref:System.Windows.Input.StylusPlugIns> architettura fornisce un meccanismo per l'implementazione di controllo di basso livello su <xref:System.Windows.Input.Stylus> input e la creazione di input penna <xref:System.Windows.Ink.Stroke> oggetti. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classe fornisce un meccanismo per implementare un comportamento personalizzato e applicarlo al flusso di dati provenienti dal dispositivo stilo per prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   [Architettura](#Architecture)  
  
-   [Implementazione di Plug-in dello stilo](#ImplementingStylusPlugins)  
  
-   [Aggiungere il plug-in per un oggetto InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architettura  
 Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> è l'evoluzione del [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) API, descritte in [accesso e la modifica di Input penna](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)nella [Software di Microsoft Windows XP Tablet PC Edition Kit di sviluppo 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Ogni <xref:System.Windows.UIElement> ha un <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. È possibile aggiungere un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a un elemento <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà per modificare <xref:System.Windows.Input.StylusPoint> dati man mano che viene generati. <xref:System.Windows.Input.StylusPoint>i dati sono costituiti da tutte le proprietà supportate dal digitalizzatore del sistema, inclusi il <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> punto dati, nonché <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> dati.  
  
 Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> gli oggetti vengono inseriti direttamente nel flusso di dati provenienti dal <xref:System.Windows.Input.Stylus> dispositivo quando si aggiunge il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> per il <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà. L'ordine in cui vengono aggiunti i plug-in per il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta definisce l'ordine in cui riceveranno <xref:System.Windows.Input.StylusPoint> dati. Ad esempio, se si aggiunge un plug-in filtro che limita l'input a una determinata area e quindi aggiungere un plug-in che riconosce quando vengono scritti, il plug-in riceverà filtrato <xref:System.Windows.Input.StylusPoint> dati.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementazione di Plug-in dello stilo  
 Per implementare un plug-in, derivare una classe da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Questa classe viene applicata al flusso di dati provenienti dal <xref:System.Windows.Input.Stylus>. In questa classe è possibile modificare i valori del <xref:System.Windows.Input.StylusPoint> dati.  
  
> [!CAUTION]
>  Se un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> genera o genera un'eccezione, l'applicazione verrà chiusa. È consigliabile verificare accuratamente i controlli che utilizzano un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e utilizzare un controllo solo se si è certi di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> non genererà un'eccezione.  
  
 Nell'esempio seguente viene illustrato un plug-in che limita l'input con stilo modificando il <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> i valori di <xref:System.Windows.Input.StylusPoint> provengono dati man mano che il <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiungere il plug-in per un oggetto InkCanvas  
 Il modo più semplice per utilizzare il plug-in personalizzato consiste nell'implementare una classe che deriva da InkCanvas e aggiungerla al <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà.  
  
 Nell'esempio seguente viene illustrato un personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si aggiunge un `FilterInkCanvas` all'applicazione e l'esecuzione, si noterà che l'input penna viene limitato a un'area solo dopo il completamento di un tratto. In questo modo il <xref:System.Windows.Controls.InkCanvas> ha un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà, che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ed è già un membro del <xref:System.Windows.UIElement.StylusPlugIns%2A> insieme. Personalizzata <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aggiunto per il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta riceve il <xref:System.Windows.Input.StylusPoint> dati dopo <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i dati. Di conseguenza, il <xref:System.Windows.Input.StylusPoint> dati non verranno filtrati fino a dopo che l'utente solleva la penna per terminare un tratto. Per filtrare l'input penna che l'utente viene tracciato, è necessario inserire il `FilterPlugin` prima di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Il codice c# seguente viene illustrato un personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna che viene disegnato.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 Derivando <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserendoli in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> raccolte, è possibile migliorare notevolmente il comportamento della penna. È possibile accedere il <xref:System.Windows.Input.StylusPoint> dati man mano che viene generati, offrendo la possibilità di personalizzare il <xref:System.Windows.Input.Stylus> input. Perché si dispone di accesso di basso livello per il <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare la raccolta di input penna e il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione avanzata dell'input penna](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [L'accesso e modifica dell'Input penna](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
