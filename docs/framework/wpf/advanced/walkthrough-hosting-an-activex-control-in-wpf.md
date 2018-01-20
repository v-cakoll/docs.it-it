---
title: 'Procedura dettagliata: hosting di un controllo ActiveX in WPF'
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
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b0e85c715db30c6e577980376d25d56238e2835a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Procedura dettagliata: hosting di un controllo ActiveX in WPF
Per migliorare l'interazione con i browser, è possibile utilizzare [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controlli il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su. Questa procedura dettagliata illustra come è possibile ospitare il [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] come controllo in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del progetto.  
  
-   Creazione del controllo ActiveX.  
  
-   Hosting del controllo ActiveX in una pagina WPF.  
  
 Dopo aver completato questa procedura dettagliata, si sarà in grado di utilizzare [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controlli il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]installato nel computer in cui [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] è installato.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
  
#### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto  
  
1.  Creare un progetto di applicazione WPF denominato `HostingAxInWpf`.  
  
2.  Aggiungere un progetto libreria di controlli Windows Form alla soluzione e denominare il progetto `WmpAxLib`.  
  
3.  Nel progetto WmpAxLib, aggiungere un riferimento all'assembly di Windows Media Player, denominato Wmp.  
  
4.  Aprire il **della casella degli strumenti**.  
  
5.  Fare clic del mouse il **della casella degli strumenti**, quindi fare clic su **Scegli elementi**.  
  
6.  Fare clic su di **componenti COM** , selezionare il **Windows Media Player** controllare e quindi fare clic su **OK**.  
  
     Il controllo di Windows Media Player viene aggiunto per il **della casella degli strumenti**.  
  
7.  In Esplora soluzioni fare doppio clic su di **UserControl1** file e quindi fare clic su **rinominare**.  
  
8.  Modificare il nome in `WmpAxControl.vb` o `WmpAxControl.cs`, a seconda del linguaggio.  
  
9. Se viene richiesto di rinominare tutti i riferimenti, fare clic su **Sì**.  
  
## <a name="creating-the-activex-control"></a>Creazione di un controllo ActiveX  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]Genera automaticamente un <xref:System.Windows.Forms.AxHost> classe wrapper per un [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controllare quando il controllo viene aggiunto all'area di progettazione. La procedura seguente viene creato un assembly gestito denominato AxInterop.WMPLib.dll.  
  
#### <a name="to-create-the-activex-control"></a>Per creare il controllo ActiveX  
  
1.  Aprire WmpAxControl. vb o WmpAxControl.cs in Progettazione Windows Form.  
  
2.  Dal **della casella degli strumenti**, aggiungere il controllo di Windows Media Player all'area di progettazione.  
  
3.  Nella finestra Proprietà impostare la proprietà del controllo Windows Media Player <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.  
  
4.  Compilare il progetto di libreria di controllo WmpAxLib.  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hosting del controllo ActiveX in una pagina WPF  
  
#### <a name="to-host-the-activex-control"></a>Per ospitare il controllo ActiveX  
  
1.  Nel progetto HostingAxInWpf, aggiungere un riferimento all'oggetto generato [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] assembly di interoperabilità.  
  
     Questo assembly è denominato AxInterop.WMPLib.dll ed è stato aggiunto alla cartella di Debug del progetto WmpAxLib quando è stato importato il controllo di Windows Media Player.  
  
2.  Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.  
  
3.  Aggiungere un riferimento di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, denominato System.  
  
4.  Aprire MainWindow. XAML in WPF Designer.  
  
5.  Nome di <xref:System.Windows.Controls.Grid> elemento `grid1`.  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  In visualizzazione progettazione o visualizzazione XAML, selezionare il <xref:System.Windows.Window> elemento.  
  
7.  Nella finestra Proprietà fare clic su di **eventi** scheda.  
  
8.  Fare doppio clic su di <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
9. Inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
     Questo codice crea un'istanza del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllare e aggiunge un'istanza di `AxWindowsMediaPlayer` controllo come figlio.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
