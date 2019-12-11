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
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960119"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida
In questo argomento viene illustrato come abilitare gli stili di visualizzazione in un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato in un'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Se l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, la maggior parte dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utilizzerà automaticamente gli stili di visualizzazione. Per altre informazioni, vedere [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Per un listato di codice completo delle attività illustrate in questo argomento, vedere l'articolo relativo all' [Abilitazione degli stili di visualizzazione in un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Attivazione degli stili di visualizzazione Windows Form  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Per attivare gli stili di visualizzazione Windows Form  
  
1. Creare un progetto di applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominato `HostingWfWithVisualStyles`.  
  
2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Nella casella degli strumenti fare doppio clic sull'icona <xref:System.Windows.Controls.Grid> per inserire un elemento <xref:System.Windows.Controls.Grid> nell'area di progettazione.  
  
4. Nella Finestra Proprietà impostare i valori delle proprietà <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> su **auto**.  
  
5. Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare il <xref:System.Windows.Window>.  
  
6. Nella Finestra Proprietà fare clic sulla scheda **eventi** .  
  
7. Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.
  
8. In MainWindow. XAML. vb o MainWindow.xaml.cs inserire il codice seguente per gestire l'evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene disegnato con stili di visualizzazione.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Disattivazione degli stili di visualizzazione Windows Form  
 Per disabilitare gli stili di visualizzazione, è sufficiente rimuovere la chiamata al metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Per disattivare gli stili di visualizzazione Windows Form  
  
1. Aprire MainWindow.xaml.vb o MainWindow.xaml.cs nell'editor di codice.  
  
2. Impostare come commento la chiamata al metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
3. Premere F5 per compilare ed eseguire l'applicazione.  
  
     Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene disegnato con lo stile di sistema predefinito.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
