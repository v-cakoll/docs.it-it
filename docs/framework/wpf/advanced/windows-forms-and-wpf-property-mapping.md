---
title: Mapping di proprietà di Windows Form e WPF
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: ae4a97bc96a4f9e93942b4995f488c427fda3134
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917505"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Mapping di proprietà di Windows Form e WPF
Le [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tecnologie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e hanno due modelli di proprietà simili ma diversi. Il *mapping delle proprietà* supporta l'interoperatività tra le due architetture e offre le funzionalità seguenti:  
  
- Consente di eseguire facilmente il mapping delle modifiche delle proprietà rilevanti nell'ambiente host al controllo o all'elemento ospitato.  
  
- Fornisce la gestione predefinita per il mapping delle proprietà utilizzate più di frequente.  
  
- Consente di rimuovere facilmente, eseguire l'override o estendere le proprietà predefinite.  
  
- Garantisce che le modifiche ai valori delle proprietà nell'host vengano automaticamente rilevate e convertite nel controllo o nell'elemento ospitato.  
  
> [!NOTE]
> Gli eventi di modifica delle proprietà non vengono propagati al controllo di hosting o alla gerarchia degli elementi. La conversione di proprietà non viene eseguita se il valore locale di una proprietà non cambia a causa di impostazioni dirette, stili, ereditarietà, data binding o altri meccanismi che modificano il valore della proprietà.  
  
 Utilizzare la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> proprietà sull'elemento e la <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà sul <xref:System.Windows.Forms.Integration.ElementHost> controllo per accedere al mapping delle proprietà.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Mapping di proprietà con l'elemento WindowsFormsHost  
 L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento converte le proprietà predefinite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] negli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalenti utilizzando la seguente tabella di conversione.  
  
