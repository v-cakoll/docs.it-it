---
title: 'Procedura: creare un componente aggiuntivo che costituisce un''interfaccia utente'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fea1c718eedb12d49eced9964e4f9045badf07ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedura: creare un componente aggiuntivo che costituisce un'interfaccia utente
In questo esempio viene illustrato come creare un componente aggiuntivo che è un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ed è ospitato da un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione autonoma.  
  
 Il componente aggiuntivo è un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vale a dire un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] controllo utente. Il contenuto del controllo utente è costituito da un unico pulsante che consente di visualizzare una finestra di messaggio. Il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione autonoma ospita il componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] come contenuto della finestra principale dell'applicazione.  
  
 **Prerequisiti**  
  
 In questo esempio viene evidenziato il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estensioni per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aggiuntivo modello abilitare questo scenario, si presuppone quanto segue:  
  
-   Conoscere il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello del componente aggiuntivo, tra cui sviluppo di pipeline, componenti aggiuntivi e host. Se non si ha familiarità con questi concetti, vedere [aggiuntivi ed estensibilità](../../../../docs/framework/add-ins/index.md). Per un'esercitazione che illustra l'implementazione di una pipeline, un componente aggiuntivo e un'applicazione host, vedere [procedura dettagliata: creazione di un'applicazione estensibile](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Conoscenza del [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] estensioni per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello del componente aggiuntivo, che è disponibili qui: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Esempio  
 Per creare un componente aggiuntivo che è un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiede codice specifico per ogni segmento della pipeline, il componente aggiuntivo e l'applicazione host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementazione del segmento di pipeline di contratto  
 Quando un componente aggiuntivo è un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], deve implementare il contratto per il componente aggiuntivo <xref:System.AddIn.Contract.INativeHandleContract>. Nell'esempio `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione componente aggiuntivo  
 Poiché il componente aggiuntivo viene implementato come una sottoclasse di <xref:System.Windows.FrameworkElement> tipo, la vista del componente aggiuntivo deve inoltre sottoclasse <xref:System.Windows.FrameworkElement>. Il codice seguente mostra la vista del componente aggiuntivo del contratto, implementato come la `WPFAddInView` classe.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 In questo caso, la vista del componente aggiuntivo è derivata da <xref:System.Windows.Controls.UserControl>. Di conseguenza, il componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] anche deve derivare da <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato del componente aggiuntivo  
 Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, il componente aggiuntivo è un <xref:System.Windows.FrameworkElement> (come specificato dal segmento di pipeline di visualizzazione). Pertanto, il <xref:System.Windows.FrameworkElement> deve essere convertito in un <xref:System.AddIn.Contract.INativeHandleContract> prima di oltrepassare il limite di isolamento. Questa operazione viene eseguita dall'adapter sul lato componente-chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, come illustrato nel codice seguente.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 Del modello di componente aggiuntivo in un componente aggiuntivo restituisce un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (vedere [creare un componente aggiuntivo che restituisce un'interfaccia utente](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), l'adattatore del componente aggiuntivo di convertire il <xref:System.Windows.FrameworkElement> per un <xref:System.AddIn.Contract.INativeHandleContract> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>deve inoltre essere chiamato in questo modello, anche se è necessario implementare un metodo da cui scrivere il codice per la chiamata. A tale scopo, si esegue l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implementare il codice che chiama <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se il codice che chiama <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> è previsto un <xref:System.AddIn.Contract.INativeHandleContract>. In questo caso il chiamante sarà l'adattatore sul lato host, trattato in una sottosezione successiva.  
  
