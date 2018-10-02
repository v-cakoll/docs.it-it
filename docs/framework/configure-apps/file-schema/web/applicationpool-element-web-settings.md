---
title: '&lt;applicationPool&gt; (impostazioni Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d5d6ee0b5153c734249e64a4d29f6621edcc61bf
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48046487"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="ce232-102">&lt;applicationPool&gt; (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="ce232-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="ce232-103">Specifica le impostazioni di configurazione che vengono utilizzate da ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET viene eseguito in modalità integrata in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ce232-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce232-104">Questo elemento e la funzionalità supporta funzionano solo se l'applicazione ASP.NET è ospitato in [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ce232-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="ce232-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce232-105">\<configuration></span></span>  
<span data-ttu-id="ce232-106">\<System. Web > (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="ce232-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="ce232-107">\<applicationPool > (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="ce232-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce232-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce232-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce232-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce232-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ce232-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce232-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce232-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce232-111">Attributes</span></span>  
  
|<span data-ttu-id="ce232-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="ce232-112">Attribute</span></span>|<span data-ttu-id="ce232-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce232-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="ce232-114">Specifica il numero di richieste simultaneo per CPU consentiti da ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ce232-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="ce232-115">Specifica può essere in esecuzione il numero di thread simultaneo per un pool di applicazioni per ogni CPU.</span><span class="sxs-lookup"><span data-stu-id="ce232-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="ce232-116">Ciò offre un modo alternativo per controllare la concorrenza ASP.NET, poiché è possibile limitare il numero di thread gestiti che può essere utilizzato per CPU per rispondere alle richieste.</span><span class="sxs-lookup"><span data-stu-id="ce232-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="ce232-117">Per impostazione predefinita questa impostazione è 0, che indica che ASP.NET non limita il numero di thread che possono essere creati per CPU, anche se il pool di thread CLR limita inoltre il numero di thread che possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="ce232-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="ce232-118">Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un unico processo.</span><span class="sxs-lookup"><span data-stu-id="ce232-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="ce232-119">Quando due o più applicazioni ASP.NET eseguite in un singolo pool di applicazioni, il set cumulativo di richieste inoltrate a tutte le applicazioni nel pool di applicazioni è soggetto a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="ce232-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce232-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce232-120">Child Elements</span></span>  
 <span data-ttu-id="ce232-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ce232-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce232-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce232-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ce232-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce232-123">Element</span></span>|<span data-ttu-id="ce232-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce232-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce232-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="ce232-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="ce232-126">Contiene informazioni su come ASP.NET interagisce con un'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="ce232-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce232-127">Note</span><span class="sxs-lookup"><span data-stu-id="ce232-127">Remarks</span></span>  
 <span data-ttu-id="ce232-128">Quando si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare come ASP.NET gestisce le richieste di thread e le code quando l'applicazione è ospitata in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="ce232-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="ce232-129">Se si esegue IIS 6 o [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in modalità classica o in modalità ISAPI, queste impostazioni verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="ce232-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="ce232-130">Il `applicationPool` impostazioni si applicano a tutti i pool di applicazioni in esecuzione su una particolare versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce232-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="ce232-131">Le impostazioni sono contenute in un file ASPNET config.</span><span class="sxs-lookup"><span data-stu-id="ce232-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="ce232-132">È disponibile una versione di questo file per le versioni 2.0 e 4.0 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce232-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="ce232-133">(Le versioni 3.0 e 3.5 di .NET Framework condividono file Aspnet. config con la versione 2.0).</span><span class="sxs-lookup"><span data-stu-id="ce232-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce232-134">Se si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] su [!INCLUDE[win7](../../../../../includes/win7-md.md)], è possibile configurare un file Aspnet. config separato per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce232-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="ce232-135">Ciò consente di adattare le prestazioni dei thread per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce232-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="ce232-136">Per il `maxConcurrentRequestsPerCPU` impostazione, l'impostazione predefinita pari a "5000" nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in modo efficace consente di disattivare la limitazione delle richieste controllata da ASP.NET, a meno che non si hanno effettivamente le richieste di più di 5000 per ogni CPU.</span><span class="sxs-lookup"><span data-stu-id="ce232-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="ce232-137">L'impostazione predefinita invece dipende il pool di thread CLR per gestire automaticamente la concorrenza per ogni CPU.</span><span class="sxs-lookup"><span data-stu-id="ce232-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="ce232-138">Le applicazioni che fanno largo uso dell'elaborazione della richiesta asincrona, o che presentano molte richieste a esecuzione prolungata bloccate nella rete i/o, potranno usufruire di aumento del limite predefinito nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce232-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="ce232-139">Impostazione `maxConcurrentRequestsPerCPU` su zero disattiva l'utilizzo di thread gestiti per l'elaborazione delle richieste ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ce232-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="ce232-140">Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste di restare sempre aggiornato riguardo il thread dei / o IIS e pertanto la concorrenza è limitata dalle impostazioni di thread IIS.</span><span class="sxs-lookup"><span data-stu-id="ce232-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="ce232-141">Il `requestQueueLimit` impostazione funziona esattamente come i `requestQueueLimit` attributo delle [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) elemento, che è impostato nei file Web. config per applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ce232-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="ce232-142">Tuttavia, il `requestQueueLimit` impostazione in un file ASPNET sostituisce il `requestQueueLimit` impostazione in un file Web. config.</span><span class="sxs-lookup"><span data-stu-id="ce232-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="ce232-143">In altre parole, se sono impostati entrambi gli attributi (per impostazione predefinita, questo è true), il `requestQueueLimit` impostazione nel file ASPNET ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="ce232-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce232-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce232-144">Example</span></span>  
 <span data-ttu-id="ce232-145">Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo ASP.NET nel file Aspnet. config nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce232-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="ce232-146">L'applicazione è ospitata un [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ce232-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] <span data-ttu-id="ce232-147">è in esecuzione in modalità integrata.</span><span class="sxs-lookup"><span data-stu-id="ce232-147"> is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="ce232-148">L'applicazione usa il [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="ce232-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="ce232-149">I valori nell'esempio sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ce232-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="ce232-150">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="ce232-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce232-151">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ce232-151">Namespace</span></span>||  
|<span data-ttu-id="ce232-152">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="ce232-152">Schema Name</span></span>||  
|<span data-ttu-id="ce232-153">File di convalida</span><span class="sxs-lookup"><span data-stu-id="ce232-153">Validation File</span></span>||  
|<span data-ttu-id="ce232-154">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="ce232-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="ce232-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce232-155">See Also</span></span>  
 [<span data-ttu-id="ce232-156">Elemento \<system.web> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="ce232-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
