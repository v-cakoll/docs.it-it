---
title: 'Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form'
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
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5af705509d30f7dfd50ade0c07aca242deff4dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form
Questa procedura dettagliata illustra come creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito controllare e inserirlo in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] form e controlli tramite il <xref:System.Windows.Forms.Integration.ElementHost> controllo.  
  
 In questa procedura dettagliata, verrà implementata una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> che contiene due controlli figlio. Il <xref:System.Windows.Controls.UserControl> consente di visualizzare un cono tridimensionale (3D). Il rendering di oggetti 3D è molto più semplice con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. È pertanto utile per ospitare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> classe per creare la grafica 3D in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
-   Creazione del progetto host Windows Form.  
  
-   Hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo composito WPF 3D in Windows Form](http://go.microsoft.com/fwlink/?LinkID=160001).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a>Creazione di UserControl  
  
#### <a name="to-create-the-usercontrol"></a>Per creare il controllo UserControl  
  
1.  Creare un progetto libreria di controlli utente WPF denominato `HostingWpfUserControlInWf`.  
  
2.  Aprire UserControl1. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Sostituire il codice generato con il codice seguente.  
  
     Questo codice definisce un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio. Il primo controllo figlio è un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> controllo; il secondo è un <xref:System.Windows.Controls.Viewport3D> controllo che visualizza un cono 3D.  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a>Creazione del progetto host Windows Form  
  
#### <a name="to-create-the-host-project"></a>Per creare il progetto host  
  
1.  Aggiungere un progetto di applicazione Windows denominato `WpfUserControlHost` alla soluzione. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  In Esplora soluzioni aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.  
  
3.  Aggiungere riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.  
  
5.  In Esplora soluzioni, impostare il `WpfUserControlHost` progetto come progetto di avvio.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a>Hosting di Windows Presentation Foundation UserControl  
  
#### <a name="to-host-the-usercontrol"></a>Per ospitare il controllo UserControl  
  
1.  In Progettazione Windows Form, aprire Form1.  
  
2.  Nella finestra Proprietà fare clic su **eventi**, quindi fare doppio clic sul <xref:System.Windows.Forms.Form.Load> creare un gestore dell'evento.  
  
     Verrà aperto l'Editor di codice appena generato `Form1_Load` gestore dell'evento.  
  
3.  Sostituire il codice in Form1. cs con il codice seguente.  
  
     Il `Form1_Load` gestore eventi crea un'istanza di `UserControl1` e aggiunge OILT il <xref:System.Windows.Forms.Integration.ElementHost> insieme di controlli figlio del controllo. Il <xref:System.Windows.Forms.Integration.ElementHost> controllo viene aggiunto alla raccolta del form dei controlli figlio.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Hosting di un controllo composito WPF in Windows Form](http://go.microsoft.com/fwlink/?LinkID=160001)
