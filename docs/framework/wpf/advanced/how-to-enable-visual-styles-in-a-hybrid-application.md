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
ms.openlocfilehash: 7aa5208a4f378408a01a08a2f4c9dbf2edfa5243
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776142"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida
In questo argomento viene illustrato come abilitare [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] gli stili di visualizzazione in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.  
  
 Se l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo, la maggior parte delle [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli userà automaticamente gli stili di visualizzazione quando l'applicazione viene eseguita in [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]. Per altre informazioni, vedere [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Per un listato di codice completo delle attività illustrate in questo argomento, vedere [abilitazione stili di visualizzazione in un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Attivazione degli stili di visualizzazione Windows Form  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Per attivare gli stili di visualizzazione Windows Form  
  
1. Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di applicazione denominato `HostingWfWithVisualStyles`.  
  
2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Nella casella degli strumenti, fare doppio clic il <xref:System.Windows.Controls.Grid> icona per posizionare un <xref:System.Windows.Controls.Grid> elemento nell'area di progettazione.  
  
4. Nella finestra Proprietà, impostare i valori del <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> delle proprietà per **Auto**.  
  
5. Nella visualizzazione progettazione o XAML, selezionare il <xref:System.Windows.Window>.  
  
6. Nella finestra Proprietà scegliere il **eventi** scheda.  
  
7. Fare doppio clic il <xref:System.Windows.FrameworkElement.Loaded> evento.
  
8. In MainWindow.xaml.cs o MainWindow. Xaml. vb, inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene disegnato con stili visivi.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Disattivazione degli stili di visualizzazione Windows Form  
 Per disabilitare gli stili di visualizzazione, rimuovere semplicemente la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo).  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Per disattivare gli stili di visualizzazione Windows Form  
  
1. Aprire MainWindow.xaml.vb o MainWindow.xaml.cs nell'editor di codice.  
  
2. Commentare la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo).  
  
3. Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene disegnato con lo stile di sistema predefinito.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [Procedura dettagliata: Hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
