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
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181943"
---
# <a name="tooltip-overview"></a>Panoramica sul controllo ToolTip
Una descrizione comando è una piccola finestra popup che viene visualizzata quando un <xref:System.Windows.Controls.Button>utente posiziona il puntatore del mouse su un elemento, ad esempio su un oggetto . L'argomento introduce la descrizione comando e illustra come creare e personalizzare il relativo contenuto.  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a>Che cos'è una descrizione comando?  
 Quando si sposta il puntatore del mouse su un elemento per cui esiste una descrizione comando, viene visualizzata una finestra con contenuto relativo all'elemento (ad esempio, testo che descrive la funzione di un controllo) per un periodo di tempo specificato. Se si sposta il puntatore del mouse all'esterno del controllo, la finestra scompare perché il contenuto della descrizione comando non può ricevere lo stato attivo.  
  
 Il contenuto di una descrizione comando può essere costituito da una o più righe di testo, immagini, forme o altro contenuto visivo. Per definire una descrizione comando per un controllo, impostare una delle proprietà seguenti sul contenuto della descrizione comando.  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 La proprietà utilizzata varia a seconda che il controllo <xref:System.Windows.FrameworkContentElement> che <xref:System.Windows.FrameworkElement> definisce la descrizione comandi erediti dalla classe o .  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a>Creazione di una descrizione comando  
 Nell'esempio seguente viene illustrato come creare <xref:System.Windows.FrameworkElement.ToolTip%2A> una <xref:System.Windows.Controls.Button> semplice descrizione comando impostando la proprietà per un controllo su una stringa di testo.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 È inoltre possibile definire <xref:System.Windows.Controls.ToolTip> una descrizione comando come oggetto. Nell'esempio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguente viene <xref:System.Windows.Controls.ToolTip> utilizzato per specificare un oggetto come descrizione comando di un <xref:System.Windows.Controls.TextBox> elemento. Si noti che <xref:System.Windows.Controls.ToolTip> l'esempio <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> specifica il mediante l'impostazione della proprietà.  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.ToolTip> utilizzato il codice per generare un oggetto. Nell'esempio <xref:System.Windows.Controls.ToolTip> viene`tt`creato un oggetto <xref:System.Windows.Controls.Button>( ) e viene associato a un oggetto .  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 È inoltre possibile creare contenuto della <xref:System.Windows.Controls.ToolTip> descrizione comandi non definito come oggetto racchiudendo <xref:System.Windows.Controls.DockPanel>il contenuto della descrizione comandi in un elemento di layout, ad esempio . Nell'esempio seguente viene <xref:System.Windows.FrameworkElement.ToolTip%2A> illustrato come <xref:System.Windows.Controls.TextBox> impostare la proprietà <xref:System.Windows.Controls.DockPanel> di un a a contenuto racchiuso in un controllo.  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a>Uso delle proprietà delle classi ToolTip e ToolTipService  
 È possibile personalizzare il contenuto della descrizione comando impostando proprietà visive e applicando stili. Se si definisce il <xref:System.Windows.Controls.ToolTip> contenuto della descrizione comandi come <xref:System.Windows.Controls.ToolTip> oggetto, è possibile impostare le proprietà visive dell'oggetto. In caso contrario, è necessario <xref:System.Windows.Controls.ToolTipService> impostare proprietà associate equivalenti nella classe.  
  
 Per un esempio di impostazione delle proprietà per specificare <xref:System.Windows.Controls.ToolTip> la <xref:System.Windows.Controls.ToolTipService> posizione del contenuto della descrizione comandi utilizzando le proprietà e , vedere [Posizione di una descrizione comandi](how-to-position-a-tooltip.md).  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a>Applicazione di stili a una descrizione comando  
 È possibile <xref:System.Windows.Controls.ToolTip> applicare uno <xref:System.Windows.Style>stile a definendo un file . Nell'esempio riportato <xref:System.Windows.Style> `Simple` di seguito viene definita una <xref:System.Windows.Controls.ToolTip> chiamata che mostra <xref:System.Windows.Controls.Control.Background%2A>come <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A>eseguire <xref:System.Windows.Controls.Control.FontWeight%2A>l'offset della posizione e modificarne l'aspetto impostando , , e .  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a>Uso delle proprietà di ToolTipService relative all'intervallo di tempo  
 La <xref:System.Windows.Controls.ToolTipService> classe fornisce le seguenti proprietà per <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>impostare i tempi di visualizzazione della descrizione comandi: , <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>e <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.  
  
 Utilizzare <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> le <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> proprietà e per specificare un <xref:System.Windows.Controls.ToolTip> ritardo, in genere <xref:System.Windows.Controls.ToolTip> breve, prima che venga visualizzato un oggetto e anche per specificare per quanto tempo un oggetto rimane visibile. Per altre informazioni, vedere [Procedura: ritardare la visualizzazione di un oggetto ToolTip](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).  
  
 La <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà determina se le descrizioni comandi per controlli diversi vengono visualizzate senza un ritardo iniziale quando si sposta rapidamente il puntatore del mouse tra di essi. Per ulteriori informazioni <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> sulla proprietà , vedere [Utilizzare la proprietà BetweenShowDelay](how-to-use-the-betweenshowdelay-property.md).  
  
 L'esempio seguente mostra come impostare queste proprietà per una descrizione comando.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [Argomenti relativi alle procedure](tooltip-how-to-topics.md)
