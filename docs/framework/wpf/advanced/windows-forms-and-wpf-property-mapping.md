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
ms.openlocfilehash: f2177c65a8b1a1d5ad2f5bad67591e6d98087539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Mapping di proprietà di Windows Form e WPF
Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tecnologie hanno due proprietà simili ma diversi modelli. *Mapping di proprietà* supporta l'interazione tra le due architetture e fornisce le funzionalità seguenti:  
  
-   Consente di eseguire il mapping delle modifiche delle proprietà pertinenti nell'ambiente host per il controllo ospitato o un elemento.  
  
-   Fornisce proprietà di gestione predefinita per il mapping di più comunemente utilizzate.  
  
-   Consente la semplice rimozione, si esegue l'override o l'estensione di proprietà predefinite.  
  
-   Assicura che il valore di proprietà cambia nell'host vengono rilevati automaticamente e convertiti nel controllo ospitato elemento.  
  
> [!NOTE]
>  Gli eventi di modifica delle proprietà non vengono propagati backup del controllo host o della gerarchia di elementi. La conversione delle proprietà non viene eseguita se il valore locale di una proprietà non viene modificato a causa di impostazione diretta, stili, ereditarietà, associazione dati o altri meccanismi che modificano il valore della proprietà.  
  
 Utilizzare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento e <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> proprietà <xref:System.Windows.Forms.Integration.ElementHost> controllo per accedere al mapping di proprietà.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Mapping di proprietà con l'elemento WindowsFormsHost  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento converte predefinito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà loro [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalenti utilizzando la seguente tabella di conversione.  
  
