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
ms.openlocfilehash: 1886703e089ed538f68a7221906d815a8ae72076
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182667"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Procedura: Procedura: creare un componente aggiuntivo che restituisce un'interfaccia utente
Questo esempio illustra come creare un componente aggiuntivo che restituisce un Windows Presentation Foundation (WPF) a un'applicazione autonoma WPF host.  
  
 Il componente aggiuntivo restituisce un'interfaccia utente che rappresenta un controllo utente WPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione autonoma WPF ospita il componente aggiuntivo e visualizza il controllo utente (restituito dal componente aggiuntivo) come contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio vengono evidenziate le estensioni WPF per il modello di componente aggiuntivo .NET Framework che Abilita questo scenario e si presuppone quanto segue:  
  
- Conoscenza del modello di componente aggiuntivo .NET Framework, tra cui pipeline, componente aggiuntivo e sviluppo host. Se non si ha familiarità con questi concetti, vedere [componenti aggiuntivi ed estensibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione in cui viene illustrata l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, [vedere Procedura dettagliata: Creazione di un'applicazione](../../add-ins/walkthrough-create-extensible-app.md)estendibile.  
  
- Informazioni sulle estensioni WPF per il modello di componente aggiuntivo .NET Framework, disponibile qui: [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che restituisce un'interfaccia utente WPF, è necessario codice specifico per ogni segmento di pipeline, per il componente aggiuntivo e per l'applicazione host.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Un metodo deve essere definito dal contratto per la restituzione di un'interfaccia utente e il relativo valore restituito deve <xref:System.AddIn.Contract.INativeHandleContract>essere di tipo. Questa operazione viene illustrata `GetAddInUI` dal metodo `IWPFAddInContract` del contratto nel codice riportato di seguito.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo implementa l'oggetto [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] fornito come sottoclassi di <xref:System.Windows.FrameworkElement>, il metodo nella visualizzazione del componente aggiuntivo correlato a `IWPFAddInView.GetAddInUI` deve restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione componente aggiuntivo del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Il metodo del contratto restituisce <xref:System.AddIn.Contract.INativeHandleContract>un oggetto, ma il componente aggiuntivo restituisce <xref:System.Windows.FrameworkElement> un oggetto, come specificato dalla visualizzazione del componente aggiuntivo. Di conseguenza, <xref:System.Windows.FrameworkElement> l'oggetto deve essere convertito <xref:System.AddIn.Contract.INativeHandleContract> in un oggetto prima di attraversare il limite di isolamento. Questa operazione viene eseguita dall'adattatore sul lato del componente aggiuntivo chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 Poiché l'applicazione host visualizzerà un <xref:System.Windows.FrameworkElement>oggetto, il metodo nella visualizzazione host correlata a `IWPFAddInHostView.GetAddInUI` deve restituire un valore di tipo <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione host del contratto, implementata come interfaccia.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Il metodo del contratto restituisce <xref:System.AddIn.Contract.INativeHandleContract>un oggetto, ma l'applicazione host prevede <xref:System.Windows.FrameworkElement> un oggetto, come specificato dalla visualizzazione host. Di conseguenza, <xref:System.AddIn.Contract.INativeHandleContract> l'oggetto deve essere convertito <xref:System.Windows.FrameworkElement> in un oggetto dopo aver oltrepassato il limite di isolamento. Questa operazione viene eseguita dall'adattatore sul lato host chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Con l'adattatore lato componente aggiuntivo e la visualizzazione dei componenti aggiuntivi creati, il componente aggiuntivo`WPFAddIn1.AddIn`() deve implementare il `IWPFAddInView.GetAddInUI` metodo per <xref:System.Windows.Controls.UserControl> restituire un <xref:System.Windows.FrameworkElement> oggetto (in questo esempio). L'implementazione di <xref:System.Windows.Controls.UserControl>, `AddInUI`, viene mostrata dal codice seguente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 L'implementazione di `IWPFAddInView.GetAddInUI` da parte del componente aggiuntivo deve semplicemente restituire una nuova istanza di `AddInUI`, come illustrato dal codice seguente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Con l'adattatore sul lato host e la visualizzazione host creati, l'applicazione host può utilizzare il .NET Framework modello di componente aggiuntivo per aprire la pipeline, acquisire una visualizzazione host del componente aggiuntivo e chiamare il `IWPFAddInHostView.GetAddInUI` metodo. Il codice riportato di seguito illustra i diversi passaggi.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vedere anche

- [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md)
