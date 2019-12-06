---
title: Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: cf5ea345c900dec0e4859d81fcb272c1ba3d3df6
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837753"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="50521-102">Strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="50521-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="50521-103">Lo strumento di registrazione dei servizi di Windows Workflow (WFServicesReg.exe) è un strumento autonomo che può essere utilizzato per aggiungere, rimuovere o ripristinare gli elementi di configurazione per i servizi Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="50521-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50521-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50521-104">Syntax</span></span>  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="50521-105">Note</span><span class="sxs-lookup"><span data-stu-id="50521-105">Remarks</span></span>  
 <span data-ttu-id="50521-106">Lo strumento si trova nel percorso di installazione di .NET Framework 3,5, in particolare%windir%\Microsoft.NET\Framework\v3.5 o in%windir%\Microsoft.NET\Framework64\v3.5 in computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="50521-106">The tool can be found at the .NET Framework 3.5 installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="50521-107">Nelle tabelle riportate di seguito vengono illustrate le opzioni che è possibile utilizzare con lo strumento di registrazione dei servizi di Windows Workflow.</span><span class="sxs-lookup"><span data-stu-id="50521-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="50521-108">Opzione</span><span class="sxs-lookup"><span data-stu-id="50521-108">Option</span></span>|<span data-ttu-id="50521-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50521-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="50521-110">Configura i servizi di Windows Workflow.</span><span class="sxs-lookup"><span data-stu-id="50521-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="50521-111">Utilizzato in scenari di installazione e ripristino.</span><span class="sxs-lookup"><span data-stu-id="50521-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="50521-112">Rimuove la configurazione dei servizi di Windows Workflow.</span><span class="sxs-lookup"><span data-stu-id="50521-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="50521-113">Stampare informazioni dettagliate (per configurazione o rimozione).</span><span class="sxs-lookup"><span data-stu-id="50521-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="50521-114">Abilita formato di registrazione di MSI.</span><span class="sxs-lookup"><span data-stu-id="50521-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="50521-115">Riduce a icona la finestra durante l' esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="50521-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="50521-116">Registrazione</span><span class="sxs-lookup"><span data-stu-id="50521-116">Registration</span></span>  
 <span data-ttu-id="50521-117">Lo strumento controlla il file Web.config e registra gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="50521-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- <span data-ttu-id="50521-118">.NET Framework 3,5 assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="50521-118">.NET Framework 3.5 reference assemblies.</span></span>  
  
- <span data-ttu-id="50521-119">Provider di compilazione per i file .xoml.</span><span class="sxs-lookup"><span data-stu-id="50521-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="50521-120">Gestori HTTP per .xoml e file .rules.</span><span class="sxs-lookup"><span data-stu-id="50521-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="50521-121">Lo strumento controlla il file Machine.config e registra le estensioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50521-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="50521-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="50521-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="50521-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="50521-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="50521-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="50521-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="50521-125">Lo strumento regista inoltre le utilità di importazione dei metadati client seguenti:</span><span class="sxs-lookup"><span data-stu-id="50521-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="50521-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="50521-126">policyImporters</span></span>  
  
