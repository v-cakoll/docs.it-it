---
title: 'Procedura dettagliata: Hosting di un controllo Windows Form in WPF tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 10554145de9725bb4cfc655ed88195dce28d739c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032110"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Procedura dettagliata: Hosting di un controllo Windows Form in WPF tramite XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre numerosi controlli con un insieme di funzionalità completo. Tuttavia, può a volte si desidera utilizzare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine. Ad esempio, potrebbe essere un investimento sostanziale nella esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli o si può avere un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che fornisce funzionalità univoche.  
  
 Questa procedura dettagliata illustra come ospitare un controllo Windows Form <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Hosting di controlli Windows Form in WPF tramite XAML esempio](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>Prerequisiti  

Per completare la procedura dettagliata, è necessario Visual Studio.  
  
## <a name="hosting-the-windows-forms-control"></a>Hosting del controllo Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Per ospitare il controllo MaskedTextBox  
  
1. Creare un progetto di applicazione WPF denominato `HostingWfInWpfWithXaml`.  
  
2. Aggiungere riferimenti agli assembly indicati di seguito.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4. Nel <xref:System.Windows.Window> elemento, aggiungere il seguente mapping dello spazio dei nomi. Il `wf` mapping dello spazio dei nomi consente di stabilire un riferimento all'assembly che contiene il controllo Windows Form.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. Nel <xref:System.Windows.Controls.Grid> elemento aggiungere il seguente XAML.  
  
     Il <xref:System.Windows.Forms.MaskedTextBox> viene creato come elemento figlio del controllo di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controlli Windows Form e controlli WPF equivalenti](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hosting di controlli Windows Form in WPF usando l'esempio XAML](https://go.microsoft.com/fwlink/?LinkID=160000)
