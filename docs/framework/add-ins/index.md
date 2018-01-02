---
title: "Componenti aggiuntivi ed estensibilità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e4d336992be216178b1237c9f43bffb3de61fba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="5e1eb-102">Componenti aggiuntivi ed estensibilità</span><span class="sxs-lookup"><span data-stu-id="5e1eb-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="5e1eb-103">I componenti aggiuntivi forniscono funzionalità o servizi estesi per un'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="5e1eb-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] offre un modello di programmazione che gli sviluppatori possono usare per sviluppare componenti aggiuntivi e attivarli nella propria applicazione host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="5e1eb-105">Ciò avviene attraverso la costruzione di una pipeline di comunicazione tra l'host e il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="5e1eb-106">Il modello viene implementato usando i tipi inclusi negli spazi dei nomi <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>e <xref:System.AddIn.Contract> .</span><span class="sxs-lookup"><span data-stu-id="5e1eb-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="5e1eb-107">In questa panoramica sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e1eb-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="5e1eb-108">Modello dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="5e1eb-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="5e1eb-109">Distinzione tra componenti aggiuntivi e host</span><span class="sxs-lookup"><span data-stu-id="5e1eb-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="5e1eb-110">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5e1eb-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="5e1eb-111">Riferimento</span><span class="sxs-lookup"><span data-stu-id="5e1eb-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="5e1eb-112">Altro codice di esempio e alcuni strumenti per la compilazione di pipeline dei componenti aggiuntivi in versione Customer Technology Preview sono disponibili nel [sito del framework di estendibilità gestita e dei componenti aggiuntivi su CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="5e1eb-113">Modello dei componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="5e1eb-113">Add-in Model</span></span>  
 <span data-ttu-id="5e1eb-114">Il modello dei componenti aggiuntivi consiste in una serie di segmenti che costituiscono la pipeline del componente aggiuntivo, chiamata anche pipeline di comunicazione, responsabile di tutta la comunicazione tra il componente aggiuntivo e l'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="5e1eb-115">La pipeline è un modello di comunicazione simmetrico di segmenti che scambia dati tra un componente aggiuntivo e il relativo host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="5e1eb-116">Lo sviluppo di questi segmenti tra l'host e il componente aggiuntivo fornisce i livelli di astrazione necessari per il supporto del controllo delle versioni e l'isolamento del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="5e1eb-117">L'illustrazione seguente mostra la pipeline.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="5e1eb-118">![Aggiungi &#45; nel modello di pipeline. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="5e1eb-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="5e1eb-119">Pipeline del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="5e1eb-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="5e1eb-120">Gli assembly per questi segmenti non devono trovarsi nello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="5e1eb-121">È possibile caricare un componente aggiuntivo nel suo nuovo dominio applicazione, in uno esistente o persino in quello dell'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="5e1eb-122">È possibile caricare più componenti aggiuntivi nello stesso dominio applicazione, in modo che condividano le risorse e i contesti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="5e1eb-123">Il modello dei componenti aggiuntivi supporta, e consiglia, un limite facoltativo tra l'host e il componente aggiuntivo, chiamato limite di isolamento (o anche limite remoto).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="5e1eb-124">Questo limite può essere un dominio applicazione o un limite di processo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="5e1eb-125">Il segmento dei contratti al centro della pipeline viene caricato sia nel dominio applicazione dell'host sia in quello del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="5e1eb-126">Il contratto definisce i metodi virtuali usati dall'host e dal componente aggiuntivo per scambiare tipi l'uno con l'altro.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="5e1eb-127">Per attraversare il limite di isolamento, i tipi devono essere contratti o tipi serializzabili.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="5e1eb-128">I tipi che non sono contratti o tipi serializzabili devono essere convertiti in contratti dai segmenti degli adattatori nella pipeline.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="5e1eb-129">I segmenti delle visualizzazioni della pipeline sono classi di base astratte o interfacce che forniscono all'host e al componente aggiuntivo una visualizzazione dei metodi che condividono, definiti dal contratto.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="5e1eb-130">Per altre informazioni sullo sviluppo di segmenti della pipeline, vedere [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="5e1eb-131">Le sezioni seguenti descrivono le funzionalità del modello dei componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="5e1eb-132">Controllo delle versioni indipendente</span><span class="sxs-lookup"><span data-stu-id="5e1eb-132">Independent Versioning</span></span>  
 <span data-ttu-id="5e1eb-133">Il modello dei componenti aggiuntivi permette agli host e ai componenti aggiuntivi di eseguire il controllo delle versioni in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="5e1eb-134">Di conseguenza, il modello permette gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e1eb-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="5e1eb-135">Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per una versione precedente dell'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="5e1eb-136">Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per una versione successiva dell'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="5e1eb-137">Creazione di un adattatore che permette a un host di usare un componente aggiuntivo creato per un host diverso.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="5e1eb-138">Individuazione e attivazione</span><span class="sxs-lookup"><span data-stu-id="5e1eb-138">Discovery and Activation</span></span>  
 <span data-ttu-id="5e1eb-139">È possibile attivare un componente aggiuntivo usando un token da una raccolta che rappresenta i componenti aggiuntivi trovati in un archivio di informazioni.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="5e1eb-140">Per trovare i componenti aggiuntivi, è necessario cercare il tipo che definisce la visualizzazione dell'host del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="5e1eb-141">È possibile trovare un componente aggiuntivo anche in base al tipo che lo definisce.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="5e1eb-142">L'archivio di informazioni è costituito da due file di cache: l'archivio della pipeline e l'archivio del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="5e1eb-143">Per informazioni sull'aggiornamento e la ricompilazione dell'archivio di informazioni, vedere [Individuazione di componenti aggiuntivi](http://msdn.microsoft.com/en-us/5d268dde-11df-4c4d-a022-f58d88bbc421).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-143">For information about updating and rebuilding the information store, see [Add-in Discovery](http://msdn.microsoft.com/en-us/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="5e1eb-144">Per informazioni sull'attivazione dei componenti aggiuntivi, vedere [Attivazione di componenti aggiuntivi](http://msdn.microsoft.com/en-us/bedcbcdf-5964-4215-b5f3-3299798b2b3f) e [Procedura: attivare componenti aggiuntivi con isolamento e sicurezza diversi](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-144">For information about activating add-ins, see [Add-in Activation](http://msdn.microsoft.com/en-us/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="5e1eb-145">Livelli di isolamento e processi esterni</span><span class="sxs-lookup"><span data-stu-id="5e1eb-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="5e1eb-146">Il modello dei componenti aggiuntivi supporta diversi livelli di isolamento tra il componente aggiuntivo e il relativo host o tra componenti aggiuntivi diversi. Partendo dal meno isolato, i livelli sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e1eb-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="5e1eb-147">Il componente aggiuntivo viene eseguito nello stesso dominio applicazione dell'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="5e1eb-148">Questo livello non è consigliato, perché comporta la perdita delle funzionalità di isolamento e scaricamento ottenute usando domini applicazione diversi.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="5e1eb-149">Più componenti aggiuntivi vengono caricati nello stesso dominio applicazione, che è diverso da quello usato dall'host.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="5e1eb-150">Ogni componente aggiuntivo viene caricato in modo esclusivo nel proprio dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="5e1eb-151">Questo è il livello di isolamento più comune.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="5e1eb-152">Più componenti aggiuntivi vengono caricati nello stesso dominio applicazione in un processo esterno.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="5e1eb-153">Ogni componente aggiuntivo viene caricato in modo esclusivo nel proprio dominio applicazione in un processo esterno.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="5e1eb-154">Questo è lo scenario più isolato.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="5e1eb-155">Per altre informazioni sull'uso di processi esterni, vedere [Procedura: attivare componenti aggiuntivi con isolamento e sicurezza diversi](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/en-us/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="5e1eb-156">Gestione della durata</span><span class="sxs-lookup"><span data-stu-id="5e1eb-156">Lifetime Management</span></span>  
 <span data-ttu-id="5e1eb-157">Poiché il modello dei componenti aggiuntivi si estende oltre i limiti del dominio applicazione e del processo, Garbage Collection non è in sé sufficiente per rilasciare e recuperare oggetti.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="5e1eb-158">Il modello dei componenti aggiuntivi offre un meccanismo di gestione della durata che usa token e conteggio dei riferimenti e che in genere non richiede programmazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="5e1eb-159">Per altre informazioni, vedere [Gestione della durata](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="5e1eb-159">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="5e1eb-160">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="5e1eb-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="5e1eb-161">Distinzione tra componenti aggiuntivi e host</span><span class="sxs-lookup"><span data-stu-id="5e1eb-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="5e1eb-162">La differenza tra un componente aggiuntivo e un host consiste semplicemente nel fatto che l'host è quello che attiva il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="5e1eb-163">L'host può essere il più grande dei due, ad esempio un'applicazione di elaborazione di testo e i suoi correttori ortografici, oppure può essere anche il più piccolo dei due, ad esempio un client di messaggistica immediata che incorpora un lettore multimediale.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="5e1eb-164">Il modello dei componenti aggiuntivi supporta componenti aggiuntivi in scenari client e server.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="5e1eb-165">Esempi di componenti aggiuntivi server includono i componenti aggiuntivi che forniscono server di posta elettronica con ricerca di virus, filtri antispam e protezione IP.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="5e1eb-166">Esempi di componenti aggiuntivi client includono componenti aggiuntivi di riferimento per elaboratori di testo, funzionalità specializzate per programmi di grafica e giochi e ricerca di virus per client di posta elettronica locali.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local e-mail clients.</span></span>  
  
 [<span data-ttu-id="5e1eb-167">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="5e1eb-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="5e1eb-168">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5e1eb-168">Related Topics</span></span>  
  
|<span data-ttu-id="5e1eb-169">Titolo</span><span class="sxs-lookup"><span data-stu-id="5e1eb-169">Title</span></span>|<span data-ttu-id="5e1eb-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e1eb-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5e1eb-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="5e1eb-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="5e1eb-172">Descrive la pipeline di comunicazione dei segmenti dall'applicazione host al componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="5e1eb-173">Fornisce esempi di codice in argomenti con procedure dettagliate che descrivono come costruire la pipeline e implementare segmenti nella pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e1eb-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>|  
|[<span data-ttu-id="5e1eb-174">Domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="5e1eb-174">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="5e1eb-175">Descrive la relazione tra domini applicazione, che forniscono un limite di isolamento per sicurezza, affidabilità e controllo delle versioni, e assembly.</span><span class="sxs-lookup"><span data-stu-id="5e1eb-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="5e1eb-176">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="5e1eb-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="5e1eb-177">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5e1eb-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="5e1eb-178">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="5e1eb-178">Back to top</span></span>](#top)