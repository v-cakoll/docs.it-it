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
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181926"
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo
L'architettura <xref:System.Windows.Input.StylusPlugIns> fornisce un meccanismo per <xref:System.Windows.Input.Stylus> l'implementazione del <xref:System.Windows.Ink.Stroke> controllo di basso livello sull'input e la creazione di oggetti input penna digitali. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classe fornisce un meccanismo che consente di implementare un comportamento personalizzato e di applicarlo al flusso di dati provenienti dal dispositivo stilo per ottenere prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- [Architettura](#Architecture)  
  
- [Implementazione dei plug-in dello stiloImplementing Stylus Plug-ins](#ImplementingStylusPlugins)  
  
- [Aggiunta del plug-in a un oggetto InkCanvasAdding Your Plug-in to an InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 L'evoluzione <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> delle API [StylusInput,](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) descritta in Accesso e modifica dell'input penna . [Accessing and Manipulating Pen Input](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))  
  
 Ognuna <xref:System.Windows.UIElement> <xref:System.Windows.UIElement.StylusPlugIns%2A> ha una <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>proprietà che è un oggetto . È possibile <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aggiungere un a <xref:System.Windows.UIElement.StylusPlugIns%2A> alla <xref:System.Windows.Input.StylusPoint> proprietà di un elemento per modificare i dati man mano che vengono generati. <xref:System.Windows.Input.StylusPoint>i dati sono costituiti da tutte le proprietà <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.Y%2A> supportate dal digitalizzatore di sistema, inclusi i dati punto e , nonché <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> i dati.  
  
 Gli <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti vengono inseriti direttamente nel <xref:System.Windows.Input.Stylus> flusso di dati <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> provenienti dal dispositivo quando si aggiunge il alla <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà . L'ordine in cui i plug-in vengono aggiunti alla <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta <xref:System.Windows.Input.StylusPoint> determina l'ordine in cui riceveranno i dati. Ad esempio, se si aggiunge un plug-in di filtro che limita l'input a una determinata area e quindi si aggiunge un plug-in che riconosce i movimenti così come vengono scritti, il plug-in che riconosce i movimenti riceverà i dati filtrati. <xref:System.Windows.Input.StylusPoint>  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>Implementazione dei plug-in dello stiloImplementing Stylus Plug-ins  
 Per implementare un plug-in, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>derivare una classe da . Questa classe viene applicata o il flusso <xref:System.Windows.Input.Stylus>di dati non appena arriva dall'oggetto . In questa classe è possibile <xref:System.Windows.Input.StylusPoint> modificare i valori dei dati.  
  
> [!CAUTION]
> Se <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> un oggetto genera o causa un'eccezione, l'applicazione verrà chiusa. È necessario testare accuratamente <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> i controlli che utilizzano <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> un e utilizzare solo un controllo se si è certi che non verrà generata un'eccezione.  
  
 Nell'esempio <xref:System.Windows.Input.StylusPoint> seguente viene illustrato un plug-in che <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.Y%2A> limita l'input dello stilo modificando i valori e nei dati provenienti dal <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiunta del plug-in a un oggetto InkCanvasAdding Your Plug-in to an InkCanvas  
 Il modo più semplice per usare il plug-in personalizzato consiste nell'implementare <xref:System.Windows.UIElement.StylusPlugIns%2A> una classe che deriva da InkCanvas e aggiungerla alla proprietà.  
  
 Nell'esempio seguente <xref:System.Windows.Controls.InkCanvas> viene illustrato un oggetto personalizzato che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si `FilterInkCanvas` aggiunge un all'applicazione e lo si esegue, si noterà che l'input penna non è limitato a un'area fino a quando l'utente non ha completato un tratto. Ciò è <xref:System.Windows.Controls.InkCanvas> dovuto <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> al fatto <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> che l'oggetto dispone <xref:System.Windows.UIElement.StylusPlugIns%2A> di una proprietà , che è un ed è già un membro della raccolta. La <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> personalizzazione aggiunta <xref:System.Windows.UIElement.StylusPlugIns%2A> alla raccolta <xref:System.Windows.Input.StylusPoint> riceve <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> i dati dopo la ricezione dei dati. Di conseguenza, <xref:System.Windows.Input.StylusPoint> i dati non verranno filtrati fino a quando l'utente non solleva la penna per terminare un tratto. Per filtrare l'input penna mentre viene `FilterPlugin` disegnato <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>dall'utente, è necessario inserire il file prima del file .  
  
 Il seguente codice in <xref:System.Windows.Controls.InkCanvas> C, viene illustrato un'operazione personalizzata che filtra l'input penna mentre viene disegnata.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>Conclusioni  
 Derivando le <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> proprie classi e <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> inserendole nelle raccolte, è possibile migliorare notevolmente il comportamento dell'input penna digitale. Si ha accesso <xref:System.Windows.Input.StylusPoint> ai dati così come vengono generati, offrendo la possibilità di personalizzare l'input. <xref:System.Windows.Input.Stylus> Poiché si dispone di tale <xref:System.Windows.Input.StylusPoint> accesso di basso livello ai dati, è possibile implementare la raccolta e il rendering dell'input penna con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione avanzata dell'input penna](advanced-ink-handling.md)
- [Accesso e manipolazione dell'input penna](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
