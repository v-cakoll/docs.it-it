---
title: "Procedura: Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f882d62152d0116d5bff3bcd604f04c249443a94
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396669"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Procedura: Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che restituisce un Windows Presentation Foundation (WPF) in un host applicazione WPF autonoma.  
  
 Il componente aggiuntivo restituisce un'interfaccia utente che è un controllo utente WPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione WPF autonoma ospita il componente aggiuntivo e visualizza il controllo utente (restituito dal componente aggiuntivo) come il contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 Questo esempio illustra le estensioni WPF per il modello di componente aggiuntivo di .NET Framework che abilitare questo scenario e si presuppone quanto segue:  
  
-   Conoscenza del .NET Framework-in modello, tra cui sviluppo di pipeline, componenti aggiuntivi e host. Se non si ha familiarità con questi concetti, vedere [componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere [procedura dettagliata: Creazione di un'applicazione estendibile](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Conoscenza delle estensioni di WPF per il modello .NET Framework con componente aggiuntivo che è disponibile qui: [Cenni preliminari sui componenti aggiuntivi WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che restituisce una UI WPF richiede codice specifico per ogni segmento di pipeline, il componente aggiuntivo e l'applicazione host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Un metodo deve essere definito dal contratto per la restituzione di un'interfaccia utente e il relativo valore restituito deve essere di tipo <xref:System.AddIn.Contract.INativeHandleContract>. Detto è dimostrato dal `GetAddInUI` metodo del `IWPFAddInContract` dei contratti nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo implementa il [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornite come sottoclassi di <xref:System.Windows.FrameworkElement>, il metodo nella visualizzazione componente aggiuntivo che è correlata a `IWPFAddInView.GetAddInUI` deve restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione componente aggiuntivo del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Il metodo del contratto restituisce un <xref:System.AddIn.Contract.INativeHandleContract>, ma il componente aggiuntivo restituisce un' <xref:System.Windows.FrameworkElement> (come specificato dalla visualizzazione componente aggiuntivo). Di conseguenza, il <xref:System.Windows.FrameworkElement> deve essere convertito in un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento. Questa operazione viene eseguita dall'adattatore lato componente aggiuntivo tramite la chiamata <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 Poiché l'applicazione host visualizzerà un <xref:System.Windows.FrameworkElement>, il metodo nella visualizzazione host correlata a `IWPFAddInHostView.GetAddInUI` devono restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione host del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Il metodo del contratto restituisce un <xref:System.AddIn.Contract.INativeHandleContract>, ma l'applicazione host prevede un <xref:System.Windows.FrameworkElement> (come specificato dalla visualizzazione host). Di conseguenza, il <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento. Questa operazione viene eseguita dall'adattatore lato host chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Adattatore lato componente aggiuntivo e la visualizzazione componente aggiuntivo creato, il componente aggiuntivo (`WPFAddIn1.AddIn`) deve implementare il `IWPFAddInView.GetAddInUI` per restituire una <xref:System.Windows.FrameworkElement> oggetto (un <xref:System.Windows.Controls.UserControl> in questo esempio). L'implementazione del <xref:System.Windows.Controls.UserControl>, `AddInUI`, viene visualizzato per il codice seguente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 L'implementazione del `IWPFAddInView.GetAddInUI` per il componente aggiuntivo deve semplicemente restituire una nuova istanza della `AddInUI`, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Adattatore lato host e la visualizzazione host creato, l'applicazione host può utilizzare il modello di componente aggiuntivo di .NET Framework per aprire la pipeline, acquisire una visualizzazione host del componente aggiuntivo e chiamare il `IWPFAddInHostView.GetAddInUI` (metodo). Il codice riportato di seguito illustra i diversi passaggi.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vedere anche  
 [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))  
 [Cenni preliminari sui componenti aggiuntivi di WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
