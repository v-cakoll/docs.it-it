---
title: Panoramica sul controllo ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: a11dcfc9030944365adda3656a8895912b0ef0d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43805221"
---
# <a name="tooltip-overview"></a>Panoramica sul controllo ToolTip
Una descrizione comando è una piccola finestra popup che viene visualizzato quando l'utente posiziona il puntatore del mouse su un elemento, ad esempio su un <xref:System.Windows.Controls.Button>. L'argomento introduce la descrizione comando e illustra come creare e personalizzare il relativo contenuto.  
  
 
  
<a name="what_is_a_tooltip"></a>   
## <a name="what-is-a-tooltip"></a>Che cos'è una descrizione comando?  
 Quando si sposta il puntatore del mouse su un elemento per cui esiste una descrizione comando, viene visualizzata una finestra con contenuto relativo all'elemento (ad esempio, testo che descrive la funzione di un controllo) per un periodo di tempo specificato. Se si sposta il puntatore del mouse all'esterno del controllo, la finestra scompare perché il contenuto della descrizione comando non può ricevere lo stato attivo.  
  
 Il contenuto di una descrizione comando può essere costituito da una o più righe di testo, immagini, forme o altro contenuto visivo. Per definire una descrizione comando per un controllo, impostare una delle proprietà seguenti sul contenuto della descrizione comando.  
  
-   <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 La proprietà da usare dipende dal fatto che il controllo che definisce la descrizione comando erediti dal <xref:System.Windows.FrameworkContentElement> o <xref:System.Windows.FrameworkElement> classe.  
  
<a name="create_tooltip"></a>   
## <a name="creating-a-tooltip"></a>Creazione di una descrizione comando  
 Nell'esempio seguente viene illustrato come creare una semplice descrizione comando impostando il <xref:System.Windows.FrameworkElement.ToolTip%2A> proprietà per un <xref:System.Windows.Controls.Button> controllo da una stringa di testo.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 È anche possibile definire una descrizione comando come un <xref:System.Windows.Controls.ToolTip> oggetto. L'esempio seguente usa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per specificare un <xref:System.Windows.Controls.ToolTip> oggetto come descrizione comando di un <xref:System.Windows.Controls.TextBox> elemento. Si noti che nell'esempio viene specificato il <xref:System.Windows.Controls.ToolTip> impostando la <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> proprietà.  
  
 [!code-xaml[ToolTipSimple#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 L'esempio seguente Usa codice per generare un <xref:System.Windows.Controls.ToolTip> oggetto. Nell'esempio viene creata una <xref:System.Windows.Controls.ToolTip> (`tt`) e lo associa a un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ToolTipSimple#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 È anche possibile creare il contenuto della descrizione comando che non è definito come un <xref:System.Windows.Controls.ToolTip> oggetto racchiudendo il contenuto in un elemento di layout, ad esempio un <xref:System.Windows.Controls.DockPanel>. Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.FrameworkElement.ToolTip%2A> proprietà di un <xref:System.Windows.Controls.TextBox> contenuto racchiuso in un <xref:System.Windows.Controls.DockPanel> controllo.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>   
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Uso delle proprietà delle classi ToolTip e ToolTipService  
 È possibile personalizzare il contenuto della descrizione comando impostando proprietà visive e applicando stili. Se si definisce la descrizione comando contenuta come un <xref:System.Windows.Controls.ToolTip> dell'oggetto, è possibile impostare le proprietà visive del <xref:System.Windows.Controls.ToolTip> oggetto. In caso contrario, è necessario impostare le proprietà associate equivalenti nel <xref:System.Windows.Controls.ToolTipService> classe.  
  
 Per un esempio di come impostare le proprietà per specificare la posizione del contenuto della descrizione comando usando il <xref:System.Windows.Controls.ToolTip> e <xref:System.Windows.Controls.ToolTipService> proprietà, vedere [posizionare un oggetto ToolTip](../../../../docs/framework/wpf/controls/how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>   
## <a name="styling-a-tooltip"></a>Applicazione di stili a una descrizione comando  
 È possibile applicare uno stile a un <xref:System.Windows.Controls.ToolTip> definendo una classe personalizzata <xref:System.Windows.Style>. L'esempio seguente definisce una <xref:System.Windows.Style> chiamati `Simple` che illustra come eseguire l'offset del posizionamento del <xref:System.Windows.Controls.ToolTip> e modificarne l'aspetto impostando il <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, e <xref:System.Windows.Controls.Control.FontWeight%2A>.  
  
 [!code-xaml[ToolTipSimple#Style](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>   
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Uso delle proprietà di ToolTipService relative all'intervallo di tempo  
 Il <xref:System.Windows.Controls.ToolTipService> classe fornisce le proprietà seguenti per impostare una descrizione comando i tempi di visualizzazione: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, e <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Usare la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> e <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> delle proprietà per specificare un ritardo, in genere breve, prima che un <xref:System.Windows.Controls.ToolTip> viene visualizzata e anche per specificare per quanto tempo un <xref:System.Windows.Controls.ToolTip> rimane visibile. Per altre informazioni, vedere [Procedura: ritardare la visualizzazione di un oggetto ToolTip](https://msdn.microsoft.com/library/618e05ef-f2bf-4a53-a0f4-aacb49918bd7).  
  
 Il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà determina se le descrizioni comandi per i controlli diversi vengono visualizzate senza un ritardo iniziale quando il puntatore del mouse si sposta rapidamente tra di essi. Per altre informazioni sul <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà, vedere [usare la proprietà BetweenShowDelay](../../../../docs/framework/wpf/controls/how-to-use-the-betweenshowdelay-property.md).  
  
 L'esempio seguente mostra come impostare queste proprietà per una descrizione comando.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ToolTipService>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipEventArgs>  
 <xref:System.Windows.Controls.ToolTipEventHandler>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
