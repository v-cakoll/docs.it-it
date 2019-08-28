---
title: Intercettazione dell'input dello stilo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 2547c0aa2f3a14080868c2760fa8999eb99d3d16
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046324"
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo
L' <xref:System.Windows.Input.StylusPlugIns> architettura fornisce un meccanismo per l'implementazione del controllo di basso <xref:System.Windows.Input.Stylus> livello sull'input e la creazione di <xref:System.Windows.Ink.Stroke> oggetti di input penna digitali. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classe fornisce un meccanismo per implementare il comportamento personalizzato e applicarlo al flusso di dati provenienti dal dispositivo stilo per ottenere prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Architettura](#Architecture)  
  
- [Implementazione di plug-in dello stilo](#ImplementingStylusPlugins)  
  
- [Aggiunta del plug-in a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architettura  
 Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> è l'evoluzione delle API [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) , descritte in [accesso e manipolazione dell'input penna](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), in [Microsoft Windows XP Tablet PC Edition Software Development Kit 1,7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Ogni <xref:System.Windows.UIElement> ha una <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>oggetto. È possibile aggiungere un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetto alla <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà di un elemento per <xref:System.Windows.Input.StylusPoint> modificare i dati durante la generazione. <xref:System.Windows.Input.StylusPoint>i dati sono costituiti da tutte le proprietà supportate dal digitalizzatore di sistema <xref:System.Windows.Input.StylusPoint.X%2A> , <xref:System.Windows.Input.StylusPoint.Y%2A> inclusi i <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> dati del punto e, nonché i dati.  
  
 Gli oggetti vengono inseriti direttamente nel flusso di dati provenienti <xref:System.Windows.Input.Stylus> dal <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> dispositivo quando <xref:System.Windows.UIElement.StylusPlugIns%2A> si aggiunge alla proprietà. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> L'ordine in cui i plug-in vengono aggiunti alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta determina l'ordine in cui riceveranno <xref:System.Windows.Input.StylusPoint> i dati. Se ad esempio si aggiunge un plug-in di filtro che limita l'input a una determinata area, quindi si aggiunge un plug-in che riconosce i movimenti quando vengono scritti, il plug-in che riconosce i movimenti riceverà dati filtrati <xref:System.Windows.Input.StylusPoint> .  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementazione di plug-in dello stilo  
 Per implementare un plug-in, derivare una classe <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>da. Questa classe viene applicata o il flusso di dati in entrata da <xref:System.Windows.Input.Stylus>. In questa classe è possibile modificare i valori dei <xref:System.Windows.Input.StylusPoint> dati.  
  
> [!CAUTION]
> Se un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetto genera o genera un'eccezione, l'applicazione verrà chiusa. È necessario verificare accuratamente i <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> controlli che utilizzano un e utilizzare un controllo solo se si è certi che non genererà un'eccezione.  
  
 Nell'esempio seguente viene illustrato un plug-in che limita l'input dello stilo modificando <xref:System.Windows.Input.StylusPoint.X%2A> i <xref:System.Windows.Input.StylusPoint.Y%2A> valori e nei <xref:System.Windows.Input.StylusPoint> dati in arrivo dal <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiunta del plug-in a un InkCanvas  
 Il modo più semplice per usare il plug-in personalizzato consiste nell'implementare una classe che deriva da InkCanvas e aggiungerla alla <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà.  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.InkCanvas> oggetto personalizzato che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si aggiunge un `FilterInkCanvas` oggetto all'applicazione e lo si esegue, si noterà che l'input penna non è limitato a un'area fino a quando l'utente non completa un tratto. Questo è dovuto al <xref:System.Windows.Controls.InkCanvas> fatto che <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> ha una proprietà, che <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> è un oggetto ed è già un <xref:System.Windows.UIElement.StylusPlugIns%2A> membro della raccolta. L'oggetto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzato aggiunto <xref:System.Windows.UIElement.StylusPlugIns%2A> alla raccolta riceve i dati <xref:System.Windows.Input.StylusPoint> dopo <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> la ricezione dei dati. Di conseguenza, i <xref:System.Windows.Input.StylusPoint> dati non verranno filtrati fino a quando l'utente non solleva la penna per terminare un tratto. Per filtrare l'input penna quando l'utente lo disegna, è necessario inserire `FilterPlugin` <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>prima di.  
  
 Il codice C# seguente illustra un oggetto <xref:System.Windows.Controls.InkCanvas> personalizzato che filtra l'input penna mentre viene disegnato.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 Derivando le proprie <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserendole in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> raccolte, è possibile migliorare significativamente il comportamento dell'input penna digitale. Si ha accesso ai <xref:System.Windows.Input.StylusPoint> dati generati, offrendo la possibilità di personalizzare l' <xref:System.Windows.Input.Stylus> input. Poiché si dispone di un accesso di basso livello ai <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare la raccolta di input penna e il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e modifica dell'input penna](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
