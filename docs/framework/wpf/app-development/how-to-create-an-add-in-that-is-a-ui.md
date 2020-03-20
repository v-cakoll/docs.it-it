---
title: "Procedura: creare un componente aggiuntivo che costituisce un'interfaccia utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141029"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedura: creare un componente aggiuntivo che costituisce un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che è un Windows Presentation Foundation (WPF) ospitato da un'applicazione autonoma WPFWPF.  
  
 Il componente aggiuntivo è un'interfaccia utente che è un controllo utente WPFWPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione autonoma WPFWPF ospita l'interfaccia utente del componente aggiuntivo come contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio vengono evidenziate le estensioni WPF per il modello di componente aggiuntivo .NET Framework.NET Framework che abilitano questo scenario e presuppone quanto segue:  
  
- Conoscenza del modello di componente aggiuntivo .NET Framework, inclusi pipeline, componente aggiuntivo e sviluppo host. Se non si ha familiarità con questi concetti, vedere [Componenti aggiuntivi ed estensibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere procedura dettagliata: creazione di [un'applicazione estensibile.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))  
  
- Conoscenza delle estensioni WPF al modello di componente aggiuntivo .NET Framework. Vedere [Cenni preliminari sui componenti aggiuntivi WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che è un'interfaccia utente WPFWPF richiede codice specifico per ogni segmento di pipeline, il componente aggiuntivo e l'applicazione host.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto

Quando un componente aggiuntivo è un'interfaccia utente, il <xref:System.AddIn.Contract.INativeHandleContract>contratto per il componente aggiuntivo deve implementare . Nell'esempio `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, come illustrato nel codice seguente.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo

Poiché il componente aggiuntivo viene implementato <xref:System.Windows.FrameworkElement> come sottoclasse del tipo, anche <xref:System.Windows.FrameworkElement>la visualizzazione del componente aggiuntivo deve includere una sottoclasse . Nel codice seguente viene illustrata la visualizzazione del `WPFAddInView` componente aggiuntivo del contratto, implementata come classe.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
In questo caso, la visualizzazione <xref:System.Windows.Controls.UserControl>del componente aggiuntivo è derivata da . Di conseguenza, anche l'interfaccia <xref:System.Windows.Controls.UserControl>utente del componente aggiuntivo deve derivare da .  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo

Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.Windows.FrameworkElement> il componente aggiuntivo è un (come specificato dal segmento della pipeline di visualizzazione del componente aggiuntivo). Pertanto, <xref:System.Windows.FrameworkElement> il deve <xref:System.AddIn.Contract.INativeHandleContract> essere convertito in un prima di attraversare il limite di isolamento. Questa operazione viene eseguita dall'adattatore <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>sul lato componente aggiuntivo chiamando , come illustrato nel codice seguente.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

Nel modello di componente aggiuntivo in cui un componente aggiuntivo restituisce un'interfaccia utente (vedere Creare <xref:System.Windows.FrameworkElement> un <xref:System.AddIn.Contract.INativeHandleContract> componente <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>aggiuntivo [che restituisce un'interfaccia utente](how-to-create-an-add-in-that-returns-a-ui.md)), l'adattatore del componente aggiuntivo ha convertito l'oggetto in un chiamando . <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>deve essere chiamato anche in questo modello, anche se è necessario implementare un metodo da cui scrivere il codice per chiamarlo. A tale scopo, <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> eseguire l'override <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> e implementare <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> il codice <xref:System.AddIn.Contract.INativeHandleContract>che chiama se il codice che chiama è in attesa di un oggetto . In questo caso il chiamante sarà l'adattatore sul lato host, trattato in una sottosezione successiva.  
  
> [!NOTE]
> È inoltre necessario <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> eseguire l'override in questo modello per abilitare la tabulazione tra l'interfaccia utente dell'applicazione host e l'interfaccia utente del componente aggiuntivo. Per ulteriori informazioni, vedere "Limitazioni dei componenti aggiuntivi WPF" in [Cenni preliminari](wpf-add-ins-overview.md)sui componenti aggiuntivi WPF .  
  
Poiché l'adattatore sul lato componente <xref:System.AddIn.Contract.INativeHandleContract>aggiuntivo implementa un'interfaccia che deriva da , è necessario implementare <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>anche , anche se questo viene ignorato quando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> viene sottoposto a override.  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host

In questo modello, l'applicazione host prevede in <xref:System.Windows.FrameworkElement> genere che la visualizzazione host sia una sottoclasse. L'adattatore sul lato host deve convertire il <xref:System.AddIn.Contract.INativeHandleContract> oggetto in un <xref:System.Windows.FrameworkElement> dopo che il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento. Poiché un metodo non viene chiamato dall'applicazione host per ottenere l'oggetto <xref:System.Windows.FrameworkElement>, la visualizzazione host deve "restituire" il <xref:System.Windows.FrameworkElement> da contenerla. Di conseguenza, la visualizzazione host deve <xref:System.Windows.FrameworkElement> derivare da una sottoclasse di che può contenere altre classi utente, ad <xref:System.Windows.Controls.UserControl>esempio . Nel codice seguente viene illustrata la visualizzazione `WPFAddInHostView` host del contratto, implementata come classe.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host

Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.Windows.Controls.UserControl> l'applicazione host prevede un (come specificato dalla visualizzazione host). Di conseguenza, <xref:System.AddIn.Contract.INativeHandleContract> l'oggetto <xref:System.Windows.FrameworkElement> deve essere convertito in un valore dopo aver superato <xref:System.Windows.Controls.UserControl>il limite di isolamento, prima di essere impostato come contenuto della visualizzazione host (che deriva da ).  
  
La conversione viene eseguita dall'adattatore sul lato host, come illustrato nel codice seguente.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Come si può vedere, l'adattatore <xref:System.AddIn.Contract.INativeHandleContract> sul lato host acquisisce <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> il chiamando il metodo <xref:System.AddIn.Contract.INativeHandleContract> dell'adattatore sul lato componente aggiuntivo (questo è il punto in cui il attraversa il limite di isolamento).  
  
L'adattatore sul lato <xref:System.AddIn.Contract.INativeHandleContract> host <xref:System.Windows.FrameworkElement> converte quindi l'oggetto in a chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Infine, <xref:System.Windows.FrameworkElement> l'oggetto viene impostato come contenuto della visualizzazione host.  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo

Una volta creati l'adattatore sul lato del componente aggiuntivo e la visualizzazione componente aggiuntivo, il componente aggiuntivo può essere implementato mediante derivazione dalla visualizzazione componente aggiuntivo, come illustrato nel codice seguente.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

Da questo esempio, è possibile vedere un vantaggio interessante di questo modello: gli sviluppatori di componenti aggiuntivi devono solo implementare il componente aggiuntivo (poiché è anche l'interfaccia utente), anziché sia una classe di componente aggiuntivo che un'interfaccia utente del componente aggiuntivo.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host

Dopo aver creato l'adattatore sul lato host e la visualizzazione host, l'applicazione host può utilizzare il modello di componente aggiuntivo .NET Framework per aprire la pipeline e acquisire una visualizzazione host del componente aggiuntivo. Il codice riportato di seguito illustra i diversi passaggi.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

L'applicazione host utilizza il tipico codice del modello di componente aggiuntivo .NET Framework per attivare il componente aggiuntivo, che restituisce in modo implicito la visualizzazione host all'applicazione host. L'applicazione host visualizza successivamente la <xref:System.Windows.Controls.UserControl>visualizzazione host <xref:System.Windows.Controls.Grid>(che è un ) da un oggetto .  
  
 Il codice per l'elaborazione delle interazioni con l'interfaccia utente del componente aggiuntivo viene eseguito nel dominio applicazione del componente aggiuntivo. Di seguito vengono riportati alcuni esempi di interazione:  
  
- Gestione <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dell'evento.  
  
- Visualizzazione <xref:System.Windows.MessageBox>del file .  
  
 Questa attività è completamente isolata dall'applicazione host.  
  
## <a name="see-also"></a>Vedere anche

- [Componenti aggiuntivi ed estendibilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md)
