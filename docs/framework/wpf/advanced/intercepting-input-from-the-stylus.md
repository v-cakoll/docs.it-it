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
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095138"
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo
L'architettura <xref:System.Windows.Input.StylusPlugIns> fornisce un meccanismo per l'implementazione del controllo di basso livello sull'input <xref:System.Windows.Input.Stylus> e la creazione di oggetti <xref:System.Windows.Ink.Stroke> di input digitali. La classe <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> fornisce un meccanismo per implementare il comportamento personalizzato e applicarlo al flusso di dati provenienti dal dispositivo stilo per ottenere prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Architettura](#Architecture)  
  
- [Implementazione di plug-in dello stilo](#ImplementingStylusPlugins)  
  
- [Aggiunta del plug-in a un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusioni](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architecture  
 Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> è l'evoluzione delle API di [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) , descritte in [accesso e manipolazione dell'input penna](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10)).  
  
 Ogni <xref:System.Windows.UIElement> dispone di una proprietà <xref:System.Windows.UIElement.StylusPlugIns%2A> che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. È possibile aggiungere una <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> alla proprietà <xref:System.Windows.UIElement.StylusPlugIns%2A> di un elemento per modificare i dati <xref:System.Windows.Input.StylusPoint> durante la generazione. i dati <xref:System.Windows.Input.StylusPoint> sono costituiti da tutte le proprietà supportate dal digitalizzatore di sistema, inclusi i dati di <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> punto, nonché i dati <xref:System.Windows.Input.StylusPoint.PressureFactor%2A>.  
  
 Gli oggetti <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> vengono inseriti direttamente nel flusso di dati provenienti dal dispositivo <xref:System.Windows.Input.Stylus> quando si aggiunge il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> alla proprietà <xref:System.Windows.UIElement.StylusPlugIns%2A>. L'ordine in cui i plug-in vengono aggiunti alla raccolta <xref:System.Windows.UIElement.StylusPlugIns%2A> determina l'ordine in cui riceveranno i dati <xref:System.Windows.Input.StylusPoint>. Se ad esempio si aggiunge un plug-in di filtro che limita l'input a una determinata area, quindi si aggiunge un plug-in che riconosce i movimenti quando vengono scritti, il plug-in che riconosce i movimenti riceverà dati filtrati <xref:System.Windows.Input.StylusPoint>.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementazione di plug-in dello stilo  
 Per implementare un plug-in, derivare una classe da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Questa classe viene applicata o il flusso di dati in entrata dal <xref:System.Windows.Input.Stylus>. In questa classe è possibile modificare i valori dei dati <xref:System.Windows.Input.StylusPoint>.  
  
> [!CAUTION]
> Se un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> genera o causa un'eccezione, l'applicazione verrà chiusa. È necessario verificare accuratamente i controlli che utilizzano un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e utilizzare un controllo solo se si è certi che l'<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> non genererà un'eccezione.  
  
 Nell'esempio riportato di seguito viene illustrato un plug-in che limita l'input dello stilo modificando il <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> i valori nei dati del <xref:System.Windows.Input.StylusPoint> così come provengono dal dispositivo <xref:System.Windows.Input.Stylus>.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiunta del plug-in a un InkCanvas  
 Il modo più semplice per usare il plug-in personalizzato consiste nell'implementare una classe che deriva da InkCanvas e aggiungerla alla proprietà <xref:System.Windows.UIElement.StylusPlugIns%2A>.  
  
 Nell'esempio seguente viene illustrata una <xref:System.Windows.Controls.InkCanvas> personalizzata che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si aggiunge un `FilterInkCanvas` all'applicazione e lo si esegue, si noterà che l'input penna non è limitato a un'area fino a quando l'utente non completa un tratto. Questo perché il <xref:System.Windows.Controls.InkCanvas> dispone di una proprietà <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>, che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ed è già un membro della raccolta <xref:System.Windows.UIElement.StylusPlugIns%2A>. Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzato aggiunto alla raccolta di <xref:System.Windows.UIElement.StylusPlugIns%2A> riceve i dati <xref:System.Windows.Input.StylusPoint> dopo che <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i dati. Di conseguenza, i dati <xref:System.Windows.Input.StylusPoint> non verranno filtrati fino a quando l'utente non solleva la penna per terminare un tratto. Per filtrare l'input penna quando l'utente lo disegna, è necessario inserire il `FilterPlugin` prima della <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Nel codice C# seguente viene illustrato un <xref:System.Windows.Controls.InkCanvas> personalizzato che filtra l'input penna mentre viene disegnato.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusioni  
 Derivando le proprie classi di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e inserendole in raccolte di <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, è possibile migliorare significativamente il comportamento dell'input penna digitale. Si ha accesso ai dati <xref:System.Windows.Input.StylusPoint> durante la generazione, offrendo la possibilità di personalizzare l'input di <xref:System.Windows.Input.Stylus>. Poiché si dispone di un accesso di basso livello ai dati <xref:System.Windows.Input.StylusPoint>, è possibile implementare la raccolta di input penna e il rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e modifica dell'input penna](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
