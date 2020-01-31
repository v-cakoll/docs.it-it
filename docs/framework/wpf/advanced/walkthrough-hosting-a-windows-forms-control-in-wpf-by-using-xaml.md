---
title: Ospitare un controllo Windows Forms in WPF tramite XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: a0a88c39a25e5292365a6447cefdd8f31db5e5c3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744926"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Procedura dettagliata: hosting di controlli Windows Form in WPF tramite XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre numerosi controlli con un insieme di funzionalità completo. Tuttavia, a volte può essere opportuno usare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli nelle pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ad esempio, è possibile che si disponga di un investimento sostanziale nei controlli di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] esistenti o che si disponga di un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] che fornisce funzionalità univoche.  
  
 In questa procedura dettagliata viene illustrato come ospitare un controllo <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> di Windows Forms in una pagina [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [hosting di un controllo Windows Forms in WPF usando l'esempio XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>Prerequisiti  

Per completare la procedura dettagliata, è necessario Visual Studio.  
  
## <a name="hosting-the-windows-forms-control"></a>Hosting del controllo Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Per ospitare il controllo MaskedTextBox  
  
1. Creare un progetto di applicazione WPF denominato `HostingWfInWpfWithXaml`.  
  
2. Aggiungere riferimenti agli assembly indicati di seguito.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Aprire MainWindow. XAML in WPF Designer.  
  
4. Nell'elemento <xref:System.Windows.Window> aggiungere il mapping dello spazio dei nomi seguente. Il mapping dello spazio dei nomi `wf` stabilisce un riferimento all'assembly che contiene il controllo Windows Forms.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. Nell'elemento <xref:System.Windows.Controls.Grid> aggiungere il codice XAML seguente.  
  
     Il controllo <xref:System.Windows.Forms.MaskedTextBox> viene creato come elemento figlio del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controlli Windows Form e controlli WPF equivalenti](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hosting di un controllo Windows Forms in WPF usando l'esempio XAML](https://go.microsoft.com/fwlink/?LinkID=160000)
