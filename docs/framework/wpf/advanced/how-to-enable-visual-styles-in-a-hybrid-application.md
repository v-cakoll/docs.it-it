---
title: "Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 2d714ad020f2f7b6a6343c8f8e3901b59dfd23a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida
In questo argomento viene illustrato come abilitare [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] gli stili di visualizzazione in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.  
  
 Se l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo), la maggior parte del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli utilizzerà automaticamente gli stili di visualizzazione quando l'applicazione è in esecuzione [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]. Per ulteriori informazioni, vedere [il Rendering di controlli con stili visivi](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Per un elenco di codice completo delle attività illustrate in questo argomento, vedere [abilitare gli stili di visualizzazione in un'applicazione ibrida](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Attivazione degli stili di visualizzazione Windows Form  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Per attivare gli stili di visualizzazione Windows Form  
  
1.  Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di applicazione denominato `HostingWfWithVisualStyles`.  
  
2.  In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Nella casella degli strumenti, fare doppio clic su di <xref:System.Windows.Controls.Grid> icona per inserire un <xref:System.Windows.Controls.Grid> elemento nell'area di progettazione.  
  
4.  Nella finestra Proprietà, impostare i valori del <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> proprietà **Auto**.  
  
5.  In visualizzazione progettazione o visualizzazione XAML, selezionare il <xref:System.Windows.Window>.  
  
6.  Nella finestra Proprietà fare clic su di **eventi** scheda.  
  
7.  Fare doppio clic su di <xref:System.Windows.FrameworkElement.Loaded> evento.
  
8.  In MainWindow.Xaml.cs o MainWindow, inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene disegnato con stili visivi.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Disattivazione degli stili di visualizzazione Windows Form  
 Per disabilitare gli stili di visualizzazione, rimuovere semplicemente la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Per disattivare gli stili di visualizzazione Windows Form  
  
1.  Aprire MainWindow.xaml.vb o MainWindow.xaml.cs nell'editor di codice.  
  
2.  Commentare la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo.  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene disegnato un controllo con lo stile di sistema predefinito.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Rendering dei controlli con stili visivi](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [Procedura dettagliata: hosting di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
