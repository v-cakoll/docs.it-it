---
title: Cenni preliminari sulle topologie di navigazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbe7fe80639537293413d8fb923033909a2451e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="navigation-topologies-overview"></a>Cenni preliminari sulle topologie di navigazione
<a name="introduction"></a>Questa panoramica fornisce un'introduzione alle topologie di spostamento in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Di seguito vengono analizzate tre topologie di navigazione comuni con i relativi esempi.  
  
> [!NOTE]
>  Prima di leggere questo argomento, è necessario avere familiarità con il concetto di spostamento strutturato in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizzando funzioni di pagina. Per ulteriori informazioni su entrambi gli argomenti, vedere [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Topologie di navigazione](#Navigation_Topologies)  
  
-   [Topologie di navigazione strutturata](#Structured_Navigation_Topologies)  
  
-   [Navigazione in una topologia lineare fissa](#Navigation_over_a_Fixed_Linear_Topology)  
  
-   [Navigazione dinamica in una topologia gerarchica fissa](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
-   [Navigazione in una topologia generata dinamicamente](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a>Topologie di navigazione  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigazione consiste in genere di pagine (<xref:System.Windows.Controls.Page>) con i collegamenti ipertestuali (<xref:System.Windows.Documents.Hyperlink>) che consentono di passare ad altre pagine quando si fa clic. Le pagine in cui ci si sposta sono identificate da [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (vedere [URI di tipo Pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)). Si consideri l'esempio seguente che mostra le pagine, collegamenti ipertestuali, e [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 Queste pagine sono disposte un *topologia di navigazione* la cui struttura è determinata da come è possibile spostarsi tra le pagine. Questa particolare topologia di navigazione è adatta in scenari semplici. La navigazione può tuttavia richiedere topologie più complesse, alcune delle quali possono essere definite solo quando un'applicazione è in esecuzione.  
  
 Questo argomento vengono illustrati tre topologie di spostamento comuni: *lineare fissa*, *gerarchica fissa*, e *generato dinamicamente*. Ogni topologia di navigazione è illustrato un esempio con un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] come quello illustrato nella figura riportata di seguito:  
  
 ![Pagine di attività con elementi di dati](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a>Topologie di navigazione strutturata  
 Vi sono due topologie principali di navigazione:  
  
-   **Topologia fissa**: è definita in fase di compilazione e non viene modificata in fase di esecuzione. Le topologie fisse sono utili per la navigazione in una sequenza fissa di pagine in un ordine lineare o gerarchico.  
  
-   **Topologia dinamica**: è definita in fase di esecuzione in base agli input raccolti dall'utente, dall'applicazione o dal sistema. Le topologie dinamiche sono utili quando è possibile spostarsi sulle pagine in sequenze diverse.  
  
 Sebbene sia possibile creare topologie di navigazione usando le pagine, gli esempi usano funzioni di pagina poiché questi offrono un supporto aggiuntivo che semplifica il passaggio e la restituzione dei dati tramite le pagine di una topologia.  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a>Navigazione in una topologia lineare fissa  
 Una topologia lineare fissa è analoga alla struttura di una procedura guidata con una o più pagine in cui ci si sposta in una sequenza fissa. La figura seguente illustra la struttura generale e il flusso di una procedura guidata con topologia lineare fissa.  
  
 ![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")  
  
 I comportamenti tipici per la navigazione in una topologia lineare fissa includono quanto segue:  
  
-   Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa. La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente. L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.  
  
-   Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).  
  
-   Gli utenti possono spostarsi tra pagine usando il journal.  
  
-   Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.  
  
-   Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.  
  
-   Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.  
  
-   Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.  
  
-   Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal. In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a>Navigazione dinamica in una topologia gerarchica fissa  
 In alcune applicazioni le pagine consentono di spostarsi su due o più altre pagine, come illustrato nella figura seguente.  
  
 ![Pagina che consente di spostarsi su diverse altre pagine](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")  
  
 Questa struttura è detta topologia gerarchica fissa e la sequenza in cui viene attraversata è spesso determinata in fase di esecuzione dall'applicazione o dall'utente. In fase di esecuzione, ogni pagina della gerarchia che consente di spostarsi su due o più altre pagine raccoglie i dati richiesti per determinare su quale pagina spostarsi. La figura seguente illustra una delle possibili sequenze di navigazione in base alla figura precedente.  
  
 ![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")  
  
 Anche se la sequenza di navigazione delle pagine in una struttura gerarchica fissa è determinata in fase di esecuzione, l'esperienza utente è la stessa di una topologia lineare fissa:  
  
-   Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa. La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente. L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.  
  
-   Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).  
  
-   Gli utenti possono spostarsi tra pagine usando il journal.  
  
-   Gli utenti possono modificare la sequenza di navigazione se tornano indietro tramite il journal.  
  
-   Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.  
  
-   Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.  
  
-   Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.  
  
-   Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.  
  
-   Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal. In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a>Navigazione in una topologia generata dinamicamente  
 In alcune applicazioni la sequenza di navigazione di due o più pagine può essere determinata solo in fase di esecuzione dall'utente, dall'applicazione o da dati esterni. La figura seguente illustra un insieme di pagine con una sequenza di navigazione non determinata.  
  
 ![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")  
  
 La figura seguente illustra una sequenza di navigazione scelta dall'utente in fase di esecuzione.  
  
 ![Diagramma di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")  
  
 La sequenza di navigazione è indicata come topologia generata dinamicamente. L'esperienza utente è analoga alle topologie di navigazione precedenti:  
  
-   Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa. La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente. L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.  
  
-   Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).  
  
-   Gli utenti possono spostarsi tra pagine usando il journal.  
  
-   Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.  
  
-   Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.  
  
-   Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.  
  
-   Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.  
  
-   Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal. In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.PageFunction%601>  
 <xref:System.Windows.Navigation.NavigationService>  
 [Cenni preliminari sulla navigazione strutturata](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)