|Hosting di Windows Presentation Foundation|Windows Form|Comportamento di interazione|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> set di elementi di <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del controllo ospitato e <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà del controllo ospitato. Mapping viene eseguito utilizzando le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> un colore a tinta unita, viene convertito e utilizzato per impostare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del controllo ospitato. Il <xref:System.Windows.Forms.Control.BackColor%2A> non è impostata nel controllo ospitato, perché il controllo ospitato può ereditare il valore di <xref:System.Windows.Forms.Control.BackColor%2A> proprietà. **Nota:** il controllo ospitato non supportano la trasparenza. Qualsiasi colore assegnato a <xref:System.Windows.Forms.Control.BackColor%2A> deve essere completamente opaco, con un valore alfa di 0xFF. <br /><br /> -Se <xref:System.Windows.Controls.Control.Background%2A> non è un colore a tinta unita, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo Crea una bitmap dal <xref:System.Windows.Controls.Control.Background%2A> proprietà. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo assegna questa bitmap per il <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà del controllo ospitato. Ciò fornisce un effetto simile alla trasparenza. **Nota:** è possibile eseguire l'override di questo comportamento oppure è possibile rimuovere il <xref:System.Windows.Controls.Control.Background%2A> mapping di proprietà.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Se non è stato riassegnato il mapping predefinito, <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo attraversa la struttura gerarchica dei predecessori finché rileva un predecessore con il relativo <xref:System.Windows.FrameworkElement.Cursor%2A> set di proprietà. Questo valore viene convertito in corrispondente più vicino [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursore.<br /><br /> Se il mapping predefinito per il <xref:System.Windows.FrameworkElement.ForceCursor%2A> proprietà non è stata riassegnata, lo scorrimento si interrompe sul primo predecessore con <xref:System.Windows.FrameworkElement.ForceCursor%2A> impostato su `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> non è mappato.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> esegue il mapping a <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> il controllo ospitato <xref:System.Drawing.Font?displayProperty=nameWithType>|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertita in un oggetto corrispondente <xref:System.Drawing.Font>. Quando una di queste proprietà viene modificato, un nuovo <xref:System.Drawing.Font> viene creato. Per <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> è disabilitato. Per <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> è abilitata.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> il controllo ospitato <xref:System.Drawing.Font?displayProperty=nameWithType>|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertita in un oggetto corrispondente <xref:System.Drawing.Font>. Quando una di queste proprietà viene modificato, un nuovo <xref:System.Drawing.Font> viene creato. Per <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> è abilitata. Per <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> è disabilitato.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|Il set di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà viene convertita in un oggetto corrispondente <xref:System.Drawing.Font>. Quando una di queste proprietà viene modificato, un nuovo <xref:System.Drawing.Font> viene creato. Hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene ridimensionato in base alla dimensione del carattere.<br /><br /> La dimensione del carattere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene espresso come un novantaseiesimo di pollice e in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] come un settantaduesimo di pollice. La conversione corrispondente è:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] dimensioni del carattere = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensione * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|Il <xref:System.Windows.Controls.Control.Foreground%2A> mapping di proprietà viene eseguito utilizzando le regole seguenti:<br /><br /> -Se <xref:System.Windows.Controls.Control.Foreground%2A> è un <xref:System.Windows.Media.SolidColorBrush>, utilizzare <xref:System.Windows.Media.SolidColorBrush.Color%2A> per <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Se <xref:System.Windows.Controls.Control.Foreground%2A> è un <xref:System.Windows.Media.GradientBrush>, usare il colore del <xref:System.Windows.Media.GradientStop> con il valore di offset inferiore per <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Per qualsiasi altro <xref:System.Windows.Media.Brush> digitare, lasciare <xref:System.Windows.Forms.Control.ForeColor%2A> subisce modifiche. Ciò significa che viene utilizzato il valore predefinito.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Quando <xref:System.Windows.UIElement.IsEnabled%2A> è impostata, <xref:System.Windows.Forms.Integration.WindowsFormsHost> set di elementi di <xref:System.Windows.Forms.Control.Enabled%2A> proprietà del controllo ospitato.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Tutti i quattro valori del <xref:System.Windows.Forms.Control.Padding%2A> proprietà del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo vengono impostate sullo stesso <xref:System.Windows.Thickness> valore.<br /><br /> -I valori maggiori di <xref:System.Int32.MaxValue> sono impostate su <xref:System.Int32.MaxValue>.<br />-Valori minore <xref:System.Int32.MinValue> sono impostate su <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> esegue il mapping a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo è visibile. Impostare in modo esplicito il <xref:System.Windows.Forms.Control.Visible%2A> proprietà del controllo ospitato per `false` non è consigliata.<br />-   <xref:System.Windows.Visibility.Collapsed> esegue il mapping a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` o `false`. Hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo non è stato creato e all'area viene compressa.<br />-   <xref:System.Windows.Visibility.Hidden> : L'ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] occupa spazio nel layout del controllo, ma non è visibile. In questo caso, il <xref:System.Windows.Forms.Control.Visible%2A> è impostata su `true`. Impostare in modo esplicito il <xref:System.Windows.Forms.Control.Visible%2A> proprietà del controllo ospitato per `false` non è consigliata.|  
  
 Le proprietà associate degli elementi contenitore sono completamente supportate dal <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
 Per ulteriori informazioni, vedere [procedura dettagliata: Mapping delle proprietà utilizzando l'elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Aggiornamenti alle proprietà padre  
 Le modifiche per la maggior parte delle proprietà padre determinano le notifiche per il controllo figlio hosted. Nell'elenco seguente descrive le proprietà che non causano notifiche quando i valori cambiano.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Ad esempio, se si modifica il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del controllo ospitato non cambia.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Mapping di proprietà con il controllo ElementHost  
 Le proprietà seguenti forniscono notifiche di modifica incorporate. Non chiamare il <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> metodo quando si esegue il mapping di queste proprietà:  
  
-   AutoSize  
  
-   Colore di sfondo  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursore  
  
-   Dock  
  
-   Enabled  
  
-   Tipo di carattere  
  
-   Colore di primo piano  
  
-   Percorso  
  
-   Margini  
  
-   Spaziatura interna  
  
-   Padre  
  
-   Region  
  
-   RightToLeft  
  
-   Dimensione  
  
-   TabIndex  
  
-   TabStop  
  
-   Testo  
  
-   Visible  
  
 Il <xref:System.Windows.Forms.Integration.ElementHost> controllo converte predefinito [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà loro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalenti utilizzando la seguente tabella di conversione.  
  
 Per ulteriori informazioni, vedere [procedura dettagliata: Mapping delle proprietà tramite il controllo ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hosting di Windows Form|Windows Presentation Foundation|Comportamento di interazione|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) dell'elemento ospitato|Impostazione di questa proprietà impone un aggiornamento con un <xref:System.Windows.Media.ImageBrush>. Se il <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> è impostata su `false` (valore predefinito), questo <xref:System.Windows.Media.ImageBrush> si basa sull'aspetto del <xref:System.Windows.Forms.Integration.ElementHost> controllare, tra cui la <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> proprietà e qualsiasi paint associato gestori.<br /><br /> Se il <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> proprietà è impostata su `true`, <xref:System.Windows.Media.ImageBrush> si basa sull'aspetto del <xref:System.Windows.Forms.Integration.ElementHost> padre del controllo, tra cui l'elemento padre <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> , proprietà e qualsiasi paint associato gestori.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) dell'elemento ospitato|Impostando questa proprietà, lo stesso comportamento descritto per il <xref:System.Windows.Forms.Control.BackColor%2A> mapping.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) dell'elemento ospitato|Impostando questa proprietà, lo stesso comportamento descritto per il <xref:System.Windows.Forms.Control.BackColor%2A> mapping.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] standard viene convertito corrispondente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cursore standard. Se il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non è un cursore standard, viene assegnato il valore predefinito.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Quando <xref:System.Windows.Forms.Control.Enabled%2A> è impostata, il <xref:System.Windows.Forms.Integration.ElementHost> controllo imposta il <xref:System.Windows.UIElement.IsEnabled%2A> proprietà dell'elemento ospitato.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|Il <xref:System.Windows.Forms.Control.Font%2A> valore viene convertito in un set corrispondente di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà del carattere.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> elemento ospitato|Se <xref:System.Drawing.Font.Bold%2A> è `true`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Se <xref:System.Drawing.Font.Bold%2A> è `false`, <xref:System.Windows.Controls.Control.FontWeight%2A> viene impostato su <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> elemento ospitato|Se <xref:System.Drawing.Font.Italic%2A> è `true`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Se <xref:System.Drawing.Font.Italic%2A> è `false`, <xref:System.Windows.Controls.Control.FontStyle%2A> viene impostato su <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> elemento ospitato|Si applica solo quando si ospita un <xref:System.Windows.Controls.TextBlock> controllo.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> elemento ospitato|Si applica solo quando si ospita un <xref:System.Windows.Controls.TextBlock> controllo.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> esegue il mapping a <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> esegue il mapping a <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|Il <xref:System.Windows.Forms.Integration.ElementHost> controllo imposta il <xref:System.Windows.UIElement.Visibility%2A> proprietà dell'elemento ospitato utilizzando le regole seguenti:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` esegue il mapping a <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` esegue il mapping a <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Interoperatività di WPF e Windows Form](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [Procedura dettagliata: Mapping di proprietà tramite l'elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [Procedura dettagliata: Mapping delle proprietà tramite il controllo ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
