---
title: "Procedura: Creare un componente aggiuntivo che costituisca un'interfaccia utente"
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 0464d87aef3d4e88d9340af2ac1db93c13ba26e2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592657"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedura: Creare un componente aggiuntivo che costituisca un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che è un Windows Presentation Foundation (WPF) che è ospitata da un'applicazione WPF autonoma.  
  
 Il componente aggiuntivo è un'interfaccia utente che è un controllo utente WPF. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. L'applicazione WPF autonoma ospita il componente aggiuntivo dell'interfaccia utente come il contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 Questo esempio illustra le estensioni WPF per il modello di componente aggiuntivo di .NET Framework che abilitare questo scenario e si presuppone quanto segue:  
  
- Conoscenza del .NET Framework-in modello, tra cui sviluppo di pipeline, componenti aggiuntivi e host. Se non si ha familiarità con questi concetti, vedere [componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere [procedura dettagliata: Creazione di un'applicazione estendibile](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Conoscenza delle estensioni di WPF per il modello di componente aggiuntivo di .NET Framework. Visualizzare [Cenni preliminari sui componenti aggiuntivi WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che è una UI WPF è necessario codice specifico per ogni segmento di pipeline, il componente aggiuntivo e l'applicazione host.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Quando un componente aggiuntivo è un'interfaccia utente, il contratto per il componente aggiuntivo deve implementare <xref:System.AddIn.Contract.INativeHandleContract>. Nell'esempio riportato `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo viene implementato come una sottoclasse di <xref:System.Windows.FrameworkElement> tipo, la visualizzazione componente aggiuntivo deve inoltre creare una sottoclasse <xref:System.Windows.FrameworkElement>. Il codice seguente illustra la visualizzazione componente aggiuntivo del contratto, implementata come il `WPFAddInView` classe.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 In questo caso, la visualizzazione del componente aggiuntivo deriva da <xref:System.Windows.Controls.UserControl>. Di conseguenza, l'interfaccia utente del componente aggiuntivo deve derivare anche da <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, il componente aggiuntivo è un <xref:System.Windows.FrameworkElement> (come specificato dal segmento di pipeline nella visualizzazione componente aggiuntivo). Pertanto, il <xref:System.Windows.FrameworkElement> deve essere convertito in un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento. Questa operazione viene eseguita dall'adattatore lato componente aggiuntivo tramite la chiamata <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 Del modello di componente aggiuntivo in cui un componente aggiuntivo restituisce un'interfaccia utente (vedere [creare un componente aggiuntivo che restituisce un'interfaccia utente](how-to-create-an-add-in-that-returns-a-ui.md)), l'adattatore di componente aggiuntivo convertito il <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> deve anche essere chiamato in questo modello, anche se è necessario implementare un metodo da cui scrivere il codice per chiamarla. A tale scopo, si esegue l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implementare il codice che chiama <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se il codice che chiama <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> prevede un <xref:System.AddIn.Contract.INativeHandleContract>. In questo caso il chiamante sarà l'adattatore sul lato host, trattato in una sottosezione successiva.  
  
> [!NOTE]
>  È anche necessario eseguire l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in questo modello per abilitare la tabulazione tra interfaccia utente dell'applicazione host e componenti aggiuntivi dell'interfaccia utente. Per altre informazioni, vedere "Limitazioni WPF" nella [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md).  
  
 Poiché l'adattatore lato componente aggiuntivo implementa un'interfaccia che deriva da <xref:System.AddIn.Contract.INativeHandleContract>, è inoltre necessario implementare <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, anche se questo parametro viene ignorato quando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> viene sottoposto a override.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 In questo modello, l'applicazione host prevede in genere la visualizzazione host deve essere un <xref:System.Windows.FrameworkElement> sottoclasse. L'adattatore lato host deve convertire le <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> dopo il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento. Poiché un metodo non viene chiamato dall'applicazione host per ottenere il <xref:System.Windows.FrameworkElement>, la visualizzazione host deve "restituire" il <xref:System.Windows.FrameworkElement> contenendolo. Di conseguenza, la visualizzazione host deve derivare da una sottoclasse di <xref:System.Windows.FrameworkElement> che possono contenere altri [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], ad esempio <xref:System.Windows.Controls.UserControl>. Il codice seguente mostra la visualizzazione host del contratto, implementata come il `WPFAddInHostView` classe.  

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, l'applicazione host prevede un <xref:System.Windows.Controls.UserControl> (come specificato dalla visualizzazione host). Di conseguenza, il <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento, prima di essere impostato come contenuto della visualizzazione host (che deriva da <xref:System.Windows.Controls.UserControl>).  
  
 La conversione viene eseguita dall'adattatore sul lato host, come illustrato nel codice seguente.  

 Come si può notare, l'adattatore lato host acquisisce il <xref:System.AddIn.Contract.INativeHandleContract> mediante la chiamata dell'adattatore lato componente aggiuntivo <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> metodo (questo è il punto in cui il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento).  
  
 L'adattatore lato host converte quindi il <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Infine, il <xref:System.Windows.FrameworkElement> è impostato come contenuto della visualizzazione host.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Una volta creati l'adattatore sul lato del componente aggiuntivo e la visualizzazione componente aggiuntivo, il componente aggiuntivo può essere implementato mediante derivazione dalla visualizzazione componente aggiuntivo, come illustrato nel codice seguente.  

 Questo esempio, si noterà un interessante vantaggio di questo modello: add-negli sviluppatori devono semplicemente implementare il componente aggiuntivo (dal momento che è anche l'interfaccia utente), anziché una classe di componente aggiuntivo sia un componente aggiuntivo dell'interfaccia utente.  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Adattatore lato host e la visualizzazione host creato, l'applicazione host può utilizzare il modello di componente aggiuntivo di .NET Framework per aprire la pipeline e acquisire una visualizzazione host del componente aggiuntivo. Il codice riportato di seguito illustra i diversi passaggi.  

 L'applicazione host Usa codice tipico modello di componente aggiuntivo di .NET Framework per attivare il componente aggiuntivo, il quale restituisce implicitamente la visualizzazione host per l'applicazione host. L'applicazione host successivamente, viene visualizzata la visualizzazione host (che è un <xref:System.Windows.Controls.UserControl>) da un <xref:System.Windows.Controls.Grid>.  
  
 Il codice per l'elaborazione delle interazioni con l'interfaccia utente del componente aggiuntivo viene eseguito nel dominio di applicazione del componente aggiuntivo. Di seguito vengono riportati alcuni esempi di interazione:  
  
- La gestione di <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
- Che mostra il <xref:System.Windows.MessageBox>.  
  
 Questa attività è completamente isolata dall'applicazione host.  
  
## <a name="see-also"></a>Vedere anche

- [Componenti aggiuntivi ed estendibilità](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Cenni preliminari sui componenti aggiuntivi di WPF](wpf-add-ins-overview.md)