> [!NOTE]
>  È inoltre necessario eseguire l'override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in questo modello per abilitare la tabulazione tra l'applicazione host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] e componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Per ulteriori informazioni, vedere "WPF aggiuntivo limitazioni" in [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Poiché l'adapter sul lato componente-implementa un'interfaccia che deriva da <xref:System.AddIn.Contract.INativeHandleContract>, è necessario implementare <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, anche se questo parametro viene ignorato quando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> viene sottoposto a override.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementazione del segmento di pipeline di visualizzazione host  
 In questo modello, l'applicazione host è in genere prevede la visualizzazione host deve essere un <xref:System.Windows.FrameworkElement> sottoclasse. Adattatore sul lato host deve convertire il <xref:System.AddIn.Contract.INativeHandleContract> per un <xref:System.Windows.FrameworkElement> dopo il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento. Quando un metodo non viene chiamato dall'applicazione host per ottenere il <xref:System.Windows.FrameworkElement>, la visualizzazione host deve "restituire" il <xref:System.Windows.FrameworkElement> da che lo contiene. Di conseguenza, la visualizzazione host deve derivare da una sottoclasse di <xref:System.Windows.FrameworkElement> che può contenere altre [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], ad esempio <xref:System.Windows.Controls.UserControl>. Il codice seguente viene illustrata la visualizzazione di host del contratto, implementato come la `WPFAddInHostView` classe.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementazione del segmento di pipeline dell'adattatore sul lato host  
 Mentre il contratto è un <xref:System.AddIn.Contract.INativeHandleContract>, l'applicazione host prevede un <xref:System.Windows.Controls.UserControl> (come specificato dalla visualizzazione host). Di conseguenza, il <xref:System.AddIn.Contract.INativeHandleContract> deve essere convertito in un <xref:System.Windows.FrameworkElement> dopo aver oltrepassato il limite di isolamento, prima di essere impostato come contenuto della visualizzazione host (che deriva da <xref:System.Windows.Controls.UserControl>).  
  
 La conversione viene eseguita dall'adattatore sul lato host, come illustrato nel codice seguente.  
  
  
  
 Come si può notare, l'adattatore sul lato host acquisisce il <xref:System.AddIn.Contract.INativeHandleContract> chiamando dell'adapter sul lato componente- <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> (metodo) (questo è il punto in cui il <xref:System.AddIn.Contract.INativeHandleContract> supera il limite di isolamento).  
  
 Adattatore sul lato host converte quindi il <xref:System.AddIn.Contract.INativeHandleContract> per un <xref:System.Windows.FrameworkElement> chiamando <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Infine, il <xref:System.Windows.FrameworkElement> è impostato come il contenuto della visualizzazione host.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementazione del componente aggiuntivo  
 Una volta creati l'adattatore sul lato del componente aggiuntivo e la visualizzazione componente aggiuntivo, il componente aggiuntivo può essere implementato mediante derivazione dalla visualizzazione componente aggiuntivo, come illustrato nel codice seguente.  
  
  
  
  
  
 Questo esempio, è possibile visualizzare un interessante vantaggio di questo modello: gli sviluppatori di componenti devono semplicemente implementare il componente aggiuntivo (perché è il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nonché), invece di una classe di componente aggiuntivo e un componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host  
 Con l'adattatore host sul lato host creato e la visualizzazione, è possibile utilizzare l'applicazione host di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modello di componente aggiuntivo per aprire la pipeline e acquisire una visualizzazione host del componente aggiuntivo. Il codice riportato di seguito illustra i diversi passaggi.  
  
  
  
 L'applicazione host usa tipico [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] codice del modello di componente aggiuntivo per attivare il componente aggiuntivo, che restituisce in modo implicito la visualizzazione host per l'applicazione host. L'applicazione host successivamente, viene visualizzata la visualizzazione host (ovvero un <xref:System.Windows.Controls.UserControl>) da un <xref:System.Windows.Controls.Grid>.  
  
 Il codice per l'elaborazione delle interazioni con il componente aggiuntivo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene eseguito nel dominio dell'applicazione del componente aggiuntivo. Di seguito vengono riportati alcuni esempi di interazione:  
  
-   La gestione di <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
-   Visualizzazione di <xref:System.Windows.MessageBox>.  
  
 Questa attività è completamente isolata dall'applicazione host.  
  
## <a name="see-also"></a>Vedere anche  
 [Componenti aggiuntivi ed estendibilità](../../../../docs/framework/add-ins/index.md)  
 [Cenni preliminari sui componenti aggiuntivi di WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
