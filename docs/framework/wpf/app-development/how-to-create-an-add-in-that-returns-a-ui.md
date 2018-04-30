---
title: "Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e89cb9d0c8e5a26703ff5f56a3af10d7fe9923f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che restituisce un Windows Presentation Foundation (WPF) in un host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione autonoma.  
  
 Il componente aggiuntivo che restituisce un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vale a dire un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] controllo utente. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione autonoma ospita il componente aggiuntivo e lo visualizza il controllo utente, restituito dal componente aggiuntivo, il contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio viene evidenziato il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estensioni per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aggiuntivo modello abilitare questo scenario, si presuppone quanto segue:  
  
-   Conoscere il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello del componente aggiuntivo, tra cui sviluppo di pipeline, componenti aggiuntivi e host. Se non si ha familiarità con questi concetti, vedere [aggiuntivi ed estensibilità](../../../../docs/framework/add-ins/index.md). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere [procedura dettagliata: creazione di un'applicazione estensibile](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Conoscenza del [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estensioni per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello del componente aggiuntivo, che è disponibili qui: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che restituisce un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiede codice specifico per ogni segmento della pipeline, il componente aggiuntivo e l'applicazione host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Un metodo deve essere definito dal contratto per la restituzione di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], e il relativo valore restituito deve essere di tipo <xref:System.AddIn.Contract.INativeHandleContract>. Questo viene dimostrato la `GetAddInUI` metodo il `IWPFAddInContract` contratto nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo implementa il [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornite come sottoclassi di <xref:System.Windows.FrameworkElement>, il metodo nella vista è correlata a `IWPFAddInView.GetAddInUI` deve restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione componente aggiuntivo del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Il metodo del contratto restituisce un <xref:System.AddIn.Contract.INativeHandleContract>, ma il componente aggiuntivo restituisce un <xref:System.Windows.FrameworkElement> (come specificato da parte della vista del componente aggiuntivo). Di conseguenza, il <xref:System.Windows.FrameworkElement> deve essere convertito in un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento. Questa operazione viene eseguita dall'adapter sul lato componente-chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 Poiché l'applicazione host visualizzerà un <xref:System.Windows.FrameworkElement>, il metodo nella visualizzazione host correlata a `IWPFAddInHostView.GetAddInUI` deve restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione host del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Il metodo del contratto restituisce un <xref:System.AddIn.Contract.INativeHandleContract>, ma l'applicazione host prevede un <xref:System.Windows.FrameworkElement> (come specificato dalla visualizzazione host). Di conseguenza, il <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento. Questa operazione viene eseguita dall'adapter sul lato host chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Con il lato del componente-scheda aggiuntivo creato e la visualizzazione, il componente aggiuntivo (`WPFAddIn1.AddIn`) deve implementare il `IWPFAddInView.GetAddInUI` per restituire un <xref:System.Windows.FrameworkElement> oggetto (un <xref:System.Windows.Controls.UserControl> in questo esempio). L'implementazione del <xref:System.Windows.Controls.UserControl>, `AddInUI`, viene visualizzato per il codice seguente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 L'implementazione del `IWPFAddInView.GetAddInUI` da parte del componente aggiuntivo deve semplicemente restituire una nuova istanza della `AddInUI`, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Con l'adattatore host sul lato host creato e la visualizzazione, è possibile utilizzare l'applicazione host di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello di componente aggiuntivo per aprire la pipeline, acquisire una visualizzazione host del componente aggiuntivo e chiamata di `IWPFAddInHostView.GetAddInUI` (metodo). Il codice riportato di seguito illustra i diversi passaggi.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vedere anche  
 [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md)  
 [Cenni preliminari sui componenti aggiuntivi di WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
