---
title: 'Procedura dettagliata: hosting di controlli Windows Form in WPF tramite XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5fe01b4ef9aebe697138e925935b73bd4770e86a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Procedura dettagliata: hosting di controlli Windows Form in WPF tramite XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre numerosi controlli con un insieme di funzionalità completo. Tuttavia, può talvolta si desidera utilizzare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai controlli del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine. Ad esempio, è possibile un investimento sostanziale esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli o si può disporre di un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che fornisce funzionalità univoche.  
  
 Questa procedura dettagliata viene illustrato come ospitare un controllo Windows Form <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo Windows Form in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="hosting-the-windows-forms-control"></a>Hosting del controllo Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Per ospitare il controllo MaskedTextBox  
  
1.  Creare un progetto di applicazione WPF denominato `HostingWfInWpfWithXaml`.  
  
2.  Aggiungere riferimenti agli assembly indicati di seguito.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  Nel <xref:System.Windows.Window> elemento, aggiungere il seguente mapping dello spazio dei nomi. Il `wf` mapping dello spazio dei nomi stabilisce un riferimento all'assembly che contiene il [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nel <xref:System.Windows.Controls.Grid> elemento aggiungere il codice XAML seguente.  
  
     Il <xref:System.Windows.Forms.MaskedTextBox> controllo viene creato come elemento figlio di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettagliata: hosting di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Controlli Windows Form e controlli WPF equivalenti](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [Hosting di un controllo Windows Form in WPF tramite XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000)