|Hosting di Windows Presentation Foundation|Windows Form|Comportamento di interoperatività|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento imposta la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del controllo ospitato e la <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà del controllo ospitato. Il mapping viene eseguito utilizzando le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> è un colore a tinta unita, viene convertito e utilizzato per <xref:System.Windows.Forms.Control.BackColor%2A> impostare la proprietà del controllo ospitato. La <xref:System.Windows.Forms.Control.BackColor%2A> proprietà non è impostata sul controllo ospitato, perché il controllo ospitato può ereditare il valore <xref:System.Windows.Forms.Control.BackColor%2A> della proprietà. **Nota:**  Il controllo ospitato non supporta la trasparenza. Qualsiasi colore assegnato a <xref:System.Windows.Forms.Control.BackColor%2A> deve essere completamente opaco, con un valore alfa di 0xFF. <br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> non è un colore a tinta <xref:System.Windows.Forms.Integration.WindowsFormsHost> unita, il controllo <xref:System.Windows.Controls.Control.Background%2A> crea una bitmap dalla proprietà. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo Assegna questa bitmap <xref:System.Windows.Forms.Control.BackgroundImage%2A> alla proprietà del controllo ospitato. Ciò fornisce un effetto simile alla trasparenza. **Nota:**  È possibile eseguire l'override di questo comportamento oppure è <xref:System.Windows.Controls.Control.Background%2A> possibile rimuovere il mapping delle proprietà.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Se il mapping predefinito non è stato riassegnato, <xref:System.Windows.Forms.Integration.WindowsFormsHost> il controllo attraversa la gerarchia predecessore fino a quando non trova un <xref:System.Windows.FrameworkElement.Cursor%2A> predecessore con la relativa proprietà impostata. Questo valore viene convertito nel cursore corrispondente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] più vicino.<br /><br /> Se il mapping predefinito per la <xref:System.Windows.FrameworkElement.ForceCursor%2A> proprietà non è stato riassegnato, l'attraversamento viene arrestato sul primo predecessore <xref:System.Windows.FrameworkElement.ForceCursor%2A> con impostato `true`su.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>esegue il <xref:System.Windows.Forms.RightToLeft.No>mapping a.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>esegue il <xref:System.Windows.Forms.RightToLeft.Yes>mapping a.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>non è mappato.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>esegue il <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>mapping a.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>nell'oggetto del controllo ospitato<xref:System.Drawing.Font?displayProperty=nameWithType>|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertito in un oggetto <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene <xref:System.Drawing.Font> creato un nuovo oggetto. Per <xref:System.Windows.FontStyles.Normal%2A> :<xref:System.Drawing.FontStyle.Italic> è disabilitato. Per <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A> :<xref:System.Drawing.FontStyle.Italic> è abilitato.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>nell'oggetto del controllo ospitato<xref:System.Drawing.Font?displayProperty=nameWithType>|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertito in un oggetto <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene <xref:System.Drawing.Font> creato un nuovo oggetto. Per <xref:System.Windows.FontWeights.Black%2A> <xref:System.Windows.FontWeights.Bold%2A> ,<xref:System.Windows.FontWeights.ExtraBold%2A>,,, ,<xref:System.Windows.FontWeights.Medium%2A>,o: è<xref:System.Drawing.FontStyle.Bold> abilitato. <xref:System.Windows.FontWeights.SemiBold%2A> <xref:System.Windows.FontWeights.Heavy%2A> <xref:System.Windows.FontWeights.DemiBold%2A> <xref:System.Windows.FontWeights.UltraBold%2A> Per <xref:System.Windows.FontWeights.ExtraLight%2A> ,<xref:System.Windows.FontWeights.Light%2A>,, ,<xref:System.Windows.FontWeights.UltraLight%2A>o: è<xref:System.Drawing.FontStyle.Bold> disabilitato. <xref:System.Windows.FontWeights.Thin%2A> <xref:System.Windows.FontWeights.Normal%2A> <xref:System.Windows.FontWeights.Regular%2A>|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertito in un oggetto <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene <xref:System.Drawing.Font> creato un nuovo oggetto. Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contenuto viene ridimensionato in base alle dimensioni del carattere.<br /><br /> Le dimensioni del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carattere in sono espresse come un 90 ° sesto di pollice e in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] come un valore di un centimetro di pollice. La conversione corrispondente è:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Dimensioni carattere = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensioni carattere * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Per <xref:System.Windows.Controls.Control.Foreground%2A> eseguire il mapping delle proprietà, è necessario utilizzare le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush.Color%2A> è, usare per<xref:System.Windows.Forms.Control.ForeColor%2A>. <xref:System.Windows.Media.SolidColorBrush><br />-Se <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Forms.Control.ForeColor%2A>è, usare il colore di conilvaloredioffsetpiùbassoper.<xref:System.Windows.Media.GradientStop> <xref:System.Windows.Media.GradientBrush><br />-Per qualsiasi altro <xref:System.Windows.Media.Brush> tipo, lasciare <xref:System.Windows.Forms.Control.ForeColor%2A> invariato. Ciò significa che viene utilizzato il valore predefinito.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Quando <xref:System.Windows.UIElement.IsEnabled%2A> è impostato, <xref:System.Windows.Forms.Integration.WindowsFormsHost> element imposta la <xref:System.Windows.Forms.Control.Enabled%2A> proprietà nel controllo ospitato.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Tutti e quattro i valori <xref:System.Windows.Forms.Control.Padding%2A> della proprietà nel controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato sono impostati sullo stesso <xref:System.Windows.Thickness> valore.<br /><br /> -I valori maggiori <xref:System.Int32.MaxValue> di vengono impostati <xref:System.Int32.MaxValue>su.<br />-I valori minori <xref:System.Int32.MinValue> di vengono impostati <xref:System.Int32.MinValue>su.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>esegue il <xref:System.Windows.Forms.Control.Visible%2A>mapping a.  =  `true` Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato è visibile. Non `false` è consigliabile impostare <xref:System.Windows.Forms.Control.Visible%2A> in modo esplicito la proprietà nel controllo ospitato su.<br />-   <xref:System.Windows.Visibility.Collapsed>esegue il <xref:System.Windows.Forms.Control.Visible%2A> mapping a  =  `true` o .`false` Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato non viene disegnato e la relativa area è compressa.<br />-   <xref:System.Windows.Visibility.Hidden>: Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato occupa spazio nel layout, ma non è visibile. In questo caso, la <xref:System.Windows.Forms.Control.Visible%2A> proprietà viene impostata su `true`. Non `false` è consigliabile impostare <xref:System.Windows.Forms.Control.Visible%2A> in modo esplicito la proprietà nel controllo ospitato su.|  
  
 Le proprietà associate sugli elementi del <xref:System.Windows.Forms.Integration.WindowsFormsHost> contenitore sono completamente supportate dall'elemento.  
  
 Per altre informazioni, vedere [Procedura dettagliata: Mapping delle proprietà tramite l'elemento](walkthrough-mapping-properties-using-the-windowsformshost-element.md)WindowsFormsHost.  
  
## <a name="updates-to-parent-properties"></a>Aggiornamenti alle proprietà padre  
 Le modifiche apportate alla maggior parte delle proprietà padre generano notifiche per il controllo figlio ospitato. Nell'elenco seguente vengono descritte le proprietà che non provocano notifiche quando cambiano i valori.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Se ad esempio si modifica il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento, la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del controllo ospitato non viene modificata.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Mapping di proprietà con il controllo ElementHost  
 Le proprietà seguenti forniscono una notifica di modifica incorporata. Non chiamare il metodo <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> quando si esegue il mapping di queste proprietà:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursore  
  
- Dock  
  
- Enabled  
  
- Carattere  
  
- ForeColor  
  
- Location  
  
- Margini  
  
- Spaziatura interna  
  
- Padre  
  
- Region  
  
- RightToLeft  
  
- Dimensione  
  
- TabIndex  
  
- TabStop  
  
- Text  
  
- Visibile  
  
 Il <xref:System.Windows.Forms.Integration.ElementHost> controllo converte le proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinite [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] negli equivalenti utilizzando la seguente tabella di conversione.  
  
 Per altre informazioni, vedere [Procedura dettagliata: Mapping delle proprietà tramite il controllo](walkthrough-mapping-properties-using-the-elementhost-control.md)ElementHost.  
  
|Hosting di Windows Forms|Windows Presentation Foundation|Comportamento di interoperatività|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà impone un ridisegno con <xref:System.Windows.Media.ImageBrush>un oggetto. Se la <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> proprietà è `false` impostata su (valore <xref:System.Windows.Media.ImageBrush> predefinito), si basa sull'aspetto del <xref:System.Windows.Forms.Integration.ElementHost> controllo, incluse <xref:System.Windows.Forms.Control.BackColor%2A>le proprietà, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> e qualsiasi disegno associato gestori.<br /><br /> Se la <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> proprietà è `true`impostata su, l' <xref:System.Windows.Media.ImageBrush> oggetto è basato sull'aspetto dell' <xref:System.Windows.Forms.Integration.ElementHost> elemento padre del controllo, incluse le proprietà <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> , e qualsiasi disegno associato del padre. gestori.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà determina lo stesso comportamento descritto <xref:System.Windows.Forms.Control.BackColor%2A> per il mapping.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà determina lo stesso comportamento descritto <xref:System.Windows.Forms.Control.BackColor%2A> per il mapping.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursore standard viene convertito nel cursore standard [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente. Se non [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] è un cursore standard, viene assegnato il valore predefinito.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Quando <xref:System.Windows.Forms.Control.Enabled%2A> è impostato, il <xref:System.Windows.Forms.Integration.ElementHost> controllo imposta la <xref:System.Windows.UIElement.IsEnabled%2A> proprietà nell'elemento Hosted.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Il <xref:System.Windows.Forms.Control.Font%2A> valore viene convertito in un set corrispondente di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà del tipo di carattere.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>nell'elemento Hosted|Se <xref:System.Drawing.Font.Bold%2A> è `true`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Se <xref:System.Drawing.Font.Bold%2A> è `false`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>nell'elemento Hosted|Se <xref:System.Drawing.Font.Italic%2A> è `true`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Se <xref:System.Drawing.Font.Italic%2A> è `false`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>nell'elemento Hosted|Si applica solo quando si <xref:System.Windows.Controls.TextBlock> ospita un controllo.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>nell'elemento Hosted|Si applica solo quando si <xref:System.Windows.Controls.TextBlock> ospita un controllo.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>esegue il <xref:System.Windows.FlowDirection.LeftToRight>mapping a.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>esegue il <xref:System.Windows.FlowDirection.RightToLeft>mapping a.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Il <xref:System.Windows.Forms.Integration.ElementHost> controllo imposta la <xref:System.Windows.UIElement.Visibility%2A> proprietà nell'elemento Hosted usando le regole seguenti:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`esegue il <xref:System.Windows.Visibility.Visible>mapping a.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`esegue il <xref:System.Windows.Visibility.Hidden>mapping a.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Interoperatività di WPF e Windows Form](wpf-and-windows-forms-interoperation.md)
- [Procedura dettagliata: Mapping di proprietà tramite l'elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Procedura dettagliata: Mapping delle proprietà tramite il controllo ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
