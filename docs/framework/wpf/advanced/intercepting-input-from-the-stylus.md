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
ms.openlocfilehash: c012eeb7ef7dad8c52b8b9a5f153582710c1fd73
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43725033"
---
# <a name="intercepting-input-from-the-stylus"></a>Intercettazione dell'input dello stilo
Il <xref:System.Windows.Input.StylusPlugIns> architettura fornisce un meccanismo per l'implementazione del controllo di basso livello tramite <xref:System.Windows.Input.Stylus> input e la creazione di input penna digitale <xref:System.Windows.Ink.Stroke> oggetti. Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classe fornisce un meccanismo per implementare il comportamento personalizzato e applicarlo al flusso di dati provenienti dal dispositivo stilo per prestazioni ottimali.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   [Architettura](#Architecture)  
  
-   [Implementazione di Plug-in dello stilo](#ImplementingStylusPlugins)  
  
-   [Aggiungere il plug-in con un InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [Conclusione](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>Architettura  
 Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> è l'evoluzione del [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) le API, descritto in [accesso e modifica di Input penna](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), nella [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).  
  
 Ciascuna <xref:System.Windows.UIElement> ha un <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà che è un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. È possibile aggiungere un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> a un elemento <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà da modificare <xref:System.Windows.Input.StylusPoint> dati man mano che viene generati. <xref:System.Windows.Input.StylusPoint> i dati è costituito da tutte le proprietà supportate dal digitalizzatore del sistema, tra cui il <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> punti dati, nonché <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> dati.  
  
 I <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> gli oggetti vengono inseriti direttamente nel flusso di dati provenienti dal <xref:System.Windows.Input.Stylus> dispositivo quando si aggiunge il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> per il <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà. L'ordine in cui vengono aggiunti i plug-in per il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta determina l'ordine in cui riceveranno <xref:System.Windows.Input.StylusPoint> dei dati. Ad esempio, se si aggiunge un plug-in filtro che limita l'input per una determinata area e quindi aggiungere un plug-in riconosce i movimenti mentre vengono scritti, il plug-in verrà visualizzato filtrato <xref:System.Windows.Input.StylusPoint> dei dati.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>Implementazione di Plug-in dello stilo  
 Per implementare un plug-in, derivare una classe da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>. Questa classe viene applicata al flusso di dati in arrivo dal <xref:System.Windows.Input.Stylus>. In questa classe è possibile modificare i valori del <xref:System.Windows.Input.StylusPoint> dati.  
  
> [!CAUTION]
>  Se un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> genera un'eccezione oppure genera un'eccezione, l'applicazione verrà chiusa. È consigliabile verificare attentamente i controlli che utilizzano un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e usare solo un controllo se si è certi di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> non genererà un'eccezione.  
  
 Nell'esempio seguente viene illustrato un plug-in che limita l'input dello stilo modificando la <xref:System.Windows.Input.StylusPoint.X%2A> e <xref:System.Windows.Input.StylusPoint.Y%2A> i valori la <xref:System.Windows.Input.StylusPoint> dati man mano che provengono dal <xref:System.Windows.Input.Stylus> dispositivo.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>Aggiungere il plug-in con un InkCanvas  
 Il modo più semplice per usare il plug-in personalizzato consiste nell'implementare una classe che deriva dall'oggetto InkCanvas e aggiungerlo al <xref:System.Windows.UIElement.StylusPlugIns%2A> proprietà.  
  
 L'esempio seguente illustra un oggetto personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 Se si aggiunge un `FilterInkCanvas` all'applicazione e l'esecuzione, si noterà che l'input penna non è limitato a un'area fino a dopo che l'utente ha completato un tratto. Infatti il <xref:System.Windows.Controls.InkCanvas> ha un <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> proprietà, ovvero un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ed è già membro del <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta. Personalizzata <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> aggiunto in precedenza per il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta riceve le <xref:System.Windows.Input.StylusPoint> dati dopo <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i dati. Di conseguenza, il <xref:System.Windows.Input.StylusPoint> dati non verranno filtrati fino a dopo che l'utente solleva la penna per terminare un tratto. Per filtrare l'input penna che viene tracciato l'utente, è necessario inserire il `FilterPlugin` prima di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.  
  
 Il codice c# seguente illustra un oggetto personalizzato <xref:System.Windows.Controls.InkCanvas> che filtra l'input penna che viene tracciato.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 Derivando <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classi e inserendoli in <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> raccolte, è possibile migliorare notevolmente il comportamento dell'input penna digitale. È possibile utilizzare il <xref:System.Windows.Input.StylusPoint> dati man mano che viene generati, offrendo la possibilità di personalizzare il <xref:System.Windows.Input.Stylus> input. Perché si dispone di accesso di basso livello per il <xref:System.Windows.Input.StylusPoint> dati, è possibile implementare la raccolta dell'input penna e rendering con prestazioni ottimali per l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione avanzata dell'input penna](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [L'accesso e modifica dell'Input penna](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
