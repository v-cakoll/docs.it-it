---
title: Mapping di proprietà di Windows Form e WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 07e58f87d886212426e25be83f988037549ab642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735243"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Mapping di proprietà di Windows Form e WPF
Le tecnologie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno due modelli di proprietà simili ma diversi. Il *mapping delle proprietà* supporta l'interoperatività tra le due architetture e offre le funzionalità seguenti:  
  
- Consente di eseguire facilmente il mapping delle modifiche delle proprietà rilevanti nell'ambiente host al controllo o all'elemento ospitato.  
  
- Fornisce la gestione predefinita per il mapping delle proprietà utilizzate più di frequente.  
  
- Consente di rimuovere facilmente, eseguire l'override o estendere le proprietà predefinite.  
  
- Garantisce che le modifiche ai valori delle proprietà nell'host vengano automaticamente rilevate e convertite nel controllo o nell'elemento ospitato.  
  
> [!NOTE]
> Gli eventi di modifica delle proprietà non vengono propagati al controllo di hosting o alla gerarchia degli elementi. La conversione di proprietà non viene eseguita se il valore locale di una proprietà non cambia a causa di impostazioni dirette, stili, ereditarietà, data binding o altri meccanismi che modificano il valore della proprietà.  
  
 Utilizzare la proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> e la proprietà <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> sul controllo <xref:System.Windows.Forms.Integration.ElementHost> per accedere al mapping delle proprietà.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Mapping di proprietà con l'elemento WindowsFormsHost  
 L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> converte le proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinite negli equivalenti [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utilizzando la seguente tabella di conversione.  
  
|Hosting di Windows Presentation Foundation|Windows Form|Comportamento di interoperatività|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> imposta la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> del controllo ospitato e la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del controllo ospitato. Il mapping viene eseguito utilizzando le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> è un colore a tinta unita, viene convertito e utilizzato per impostare la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> del controllo ospitato. La proprietà <xref:System.Windows.Forms.Control.BackColor%2A> non è impostata sul controllo ospitato, perché il controllo ospitato può ereditare il valore della proprietà <xref:System.Windows.Forms.Control.BackColor%2A>. **Nota:**  Il controllo ospitato non supporta la trasparenza. Qualsiasi colore assegnato a <xref:System.Windows.Forms.Control.BackColor%2A> deve essere completamente opaco, con un valore alfa di 0xFF. <br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> non è un colore a tinta unita, il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea una bitmap dalla proprietà <xref:System.Windows.Controls.Control.Background%2A>. Il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> assegna questa bitmap alla proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> del controllo ospitato. Ciò fornisce un effetto simile alla trasparenza. **Nota:**  È possibile eseguire l'override di questo comportamento oppure è possibile rimuovere il mapping della proprietà <xref:System.Windows.Controls.Control.Background%2A>.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Se il mapping predefinito non è stato riassegnato, <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo attraversa la gerarchia predecessore fino a quando non trova un predecessore con il relativo set di proprietà <xref:System.Windows.FrameworkElement.Cursor%2A>. Questo valore viene convertito nel cursore di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] corrispondente più vicino.<br /><br /> Se il mapping predefinito per la proprietà <xref:System.Windows.FrameworkElement.ForceCursor%2A> non è stato riassegnato, l'attraversamento viene arrestato sul primo predecessore con <xref:System.Windows.FrameworkElement.ForceCursor%2A> impostato su `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> non è mappato.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> sul <xref:System.Drawing.Font?displayProperty=nameWithType> del controllo ospitato|Il set di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene convertito in un <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene creato un nuovo <xref:System.Drawing.Font>. Per <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> è disabilitato. Per <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> è abilitato.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> sul <xref:System.Drawing.Font?displayProperty=nameWithType> del controllo ospitato|Il set di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene convertito in un <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene creato un nuovo <xref:System.Drawing.Font>. Per <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> è abilitato. Per <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> è disabilitata.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Il set di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene convertito in un <xref:System.Drawing.Font>corrispondente. Quando una di queste proprietà viene modificata, viene creato un nuovo <xref:System.Drawing.Font>. Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato viene ridimensionato in base alle dimensioni del carattere.<br /><br /> Le dimensioni del carattere in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono espresse come un 90 ° sesto di un pollice e in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] come uno di un centimetro di pollice. La conversione corrispondente è:<br /><br /> Dimensioni carattere [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensione carattere * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Il mapping della proprietà <xref:System.Windows.Controls.Control.Foreground%2A> viene eseguito utilizzando le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Foreground%2A> è un <xref:System.Windows.Media.SolidColorBrush>, utilizzare <xref:System.Windows.Media.SolidColorBrush.Color%2A> per <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Se <xref:System.Windows.Controls.Control.Foreground%2A> è un <xref:System.Windows.Media.GradientBrush>, utilizzare il colore del <xref:System.Windows.Media.GradientStop> con il valore di offset più basso per <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Per qualsiasi altro tipo di <xref:System.Windows.Media.Brush>, lasciare <xref:System.Windows.Forms.Control.ForeColor%2A> invariato. Ciò significa che viene utilizzato il valore predefinito.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Quando viene impostato <xref:System.Windows.UIElement.IsEnabled%2A>, <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento imposta la proprietà <xref:System.Windows.Forms.Control.Enabled%2A> nel controllo ospitato.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Tutti e quattro i valori della proprietà <xref:System.Windows.Forms.Control.Padding%2A> nel controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato vengono impostati sullo stesso valore di <xref:System.Windows.Thickness>.<br /><br /> -I valori maggiori di <xref:System.Int32.MaxValue> sono impostati su <xref:System.Int32.MaxValue>.<br />-I valori minori di <xref:System.Int32.MinValue> sono impostati su <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> viene eseguito il mapping a <xref:System.Windows.Forms.Control.Visible%2A> = `true`. Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato è visibile. Non è consigliabile impostare in modo esplicito la proprietà <xref:System.Windows.Forms.Control.Visible%2A> sul controllo ospitato su `false`.<br />-   <xref:System.Windows.Visibility.Collapsed> viene eseguito il mapping a <xref:System.Windows.Forms.Control.Visible%2A> = `true` o `false`. Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato non viene disegnato e la relativa area è compressa.<br />-   <xref:System.Windows.Visibility.Hidden>: il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato occupa spazio nel layout, ma non è visibile. In questo caso, la proprietà <xref:System.Windows.Forms.Control.Visible%2A> è impostata su `true`. Non è consigliabile impostare in modo esplicito la proprietà <xref:System.Windows.Forms.Control.Visible%2A> sul controllo ospitato su `false`.|  
  
 Le proprietà associate sugli elementi del contenitore sono completamente supportate dall'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 Per ulteriori informazioni, vedere [procedura dettagliata: mapping di proprietà tramite l'elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Aggiornamenti alle proprietà padre  
 Le modifiche apportate alla maggior parte delle proprietà padre generano notifiche per il controllo figlio ospitato. Nell'elenco seguente vengono descritte le proprietà che non provocano notifiche quando cambiano i valori.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Se ad esempio si modifica il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> del controllo ospitato non viene modificata.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Mapping di proprietà con il controllo ElementHost  
 Le proprietà seguenti forniscono una notifica di modifica incorporata. Non chiamare il metodo <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> quando si esegue il mapping di queste proprietà:  
  
- Ridimensiona automaticamente  
  
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
  
- Percorso  
  
- Margine  
  
- Spaziatura interna  
  
- Padre  
  
- Region  
  
- RightToLeft  
  
- Dimensioni  
  
- TabIndex  
  
- TabStop  
  
- Testo  
  
- Visibile  
  
 Il controllo <xref:System.Windows.Forms.Integration.ElementHost> converte le proprietà di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] predefinite negli equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzando la seguente tabella di conversione.  
  
 Per ulteriori informazioni, vedere [procedura dettagliata: mapping delle proprietà tramite il controllo ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hosting di Windows Forms|Windows Presentation Foundation|Comportamento di interoperatività|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà impone un ridisegno con un <xref:System.Windows.Media.ImageBrush>. Se la proprietà <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> è impostata su `false` (valore predefinito), questo <xref:System.Windows.Media.ImageBrush> si basa sull'aspetto del controllo <xref:System.Windows.Forms.Integration.ElementHost>, incluse le proprietà <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> e tutti i gestori di disegno collegati.<br /><br /> Se la proprietà <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> è impostata su `true`, il <xref:System.Windows.Media.ImageBrush> si basa sull'aspetto dell'elemento padre del controllo <xref:System.Windows.Forms.Integration.ElementHost>, incluse le proprietà <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> e tutti i gestori di disegno associati del padre.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà determina lo stesso comportamento descritto per il mapping del <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) nell'elemento Hosted|L'impostazione di questa proprietà determina lo stesso comportamento descritto per il mapping del <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Il cursore [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] standard viene convertito nel cursore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] standard corrispondente. Se il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non è un cursore standard, viene assegnato il valore predefinito.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Quando viene impostato <xref:System.Windows.Forms.Control.Enabled%2A>, il controllo <xref:System.Windows.Forms.Integration.ElementHost> imposta la proprietà <xref:System.Windows.UIElement.IsEnabled%2A> sull'elemento Hosted.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Il valore <xref:System.Windows.Forms.Control.Font%2A> viene convertito in un set di proprietà del tipo di carattere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] corrispondente.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> sull'elemento Hosted|Se <xref:System.Drawing.Font.Bold%2A> è `true`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Se <xref:System.Drawing.Font.Bold%2A> è `false`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> sull'elemento Hosted|Se <xref:System.Drawing.Font.Italic%2A> è `true`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Se <xref:System.Drawing.Font.Italic%2A> è `false`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> sull'elemento Hosted|Si applica solo quando si ospita un controllo <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> sull'elemento Hosted|Si applica solo quando si ospita un controllo <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> esegue il mapping a <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> esegue il mapping a <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Il controllo <xref:System.Windows.Forms.Integration.ElementHost> imposta la proprietà <xref:System.Windows.UIElement.Visibility%2A> sull'elemento Hosted utilizzando le regole seguenti:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` esegue il mapping a <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` esegue il mapping a <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Interoperatività di WPF e Windows Form](wpf-and-windows-forms-interoperation.md)
- [Procedura dettagliata: Mapping di proprietà tramite l'elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Procedura dettagliata: Mapping delle proprietà tramite il controllo ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
