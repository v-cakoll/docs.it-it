---
title: Cenni preliminari sul controllo Expander
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187119"
---
# <a name="expander-overview"></a>Cenni preliminari sul controllo Expander
Un <xref:System.Windows.Controls.Expander> controllo fornisce un modo per fornire contenuto in un'area espandibile simile a una finestra e include un'intestazione.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>Creazione di un controllo Expander semplice  
 Nell'esempio seguente viene illustrato <xref:System.Windows.Controls.Expander> come creare un controllo semplice. Questo esempio <xref:System.Windows.Controls.Expander> crea un oggetto simile all'illustrazione precedente.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 L'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> and <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di un <xref:System.Windows.Controls.Expander> oggetto <xref:System.Windows.Controls.RadioButton> può <xref:System.Windows.Controls.Image> inoltre contenere contenuto complesso, ad esempio oggetti e .  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Impostazione della direzione dell'area del contenuto espandibile  
 È possibile impostare l'area <xref:System.Windows.Controls.Expander> del contenuto di<xref:System.Windows.Controls.ExpandDirection.Down>un <xref:System.Windows.Controls.ExpandDirection.Up> <xref:System.Windows.Controls.ExpandDirection.Left>controllo <xref:System.Windows.Controls.ExpandDirection.Right>in modo <xref:System.Windows.Controls.ExpandDirection> che si espanda in una delle quattro direzioni , , o ) utilizzando la proprietà . Quando l'area del contenuto <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> è compressa, vengono visualizzati solo il pulsante di attivazione/disattivazione e il relativo pulsante di attivazione/disattivazione. Un <xref:System.Windows.Controls.Button> controllo che visualizza una freccia direzionale viene utilizzato come interruttore per espandere o comprimere l'area del contenuto. Quando viene <xref:System.Windows.Controls.Expander> espanso, il tentativo di visualizzare tutto il contenuto in un'area simile a una finestra.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controllo delle dimensioni di un controllo Expander in un pannello  
 Se <xref:System.Windows.Controls.Expander> un controllo si trova all'interno di un controllo di <xref:System.Windows.Controls.Expander> layout <xref:System.Windows.Controls.Expander.ExpandDirection%2A> che eredita <xref:System.Windows.Controls.ExpandDirection.Down> da <xref:System.Windows.Controls.ExpandDirection.Up> <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.StackPanel>, ad esempio , non specificare un <xref:System.Windows.FrameworkElement.Height%2A> oggetto quando la proprietà è impostata su o . Analogamente, non <xref:System.Windows.FrameworkElement.Width%2A> specificare <xref:System.Windows.Controls.Expander> un <xref:System.Windows.Controls.Expander.ExpandDirection%2A> on quando <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right>la proprietà è impostata su o .  
  
 Quando si imposta una <xref:System.Windows.Controls.Expander> dimensione di dimensione su un controllo nella <xref:System.Windows.Controls.Expander> direzione di visualizzazione del contenuto espanso, assume il controllo dell'area utilizzata dal contenuto e visualizza un bordo intorno ad esso. Il bordo viene visualizzato anche quando il contenuto è compresso. Per impostare le dimensioni dell'area di contenuto espansa, impostare le dimensioni del contenuto di <xref:System.Windows.Controls.Expander>, o se si desidera funzionalità di scorrimento, sull'area <xref:System.Windows.Controls.ScrollViewer> che racchiude il contenuto.  
  
 Quando <xref:System.Windows.Controls.Expander> un controllo è l'ultimo elemento in <xref:System.Windows.Controls.DockPanel>un oggetto [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] , imposta automaticamente le <xref:System.Windows.Controls.Expander> dimensioni in modo che corrispondano all'area rimanente <xref:System.Windows.Controls.DockPanel>del file . Per evitare questo comportamento <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> predefinito, <xref:System.Windows.Controls.DockPanel> impostare la proprietà dell'oggetto su `false`o assicurarsi che l'oggetto <xref:System.Windows.Controls.Expander> non sia l'ultimo elemento di un <xref:System.Windows.Controls.DockPanel>oggetto .  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>Creazione di contenuto scorrevole  
 Se il contenuto è troppo grande per le dimensioni dell'area <xref:System.Windows.Controls.Expander> di <xref:System.Windows.Controls.ScrollViewer> contenuto, è possibile eseguire il wrapping del contenuto di un oggetto in un oggetto per fornire contenuto scorrevole. Il <xref:System.Windows.Controls.Expander> controllo non fornisce automaticamente la funzionalità di scorrimento. Nella figura seguente <xref:System.Windows.Controls.Expander> viene illustrato <xref:System.Windows.Controls.ScrollViewer> un controllo che contiene un controllo.  
  
 **Controllo Expander in un controllo ScrollViewer**  
  
 ![Screenshot che mostra un espansore con ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Quando si <xref:System.Windows.Controls.Expander> inserisce <xref:System.Windows.Controls.ScrollViewer>un controllo <xref:System.Windows.Controls.ScrollViewer> in un oggetto , impostare la proprietà della dimensione che corrisponde alla direzione in cui il <xref:System.Windows.Controls.Expander> contenuto si apre alle dimensioni dell'area <xref:System.Windows.Controls.Expander> di contenuto. Ad esempio, se <xref:System.Windows.Controls.Expander.ExpandDirection%2A> si imposta <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ExpandDirection.Down> la proprietà su (l'area del contenuto si apre), impostare la <xref:System.Windows.FrameworkElement.Height%2A> proprietà del <xref:System.Windows.Controls.ScrollViewer> controllo sull'altezza richiesta per l'area di contenuto. Se invece si imposta la dimensione <xref:System.Windows.Controls.ScrollViewer> dell'altezza sul contenuto stesso, non riconosce questa impostazione e pertanto non fornisce contenuto scorrevole.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Expander> illustrato come creare un controllo <xref:System.Windows.Controls.ScrollViewer> con contenuto complesso e che contiene un controllo. Questo esempio <xref:System.Windows.Controls.Expander> crea un oggetto simile all'illustrazione all'inizio di questa sezione.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>Uso delle proprietà di allineamento  
 È possibile allineare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> il <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> contenuto <xref:System.Windows.Controls.Expander> impostando le proprietà e sul controllo . Quando si impostano queste proprietà, l'allineamento viene applicato all'intestazione e al contenuto espanso.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Argomenti relativi alle procedure](expander-how-to-topics.md)
