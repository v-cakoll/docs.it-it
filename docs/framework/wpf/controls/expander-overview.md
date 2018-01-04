---
title: Cenni preliminari sul controllo Expander
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
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f0623ed4c84247cc1759a203e3b95dd895cee2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="expander-overview"></a>Cenni preliminari sul controllo Expander
Un <xref:System.Windows.Controls.Expander> fornisce un modo per fornire contenuto in un'area espandibile è simile a una finestra che include un'intestazione.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Creazione di un controllo Expander semplice  
 Nell'esempio seguente viene illustrato come creare un semplice <xref:System.Windows.Controls.Expander> controllo. Questo esempio viene creato un <xref:System.Windows.Controls.Expander> simile a quello riportato nella figura precedente.  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Il <xref:System.Windows.Controls.ContentControl.Content%2A> e <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di un <xref:System.Windows.Controls.Expander> possono anche contenere contenuto complesso, ad esempio <xref:System.Windows.Controls.RadioButton> e <xref:System.Windows.Controls.Image> oggetti.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Impostazione della direzione dell'area del contenuto espandibile  
 È possibile impostare l'area del contenuto di un <xref:System.Windows.Controls.Expander> controllo per espandere in uno dei quattro direzioni (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, o <xref:System.Windows.Controls.ExpandDirection.Right>) utilizzando il <xref:System.Windows.Controls.ExpandDirection> proprietà. Quando l'area del contenuto è compressa, solo il <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il relativo interruttore. Oggetto <xref:System.Windows.Controls.Button> controllo che consente di visualizzare una freccia direzionale viene utilizzato come un interruttore per espandere o comprimere l'area del contenuto. Se viene espansa, il <xref:System.Windows.Controls.Expander> tenta di visualizzare tutto il contenuto in un'area simile a quello.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controllo delle dimensioni di un controllo Expander in un pannello  
 Se un <xref:System.Windows.Controls.Expander> controllo si trova all'interno di un controllo layout che eredita da <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.StackPanel>, non si specifica un <xref:System.Windows.FrameworkElement.Height%2A> sul <xref:System.Windows.Controls.Expander> quando il <xref:System.Windows.Controls.Expander.ExpandDirection%2A> è impostata su <xref:System.Windows.Controls.ExpandDirection.Down> o <xref:System.Windows.Controls.ExpandDirection.Up>. Analogamente, non si specifica un <xref:System.Windows.FrameworkElement.Width%2A> sul <xref:System.Windows.Controls.Expander> quando il <xref:System.Windows.Controls.Expander.ExpandDirection%2A> è impostata su <xref:System.Windows.Controls.ExpandDirection.Left> o <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 Quando si imposta una dimensione in un <xref:System.Windows.Controls.Expander> controllo nella direzione che viene visualizzato il contenuto espanso, il <xref:System.Windows.Controls.Expander> assume il controllo dell'area che viene utilizzato il contenuto e viene visualizzato un bordo intorno a esso. Il bordo viene visualizzato anche quando il contenuto è compresso. Per impostare le dimensioni dell'area del contenuto espansa, impostare le dimensioni del contenuto del <xref:System.Windows.Controls.Expander>, o se si desidera lo scorrimento lungo funzionalità, il <xref:System.Windows.Controls.ScrollViewer> che racchiude il contenuto.  
  
 Quando un <xref:System.Windows.Controls.Expander> controllo è l'ultimo elemento in un <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] imposta automaticamente il <xref:System.Windows.Controls.Expander> dimensioni uguali all'area rimanente del <xref:System.Windows.Controls.DockPanel>. Per evitare questo comportamento predefinito, impostare il <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> proprietà il <xref:System.Windows.Controls.DockPanel> oggetto `false`, o assicurarsi che il <xref:System.Windows.Controls.Expander> non è l'ultimo elemento in un <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Creazione di contenuto scorrevole  
 Se il contenuto è troppo grande per le dimensioni dell'area di contenuto, è possibile eseguire il wrapping del contenuto di un <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> per fornire contenuto scorrevole. Il <xref:System.Windows.Controls.Expander> controllo non fornisce automaticamente funzionalità di scorrimento. La figura seguente mostra un <xref:System.Windows.Controls.Expander> controllo che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
 **Controllo Expander in un controllo ScrollViewer**  
  
 ![Expander con ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 Quando si inserisce un <xref:System.Windows.Controls.Expander> controllo un <xref:System.Windows.Controls.ScrollViewer>, impostare il <xref:System.Windows.Controls.ScrollViewer> dimensione proprietà che corrisponde alla direzione in cui il <xref:System.Windows.Controls.Expander> contenuto si apre per la dimensione del <xref:System.Windows.Controls.Expander> area del contenuto. Ad esempio, se si imposta la <xref:System.Windows.Controls.Expander.ExpandDirection%2A> proprietà il <xref:System.Windows.Controls.Expander> a <xref:System.Windows.Controls.ExpandDirection.Down> (area di contenuto apre verso il basso), impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà il <xref:System.Windows.Controls.ScrollViewer> controllo sull'altezza richiesta per l'area del contenuto. Se invece viene impostata la dimensione dell'altezza del contenuto, <xref:System.Windows.Controls.ScrollViewer> non riconosce questa impostazione e di conseguenza, non fornisce contenuto scorrevole.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo che ha contenuto complesso e che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Questo esempio viene creato un <xref:System.Windows.Controls.Expander> che è simile alla figura all'inizio di questa sezione.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Uso delle proprietà di allineamento  
 È possibile allineare contenuto impostando il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> proprietà il <xref:System.Windows.Controls.Expander> controllo. Quando si impostano queste proprietà, l'allineamento viene applicato all'intestazione e al contenuto espanso.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
