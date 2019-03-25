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
ms.openlocfilehash: 29003779825b92402fa12b810c1a099731ac8af6
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409458"
---
# <a name="expander-overview"></a>Cenni preliminari sul controllo Expander
Un <xref:System.Windows.Controls.Expander> controllo fornisce un modo per fornire contenuto in un'area espandibile simile a una finestra che include un'intestazione.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Creazione di un controllo Expander semplice  
 Nell'esempio seguente viene illustrato come creare una semplice <xref:System.Windows.Controls.Expander> controllo. Questo esempio viene creato un <xref:System.Windows.Controls.Expander> simile a quello riportato nella figura precedente.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Il <xref:System.Windows.Controls.ContentControl.Content%2A> e <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di un <xref:System.Windows.Controls.Expander> può anche contenere contenuto complesso, ad esempio <xref:System.Windows.Controls.RadioButton> e <xref:System.Windows.Controls.Image> oggetti.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Impostazione della direzione dell'area del contenuto espandibile  
 È possibile impostare l'area di contenuto di un <xref:System.Windows.Controls.Expander> controllo per espandere in uno dei quattro direzioni (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, o <xref:System.Windows.Controls.ExpandDirection.Right>) usando il <xref:System.Windows.Controls.ExpandDirection> proprietà. Quando l'area del contenuto è compresso, solo il <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e vengono visualizzati il relativo interruttore. Oggetto <xref:System.Windows.Controls.Button> controllo che visualizza una freccia direzionale viene usato come un interruttore per espandere o comprimere l'area del contenuto. Se viene espansa, il <xref:System.Windows.Controls.Expander> prova a visualizzare tutto il contenuto in un'area simile a finestra.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controllo delle dimensioni di un controllo Expander in un pannello  
 Se un <xref:System.Windows.Controls.Expander> controllo si trova all'interno di un controllo layout che eredita da <xref:System.Windows.Controls.Panel>, come <xref:System.Windows.Controls.StackPanel>, non si specifica un <xref:System.Windows.FrameworkElement.Height%2A> sul <xref:System.Windows.Controls.Expander> quando il <xref:System.Windows.Controls.Expander.ExpandDirection%2A> è impostata su <xref:System.Windows.Controls.ExpandDirection.Down> o <xref:System.Windows.Controls.ExpandDirection.Up>. Allo stesso modo, non si specifica un <xref:System.Windows.FrameworkElement.Width%2A> nella <xref:System.Windows.Controls.Expander> quando il <xref:System.Windows.Controls.Expander.ExpandDirection%2A> è impostata su <xref:System.Windows.Controls.ExpandDirection.Left> o <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 Quando si imposta una dimensione in un <xref:System.Windows.Controls.Expander> controllo nella direzione che viene visualizzato il contenuto espanso, il <xref:System.Windows.Controls.Expander> assume il controllo dell'area in cui viene usata dal contenuto e visualizza un bordo intorno a esso. Il bordo viene visualizzato anche quando il contenuto è compresso. Per impostare le dimensioni dell'area del contenuto espansa, impostare le dimensioni del contenuto del <xref:System.Windows.Controls.Expander>, o se si desidera che lo scorrimento lungo, la funzionalità di <xref:System.Windows.Controls.ScrollViewer> che racchiude il contenuto.  
  
 Quando un <xref:System.Windows.Controls.Expander> controllo è l'ultimo elemento in un <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] viene impostata automaticamente la <xref:System.Windows.Controls.Expander> dimensioni deve essere uguale all'area rimanente del <xref:System.Windows.Controls.DockPanel>. Per evitare questo comportamento predefinito, impostare il <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà la <xref:System.Windows.Controls.DockPanel> dell'oggetto a `false`, o assicurarsi che il <xref:System.Windows.Controls.Expander> non è l'ultimo elemento in un <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Creazione di contenuto scorrevole  
 Se il contenuto è troppo grande per le dimensioni dell'area del contenuto, è possibile eseguire il wrapping di contenuto di un <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> per fornire contenuto scorrevole. Il <xref:System.Windows.Controls.Expander> controllo non fornisce automaticamente funzionalità di scorrimento. La figura seguente mostra un' <xref:System.Windows.Controls.Expander> controllo contenente un <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
 **Controllo Expander in un controllo ScrollViewer**  
  
 ![Screenshot che mostra un controllo expander con ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Quando si inserisce un <xref:System.Windows.Controls.Expander> controllare in un <xref:System.Windows.Controls.ScrollViewer>, impostare il <xref:System.Windows.Controls.ScrollViewer> dimensione proprietà che corrisponde alla direzione in cui il <xref:System.Windows.Controls.Expander> viene visualizzato alla dimensione del contenuto di <xref:System.Windows.Controls.Expander> area del contenuto. Ad esempio, se si imposta il <xref:System.Windows.Controls.Expander.ExpandDirection%2A> proprietà il <xref:System.Windows.Controls.Expander> per <xref:System.Windows.Controls.ExpandDirection.Down> (si apre l'area di contenuto verso il basso), impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà il <xref:System.Windows.Controls.ScrollViewer> controllo sull'altezza richiesta per l'area del contenuto. Se invece viene impostata la dimensione dell'altezza del contenuto stesso, <xref:System.Windows.Controls.ScrollViewer> non riconosce questa impostazione e di conseguenza, non fornisce contenuto scorrevole.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso e che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Questo esempio viene creato un <xref:System.Windows.Controls.Expander> che è simile alla figura all'inizio di questa sezione.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Uso delle proprietà di allineamento  
 È possibile allineare il contenuto impostando il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> proprietà di <xref:System.Windows.Controls.Expander> controllo. Quando si impostano queste proprietà, l'allineamento viene applicato all'intestazione e al contenuto espanso.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Procedure relative alle proprietà](expander-how-to-topics.md)
