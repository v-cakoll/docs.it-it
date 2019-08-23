---
title: Cenni preliminari sulle topologie di navigazione
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: b62432d64393f4fb749af2e25c42e2e0161de219
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950741"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="d8948-102">Cenni preliminari sulle topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="d8948-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="d8948-103">In questa panoramica viene fornita un'introduzione alle topologie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]di navigazione in.</span><span class="sxs-lookup"><span data-stu-id="d8948-103">This overview provides an introduction to navigation topologies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="d8948-104">Di seguito vengono analizzate tre topologie di navigazione comuni con i relativi esempi.</span><span class="sxs-lookup"><span data-stu-id="d8948-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8948-105">Prima di leggere questo argomento, è necessario avere familiarità con il concetto di navigazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] strutturata nell'utilizzo delle funzioni di pagina.</span><span class="sxs-lookup"><span data-stu-id="d8948-105">Before reading this topic, you should be familiar with the concept of structured navigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] using page functions.</span></span> <span data-ttu-id="d8948-106">Per altre informazioni su entrambi gli argomenti, vedere [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8948-106">For more information on both of these topics, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="d8948-107">Di seguito sono elencate le diverse sezioni di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="d8948-107">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="d8948-108">Topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="d8948-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
- [<span data-ttu-id="d8948-109">Topologie di navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="d8948-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
- [<span data-ttu-id="d8948-110">Navigazione in una topologia lineare fissa</span><span class="sxs-lookup"><span data-stu-id="d8948-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [<span data-ttu-id="d8948-111">Navigazione dinamica in una topologia gerarchica fissa</span><span class="sxs-lookup"><span data-stu-id="d8948-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [<span data-ttu-id="d8948-112">Navigazione in una topologia generata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="d8948-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a><span data-ttu-id="d8948-113">Topologie di navigazione</span><span class="sxs-lookup"><span data-stu-id="d8948-113">Navigation Topologies</span></span>  
 <span data-ttu-id="d8948-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]la navigazione è in genere costituita<xref:System.Windows.Controls.Page>da pagine () con collegamenti<xref:System.Windows.Documents.Hyperlink>ipertestuali () che passano ad altre pagine quando si fa clic su di essa.</span><span class="sxs-lookup"><span data-stu-id="d8948-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="d8948-115">Le pagine che sono state spostate sono identificate da [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (vedere URI di [pacchetto in WPF](pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="d8948-115">Pages that are navigated to are identified by [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (see [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="d8948-116">Si consideri il semplice esempio seguente che mostra le pagine, i [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]collegamenti ipertestuali e:</span><span class="sxs-lookup"><span data-stu-id="d8948-116">Consider the following simple example that shows pages, hyperlinks, and [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="d8948-117">Queste pagine sono disposte in una topologia di *navigazione* la cui struttura è determinata dal modo in cui è possibile spostarsi tra le pagine.</span><span class="sxs-lookup"><span data-stu-id="d8948-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="d8948-118">Questa particolare topologia di navigazione è adatta in scenari semplici. La navigazione può tuttavia richiedere topologie più complesse, alcune delle quali possono essere definite solo quando un'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d8948-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="d8948-119">In questo argomento vengono illustrate tre topologie di navigazione comuni: *lineare fissa*, *gerarchica fissa*e *generata dinamicamente*.</span><span class="sxs-lookup"><span data-stu-id="d8948-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="d8948-120">Ogni topologia di navigazione viene illustrata con un esempio [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con un tipo simile a quello illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="d8948-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 ![Pagine di attività con elementi di dati e pulsanti di spostamento.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a><span data-ttu-id="d8948-122">Topologie di navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="d8948-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="d8948-123">Vi sono due topologie principali di navigazione:</span><span class="sxs-lookup"><span data-stu-id="d8948-123">There are two broad types of navigation topologies:</span></span>  
  
- <span data-ttu-id="d8948-124">**Topologia fissa**: è definita in fase di compilazione e non viene modificata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d8948-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="d8948-125">Le topologie fisse sono utili per la navigazione in una sequenza fissa di pagine in un ordine lineare o gerarchico.</span><span class="sxs-lookup"><span data-stu-id="d8948-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
- <span data-ttu-id="d8948-126">**Topologia dinamica**: è definita in fase di esecuzione in base agli input raccolti dall'utente, dall'applicazione o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="d8948-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="d8948-127">Le topologie dinamiche sono utili quando è possibile spostarsi sulle pagine in sequenze diverse.</span><span class="sxs-lookup"><span data-stu-id="d8948-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="d8948-128">Sebbene sia possibile creare topologie di navigazione usando le pagine, gli esempi usano funzioni di pagina poiché questi offrono un supporto aggiuntivo che semplifica il passaggio e la restituzione dei dati tramite le pagine di una topologia.</span><span class="sxs-lookup"><span data-stu-id="d8948-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="d8948-129">Navigazione in una topologia lineare fissa</span><span class="sxs-lookup"><span data-stu-id="d8948-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="d8948-130">Una topologia lineare fissa è analoga alla struttura di una procedura guidata con una o più pagine in cui ci si sposta in una sequenza fissa.</span><span class="sxs-lookup"><span data-stu-id="d8948-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="d8948-131">Nella figura seguente viene illustrata la struttura e il flusso di alto livello di una procedura guidata con una topologia lineare fissa:</span><span class="sxs-lookup"><span data-stu-id="d8948-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology:</span></span>  
  
 ![Diagramma che mostra una topologia lineare fissa.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 <span data-ttu-id="d8948-133">I comportamenti tipici per la navigazione in una topologia lineare fissa includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d8948-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
- <span data-ttu-id="d8948-134">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="d8948-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="d8948-135">Non è necessaria una pagina [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]di avvio <xref:System.Windows.Navigation.PageFunction%601>(a-less) perché una pagina chiamante può chiamare direttamente la prima pagina della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d8948-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="d8948-136">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="d8948-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="d8948-137">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="d8948-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="d8948-138">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-138">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="d8948-139">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="d8948-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="d8948-140">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="d8948-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="d8948-141">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="d8948-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="d8948-142">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d8948-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="d8948-143">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="d8948-144">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="d8948-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="d8948-145">Navigazione dinamica in una topologia gerarchica fissa</span><span class="sxs-lookup"><span data-stu-id="d8948-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="d8948-146">In alcune applicazioni, le pagine consentono la navigazione a due o più pagine, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="d8948-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure:</span></span> 
  
 ![Diagramma che mostra una pagina in grado di spostarsi su più pagine.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 <span data-ttu-id="d8948-148">Questa struttura è detta topologia gerarchica fissa e la sequenza in cui viene attraversata è spesso determinata in fase di esecuzione dall'applicazione o dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d8948-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="d8948-149">In fase di esecuzione, ogni pagina della gerarchia che consente di spostarsi su due o più altre pagine raccoglie i dati richiesti per determinare su quale pagina spostarsi.</span><span class="sxs-lookup"><span data-stu-id="d8948-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="d8948-150">Nella figura seguente viene illustrata una delle diverse sequenze di navigazione possibili in base alla figura precedente:</span><span class="sxs-lookup"><span data-stu-id="d8948-150">The following figure illustrates one of several possible navigation sequences based on the previous figure:</span></span>  
  
 ![Diagramma che mostra una possibile sequenza di navigazione.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 <span data-ttu-id="d8948-152">Anche se la sequenza di navigazione delle pagine in una struttura gerarchica fissa è determinata in fase di esecuzione, l'esperienza utente è la stessa di una topologia lineare fissa:</span><span class="sxs-lookup"><span data-stu-id="d8948-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
- <span data-ttu-id="d8948-153">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="d8948-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="d8948-154">Non è necessaria una pagina [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]di avvio <xref:System.Windows.Navigation.PageFunction%601>(a-less) perché una pagina chiamante può chiamare direttamente la prima pagina della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d8948-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="d8948-155">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="d8948-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="d8948-156">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="d8948-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="d8948-157">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-157">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="d8948-158">Gli utenti possono modificare la sequenza di navigazione se tornano indietro tramite il journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
- <span data-ttu-id="d8948-159">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="d8948-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="d8948-160">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="d8948-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="d8948-161">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="d8948-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="d8948-162">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d8948-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="d8948-163">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="d8948-164">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="d8948-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="d8948-165">Navigazione in una topologia generata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="d8948-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="d8948-166">In alcune applicazioni la sequenza di navigazione di due o più pagine può essere determinata solo in fase di esecuzione dall'utente, dall'applicazione o da dati esterni.</span><span class="sxs-lookup"><span data-stu-id="d8948-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="d8948-167">Nella figura seguente viene illustrato un set di pagine con una sequenza di navigazione non determinata:</span><span class="sxs-lookup"><span data-stu-id="d8948-167">The following figure illustrates a set of pages with an undetermined navigation sequence:</span></span>  
  
 ![Set di pagine con una sequenza di navigazione non determinata.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 <span data-ttu-id="d8948-169">Nella figura seguente viene illustrata una sequenza di navigazione scelta dall'utente in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="d8948-169">The next figure illustrates a navigation sequence that was chosen by the user at run time:</span></span>  
  
 ![Diagramma che mostra una sequenza di navigazione scelta in fase di esecuzione.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 <span data-ttu-id="d8948-171">La sequenza di navigazione è indicata come topologia generata dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="d8948-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="d8948-172">L'esperienza utente è analoga alle topologie di navigazione precedenti:</span><span class="sxs-lookup"><span data-stu-id="d8948-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
- <span data-ttu-id="d8948-173">Navigazione dalla pagina chiamante a una pagina di avvio che inizializza la procedura guidata e porta alla prima pagina di questa.</span><span class="sxs-lookup"><span data-stu-id="d8948-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="d8948-174">Non è necessaria una pagina [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]di avvio <xref:System.Windows.Navigation.PageFunction%601>(a-less) perché una pagina chiamante può chiamare direttamente la prima pagina della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d8948-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="d8948-175">L'uso di una pagina di avvio può tuttavia semplificare l'inizializzazione della procedura guidata, in particolare se questa è complessa.</span><span class="sxs-lookup"><span data-stu-id="d8948-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="d8948-176">Gli utenti possono spostarsi tra le pagine usando i pulsanti Avanti e Indietro (o i collegamenti ipertestuali).</span><span class="sxs-lookup"><span data-stu-id="d8948-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="d8948-177">Gli utenti possono spostarsi tra pagine usando il journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-177">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="d8948-178">Gli utenti possono annullare la procedura guidata da qualsiasi pagina di questa premendo il pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="d8948-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="d8948-179">Gli utenti possono accettare la procedura guidata all'ultima pagina premendo un pulsante Fine.</span><span class="sxs-lookup"><span data-stu-id="d8948-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="d8948-180">Se una procedura guidata viene annullata, questa restituisce un risultato appropriato e non restituisce alcun dato.</span><span class="sxs-lookup"><span data-stu-id="d8948-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="d8948-181">Se un utente accetta una procedura guidata, questa restituisce un risultato appropriato e restituisce i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d8948-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="d8948-182">Al completamento della procedura guidata (accettata o annullata), le pagine incluse nella procedura guidata vengono rimosse dal journal.</span><span class="sxs-lookup"><span data-stu-id="d8948-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="d8948-183">In questo modo ogni istanza della procedura guidata viene mantenuta isolata, per evitare potenziali anomalie di dati o stato.</span><span class="sxs-lookup"><span data-stu-id="d8948-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8948-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8948-184">See also</span></span>

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="d8948-185">Cenni preliminari sulla navigazione strutturata</span><span class="sxs-lookup"><span data-stu-id="d8948-185">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
