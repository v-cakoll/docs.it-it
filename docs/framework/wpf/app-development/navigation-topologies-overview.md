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
# <a name="navigation-topologies-overview"></a><span data-ttu-id="ebec5-102">Cenni preliminari sulle topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="ebec5-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="ebec5-103">Questa panoramica fornisce un'introduzione alle topologie di spostamento in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebec5-103">This overview provides an introduction to navigation topologies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="ebec5-104">Di seguito vengono analizzate tre topologie di navigazione comuni con i relativi esempi.</span><span class="sxs-lookup"><span data-stu-id="ebec5-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebec5-105">Prima di leggere questo argomento, è necessario avere familiarità con il concetto di spostamento strutturato in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utilizzando funzioni di pagina.</span><span class="sxs-lookup"><span data-stu-id="ebec5-105">Before reading this topic, you should be familiar with the concept of structured navigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] using page functions.</span></span> <span data-ttu-id="ebec5-106">Per ulteriori informazioni su entrambi gli argomenti, vedere [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ebec5-106">For more information on both of these topics, see [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="ebec5-107">Di seguito sono elencate le diverse sezioni di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="ebec5-107">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="ebec5-108">Topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="ebec5-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
-   [<span data-ttu-id="ebec5-109">Topologie di navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="ebec5-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
-   [<span data-ttu-id="ebec5-110">Navigazione in una topologia lineare fissa</span><span class="sxs-lookup"><span data-stu-id="ebec5-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
-   [<span data-ttu-id="ebec5-111">Navigazione dinamica in una topologia gerarchica fissa</span><span class="sxs-lookup"><span data-stu-id="ebec5-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
-   [<span data-ttu-id="ebec5-112">Navigazione in una topologia generata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="ebec5-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a><span data-ttu-id="ebec5-113">Topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="ebec5-113">Navigation Topologies</span></span>  
 <span data-ttu-id="ebec5-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigazione consiste in genere di pagine (<xref:System.Windows.Controls.Page>) con i collegamenti ipertestuali (<xref:System.Windows.Documents.Hyperlink>) che consentono di passare ad altre pagine quando si fa clic.</span><span class="sxs-lookup"><span data-stu-id="ebec5-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="ebec5-115">Le pagine in cui ci si sposta sono identificate da [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (vedere [URI di tipo Pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="ebec5-115">Pages that are navigated to are identified by [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="ebec5-116">Si consideri l'esempio seguente che mostra le pagine, collegamenti ipertestuali, e [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ebec5-116">Consider the following simple example that shows pages, hyperlinks, and [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="ebec5-117">Queste pagine sono disposte un *topologia di navigazione* la cui struttura è determinata da come è possibile spostarsi tra le pagine.</span><span class="sxs-lookup"><span data-stu-id="ebec5-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="ebec5-118">Questa particolare topologia di navigazione è adatta in scenari semplici. La navigazione può tuttavia richiedere topologie più complesse, alcune delle quali possono essere definite solo quando un'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ebec5-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="ebec5-119">Questo argomento vengono illustrati tre topologie di spostamento comuni: *lineare fissa*, *gerarchica fissa*, e *generato dinamicamente*.</span><span class="sxs-lookup"><span data-stu-id="ebec5-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="ebec5-120">Ogni topologia di navigazione è illustrato un esempio con un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] come quello illustrato nella figura riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="ebec5-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 <span data-ttu-id="ebec5-121">![Pagine di attività con elementi di dati](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")</span><span class="sxs-lookup"><span data-stu-id="ebec5-121">![Task pages with data items](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure6.png "NavigationTopologyFigure6")</span></span>  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a><span data-ttu-id="ebec5-122">Topologie di navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="ebec5-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="ebec5-123">Vi sono due topologie principali di navigazione:</span><span class="sxs-lookup"><span data-stu-id="ebec5-123">There are two broad types of navigation topologies:</span></span>  
  
-   <span data-ttu-id="ebec5-124">**Topologia fissa**: è definita in fase di compilazione e non viene modificata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ebec5-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="ebec5-125">Le topologie fisse sono utili per la navigazione in una sequenza fissa di pagine in un ordine lineare o gerarchico.</span><span class="sxs-lookup"><span data-stu-id="ebec5-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
-   <span data-ttu-id="ebec5-126">**Topologia dinamica**: è definita in fase di esecuzione in base agli input raccolti dall'utente, dall'applicazione o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ebec5-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="ebec5-127">Le topologie dinamiche sono utili quando è possibile spostarsi sulle pagine in sequenze diverse.</span><span class="sxs-lookup"><span data-stu-id="ebec5-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="ebec5-128">Sebbene sia possibile creare topologie di navigazione usando le pagine, gli esempi usano funzioni di pagina poiché questi offrono un supporto aggiuntivo che semplifica il passaggio e la restituzione dei dati tramite le pagine di una topologia.</span><span class="sxs-lookup"><span data-stu-id="ebec5-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="ebec5-129">Navigazione in una topologia lineare fissa</span><span class="sxs-lookup"><span data-stu-id="ebec5-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="ebec5-130">Una topologia lineare fissa è analoga alla struttura di una procedura guidata con una o più pagine in cui ci si sposta in una sequenza fissa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="ebec5-131">La figura seguente illustra la struttura generale e il flusso di una procedura guidata con topologia lineare fissa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology.</span></span>  
  
 <span data-ttu-id="ebec5-132">![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")</span><span class="sxs-lookup"><span data-stu-id="ebec5-132">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure1.png "NavigationTopologyFigure1")</span></span>  
  
 <span data-ttu-id="ebec5-133">I comportamenti tipici per la navigazione in una topologia lineare fissa includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ebec5-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
-   <span data-ttu-id="ebec5-134">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="ebec5-135">La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="ebec5-136">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="ebec5-137">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="ebec5-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="ebec5-138">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-138">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="ebec5-139">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="ebec5-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="ebec5-140">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="ebec5-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="ebec5-141">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="ebec5-142">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="ebec5-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="ebec5-143">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="ebec5-144">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="ebec5-145">Navigazione dinamica in una topologia gerarchica fissa</span><span class="sxs-lookup"><span data-stu-id="ebec5-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="ebec5-146">In alcune applicazioni le pagine consentono di spostarsi su due o più altre pagine, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="ebec5-147">![Pagina che consente di spostarsi su diverse altre pagine](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")</span><span class="sxs-lookup"><span data-stu-id="ebec5-147">![A page that can navigate to multiple pages](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure2.png "NavigationTopologyFigure2")</span></span>  
  
 <span data-ttu-id="ebec5-148">Questa struttura è detta topologia gerarchica fissa e la sequenza in cui viene attraversata è spesso determinata in fase di esecuzione dall'applicazione o dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="ebec5-149">In fase di esecuzione, ogni pagina della gerarchia che consente di spostarsi su due o più altre pagine raccoglie i dati richiesti per determinare su quale pagina spostarsi.</span><span class="sxs-lookup"><span data-stu-id="ebec5-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="ebec5-150">La figura seguente illustra una delle possibili sequenze di navigazione in base alla figura precedente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-150">The following figure illustrates one of several possible navigation sequences based on the previous figure.</span></span>  
  
 <span data-ttu-id="ebec5-151">![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")</span><span class="sxs-lookup"><span data-stu-id="ebec5-151">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure3.png "NavigationTopologyFigure3")</span></span>  
  
 <span data-ttu-id="ebec5-152">Anche se la sequenza di navigazione delle pagine in una struttura gerarchica fissa è determinata in fase di esecuzione, l'esperienza utente è la stessa di una topologia lineare fissa:</span><span class="sxs-lookup"><span data-stu-id="ebec5-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
-   <span data-ttu-id="ebec5-153">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="ebec5-154">La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="ebec5-155">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="ebec5-156">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="ebec5-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="ebec5-157">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-157">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="ebec5-158">Gli utenti possono modificare la sequenza di navigazione se tornano indietro tramite il journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
-   <span data-ttu-id="ebec5-159">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="ebec5-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="ebec5-160">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="ebec5-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="ebec5-161">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="ebec5-162">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="ebec5-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="ebec5-163">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="ebec5-164">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="ebec5-165">Navigazione in una topologia generata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="ebec5-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="ebec5-166">In alcune applicazioni la sequenza di navigazione di due o più pagine può essere determinata solo in fase di esecuzione dall'utente, dall'applicazione o da dati esterni.</span><span class="sxs-lookup"><span data-stu-id="ebec5-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="ebec5-167">La figura seguente illustra un insieme di pagine con una sequenza di navigazione non determinata.</span><span class="sxs-lookup"><span data-stu-id="ebec5-167">The following figure illustrates a set of pages with an undetermined navigation sequence.</span></span>  
  
 <span data-ttu-id="ebec5-168">![Diagramma della topologia di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")</span><span class="sxs-lookup"><span data-stu-id="ebec5-168">![Navigation topology diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure4.png "NavigationTopologyFigure4")</span></span>  
  
 <span data-ttu-id="ebec5-169">La figura seguente illustra una sequenza di navigazione scelta dall'utente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ebec5-169">The next figure illustrates a navigation sequence that was chosen by the user at run time.</span></span>  
  
 <span data-ttu-id="ebec5-170">![Diagramma di navigazione](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")</span><span class="sxs-lookup"><span data-stu-id="ebec5-170">![Navigation diagram](../../../../docs/framework/wpf/app-development/media/navigationtopologyfigure5.png "NavigationTopologyFigure5")</span></span>  
  
 <span data-ttu-id="ebec5-171">La sequenza di navigazione è indicata come topologia generata dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="ebec5-172">L'esperienza utente è analoga alle topologie di navigazione precedenti:</span><span class="sxs-lookup"><span data-stu-id="ebec5-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
-   <span data-ttu-id="ebec5-173">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="ebec5-174">La pagina di avvio (un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-minore <xref:System.Windows.Navigation.PageFunction%601>) non è necessaria, poiché è una pagina chiamante può chiamare la prima pagina della procedura guidata direttamente.</span><span class="sxs-lookup"><span data-stu-id="ebec5-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="ebec5-175">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="ebec5-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
-   <span data-ttu-id="ebec5-176">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="ebec5-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
-   <span data-ttu-id="ebec5-177">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-177">Users can navigate between pages using the journal.</span></span>  
  
-   <span data-ttu-id="ebec5-178">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="ebec5-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
-   <span data-ttu-id="ebec5-179">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="ebec5-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
-   <span data-ttu-id="ebec5-180">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
-   <span data-ttu-id="ebec5-181">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="ebec5-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
-   <span data-ttu-id="ebec5-182">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="ebec5-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="ebec5-183">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="ebec5-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebec5-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebec5-184">See Also</span></span>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.PageFunction%601>  
 <xref:System.Windows.Navigation.NavigationService>  
 [<span data-ttu-id="ebec5-185">Cenni preliminari sulla navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="ebec5-185">Structured Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)