- <span data-ttu-id="50521-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="50521-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="50521-128">Lo strumento registra inoltre scriptmap e gestori .xoml e .rules nella metabase IIS.</span><span class="sxs-lookup"><span data-stu-id="50521-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="50521-129">Nei computer [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../includes/wxp-md.md)] (IIS 5,1 e IIS 6,0), viene registrato un set di scriptmap. xoml e. Rules.</span><span class="sxs-lookup"><span data-stu-id="50521-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and IIS 6.0), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="50521-130">In computer a 64 bit lo strumento registra scriptmap di modalità WOW, se l'opzione `Enable32BitAppOnWin64` è abilitata, o scriptmap a 64 bit nativi, se l'opzione `Enable32BitAppOnWin64` è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="50521-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="50521-131">Nei computer con Windows Vista e Windows Server 2008 (IIS 7,0 e versioni successive) sono registrati due set di gestori xoml e Rules: uno per la modalità integrata e uno per la modalità classica.</span><span class="sxs-lookup"><span data-stu-id="50521-131">On Windows Vista and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="50521-132">In computer a 64 bit sono registrati tre set di gestori (indipendentemente dallo stato dell'opzione `Enable32BitAppOnWin64`): uno per la modalità integrata, uno per la modalità classica WOW e uno per la modalità classica a 64 bit nativa.</span><span class="sxs-lookup"><span data-stu-id="50521-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50521-133">A differenza di ServiceModelreg.exe, WFServicesReg.exe non consente di aggiungere, rimuovere o ripristinare scriptmap o gestori per un particolare sito Web.</span><span class="sxs-lookup"><span data-stu-id="50521-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="50521-134">Per una soluzione alternativa a questo problema, vedere la sezione "Ripristino di scriptmap".</span><span class="sxs-lookup"><span data-stu-id="50521-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="50521-135">Utilizzo di scenari</span><span class="sxs-lookup"><span data-stu-id="50521-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="50521-136">Installazione di IIS dopo l'installazione di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="50521-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="50521-137">In un computer [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .NET Framework 3,5 viene installato prima dell'installazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="50521-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .NET Framework 3.5 is installed prior to IIS installation.</span></span> <span data-ttu-id="50521-138">A causa dell'indisponibilità della metabase IIS, l'installazione di .NET Framework 3,5 riesce senza installare gli scriptmap. xoml e. Rules.</span><span class="sxs-lookup"><span data-stu-id="50521-138">Due to the unavailability of the IIS metabase, installation of .NET Framework 3.5 succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="50521-139">Al termine dell'installazione di IIS, è possibile utilizzare lo strumento WFServicesReg.exe con l'opzione `/c` per installare questi scriptmap specifici.</span><span class="sxs-lookup"><span data-stu-id="50521-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="50521-140">Ripristino di scriptmap</span><span class="sxs-lookup"><span data-stu-id="50521-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="50521-141">Eliminazione di scriptmap nel nodo Siti Web</span><span class="sxs-lookup"><span data-stu-id="50521-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="50521-142">In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato dal nodo Siti Web.</span><span class="sxs-lookup"><span data-stu-id="50521-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="50521-143">Può essere ripristinato eseguendo lo strumento WFServicesReg.exe con l'opzione `/c`.</span><span class="sxs-lookup"><span data-stu-id="50521-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="50521-144">Eliminazione di scriptmap in un particolare sito Web</span><span class="sxs-lookup"><span data-stu-id="50521-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="50521-145">In un computer con sistema [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .xoml o .rules viene accidentalmente eliminato da un particolare sito Web (ad esempio il sito Web predefinito) piuttosto che dal nodo Siti Web.</span><span class="sxs-lookup"><span data-stu-id="50521-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="50521-146">Per ripristinare i gestori eliminati per un particolare sito Web, è necessario eseguire "WFServicesReg. exe/r" per rimuovere i gestori da tutti i siti Web, quindi eseguire "WFServicesReg. exe/c" per creare i gestori appropriati per tutti i siti Web.</span><span class="sxs-lookup"><span data-stu-id="50521-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="50521-147">Configurazione dei gestori dopo il cambio di modalità di IIS</span><span class="sxs-lookup"><span data-stu-id="50521-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="50521-148">Quando IIS è in modalità di configurazione condivisa e viene installato .NET Framework 3,5, la metabase IIS viene configurata in un percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="50521-148">When IIS is in shared configuration mode and .NET Framework 3.5 is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="50521-149">Se si passa IIS a una modalità di configurazione non-condivisa, la metabase locale non conterrà i gestori necessari.</span><span class="sxs-lookup"><span data-stu-id="50521-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="50521-150">Per configurare correttamente la metabase locale, è possibile importare la metabase condivisa in locale oppure eseguire "WFServicesReg. exe/c", che configura la metabase locale.</span><span class="sxs-lookup"><span data-stu-id="50521-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
