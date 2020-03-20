---
title: "Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174589"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che restituisce un Windows Presentation Foundation (WPF) a un'applicazione autonoma WPF host.  
  
 Il componente aggiuntivo restituisce un'interfaccia utente che è un controllo utente WPFWPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione autonoma WPFWPF ospita il componente aggiuntivo e visualizza il controllo utente (restituito dal componente aggiuntivo) come contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio vengono evidenziate le estensioni WPF per il modello di componente aggiuntivo .NET Framework.NET Framework che abilitano questo scenario e presuppone quanto segue:  
  
- Conoscenza del modello di componente aggiuntivo .NET Framework, inclusi pipeline, componente aggiuntivo e sviluppo host. Se non si ha familiarità con questi concetti, vedere [Componenti aggiuntivi ed estensibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere procedura dettagliata: creazione di [un'applicazione estensibile.](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))  
  
- Conoscenza delle estensioni WPF per il modello di componente aggiuntivo .NET Framework, disponibile qui: [Cenni preliminari](wpf-add-ins-overview.md)sui componenti aggiuntivi WPF .  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che restituisce un'interfaccia utente WPFWPF richiede codice specifico per ogni segmento di pipeline, il componente aggiuntivo e l'applicazione host.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Un metodo deve essere definito dal contratto per restituire un'interfaccia <xref:System.AddIn.Contract.INativeHandleContract>utente e il relativo valore restituito deve essere di tipo . Ciò è dimostrato `GetAddInUI` dal `IWPFAddInContract` metodo del contratto nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo implementa le interfacce <xref:System.Windows.FrameworkElement>utente fornite come sottoclassi di , `IWPFAddInView.GetAddInUI` il metodo nella <xref:System.Windows.FrameworkElement>visualizzazione del componente aggiuntivo correlato deve restituire un valore di tipo . Il codice seguente illustra la visualizzazione componente aggiuntivo del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Il metodo del <xref:System.AddIn.Contract.INativeHandleContract>contratto restituisce un <xref:System.Windows.FrameworkElement> , ma il componente aggiuntivo restituisce un oggetto (come specificato dalla visualizzazione del componente aggiuntivo). Di conseguenza, <xref:System.Windows.FrameworkElement> l'oggetto <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un prima di attraversare il limite di isolamento. Questa operazione viene eseguita dall'adattatore <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>sul lato componente aggiuntivo chiamando , come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 Poiché nell'applicazione <xref:System.Windows.FrameworkElement>host verrà visualizzato un oggetto , `IWPFAddInHostView.GetAddInUI` il metodo nella <xref:System.Windows.FrameworkElement>visualizzazione host correlata deve restituire un valore di tipo . Il codice seguente illustra la visualizzazione host del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Il metodo del <xref:System.AddIn.Contract.INativeHandleContract>contratto restituisce un <xref:System.Windows.FrameworkElement> oggetto , ma l'applicazione host prevede un oggetto (come specificato dalla visualizzazione host). Di conseguenza, <xref:System.AddIn.Contract.INativeHandleContract> l'oggetto <xref:System.Windows.FrameworkElement> deve essere convertito in un dopo aver superato il limite di isolamento. Questa operazione viene eseguita dall'adattatore sul lato host chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Una volta creati l'adattatore sul lato componente aggiuntivo`WPFAddIn1.AddIn`e la `IWPFAddInView.GetAddInUI` visualizzazione del <xref:System.Windows.FrameworkElement> componente aggiuntivo, il componente aggiuntivo ( ) deve implementare il metodo per restituire un oggetto (un <xref:System.Windows.Controls.UserControl> in questo esempio). L'implementazione <xref:System.Windows.Controls.UserControl> `AddInUI`di , , è illustrata dal codice seguente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 L'implementazione `IWPFAddInView.GetAddInUI` di da parte del componente aggiuntivo `AddInUI`deve semplicemente restituire una nuova istanza di , come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Dopo aver creato l'adattatore sul lato host e la visualizzazione host, l'applicazione host può utilizzare il modello di `IWPFAddInHostView.GetAddInUI` componente aggiuntivo .NET Framework per aprire la pipeline, acquisire una visualizzazione host del componente aggiuntivo e chiamare il metodo . Il codice riportato di seguito illustra i diversi passaggi.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vedere anche

- [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md)
