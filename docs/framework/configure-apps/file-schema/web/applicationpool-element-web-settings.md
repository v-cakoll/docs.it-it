---
title: Elemento <applicationPool> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152854"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="c1117-102">\<Elemento applicationPool> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="c1117-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="c1117-103">Specifica le impostazioni di configurazione utilizzate dai ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET è in esecuzione in modalità integrata in IIS 7.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c1117-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c1117-104">Questo elemento e la funzionalità che supporta funzionano solo se l'applicazione ASP.NET è ospitata in IIS 7.0 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c1117-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="c1117-105">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="c1117-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c1117-106">&nbsp;&nbsp;[**\<>system.web**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c1117-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="c1117-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<>applicationPool**</span><span class="sxs-lookup"><span data-stu-id="c1117-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1117-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1117-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1117-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c1117-109">Attributes and Elements</span></span>  

<span data-ttu-id="c1117-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c1117-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1117-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="c1117-111">Attributes</span></span>  
  
|<span data-ttu-id="c1117-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c1117-112">Attribute</span></span>|<span data-ttu-id="c1117-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1117-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="c1117-114">Specifica il numero di richieste simultanee ASP.NET consentite per CPU.</span><span class="sxs-lookup"><span data-stu-id="c1117-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="c1117-115">Specifica il numero di thread simultanei che possono essere in esecuzione per un pool di applicazioni per ogni CPU.</span><span class="sxs-lookup"><span data-stu-id="c1117-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="c1117-116">Ciò fornisce un modo alternativo per controllare ASP.NET concorrenza, perché è possibile limitare il numero di thread gestiti che possono essere utilizzati per ogni CPU per gestire le richieste.</span><span class="sxs-lookup"><span data-stu-id="c1117-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="c1117-117">Per impostazione predefinita, questa impostazione è 0, il che significa che ASP.NET non limita il numero di thread che possono essere creati per CPU, anche se il pool di thread CLR limita anche il numero di thread che possono essere creati.</span><span class="sxs-lookup"><span data-stu-id="c1117-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="c1117-118">Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="c1117-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="c1117-119">Quando due o più applicazioni ASP.NET vengono eseguite in un singolo pool di applicazioni, il set cumulativo di richieste effettuate a qualsiasi applicazione nel pool di applicazioni è soggetto a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="c1117-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1117-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c1117-120">Child Elements</span></span>  
 <span data-ttu-id="c1117-121">No.</span><span class="sxs-lookup"><span data-stu-id="c1117-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1117-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c1117-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c1117-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1117-123">Element</span></span>|<span data-ttu-id="c1117-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1117-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1117-125">\<>system.web</span><span class="sxs-lookup"><span data-stu-id="c1117-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="c1117-126">Contiene informazioni sull'interazione dei ASP.NET con un'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="c1117-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1117-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1117-127">Remarks</span></span>  

<span data-ttu-id="c1117-128">Quando si esegue IIS 7.0 o versione successiva in modalità integrata, questa combinazione di elementi consente di configurare la modalità di gestione delle richieste di thread e code ASP.NET quando l'applicazione è ospitata in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="c1117-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="c1117-129">Se si esegue IIS 6 o si esegue IIS 7.0 in modalità classica o in modalità ISAPI, queste impostazioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="c1117-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="c1117-130">Le `applicationPool` impostazioni si applicano a tutti i pool di applicazioni eseguiti in una particolare versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1117-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="c1117-131">Le impostazioni sono contenute in un file aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="c1117-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="c1117-132">Esiste una versione di questo file per le versioni 2.0 e 4.0 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1117-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="c1117-133">Le versioni 3.0 e 3.5 di .NET Framework condividono il file aspnet.config con la versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1117-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c1117-134">Se si esegue IIS 7.0 in Windows 7, è possibile configurare un file aspnet.config separato per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c1117-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="c1117-135">In questo modo è possibile personalizzare le prestazioni dei thread per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c1117-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="c1117-136">Per `maxConcurrentRequestsPerCPU` l'impostazione, l'impostazione predefinita di "5000" in .NET Framework 4 disattiva in modo efficace la limitazione delle richieste controllata da ASP.NET, a meno che non si disponga effettivamente di 5000 o più richieste per CPU.</span><span class="sxs-lookup"><span data-stu-id="c1117-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="c1117-137">L'impostazione predefinita dipende invece dal pool di thread CLR per gestire automaticamente la concorrenza per CPU.</span><span class="sxs-lookup"><span data-stu-id="c1117-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="c1117-138">Le applicazioni che fanno ampio uso dell'elaborazione delle richieste asincrone o che hanno molte richieste a esecuzione prolungata bloccate sull'I/O di rete, trarranno vantaggio dall'aumento del limite predefinito in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c1117-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="c1117-139">L'impostazione `maxConcurrentRequestsPerCPU` su zero disattiva l'utilizzo dei thread gestiti per l'elaborazione delle richieste ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c1117-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="c1117-140">Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste rimangono nel thread di I/O iIS e pertanto la concorrenza viene limitata dalle impostazioni del thread IIS.</span><span class="sxs-lookup"><span data-stu-id="c1117-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="c1117-141">L'impostazione `requestQueueLimit` funziona allo `requestQueueLimit` stesso modo dell'attributo dell'elemento [processModel,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) impostato nei file Web.config per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c1117-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="c1117-142">Tuttavia, `requestQueueLimit` l'impostazione in un file `requestQueueLimit` aspnet.config esegue l'override dell'impostazione in un file Web.config.</span><span class="sxs-lookup"><span data-stu-id="c1117-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="c1117-143">In altre parole, se entrambi gli attributi sono impostati (per impostazione predefinita, questo è vero), l'impostazione `requestQueueLimit` nel file aspnet.config ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1117-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1117-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1117-144">Example</span></span>  

<span data-ttu-id="c1117-145">Nell'esempio seguente viene illustrato come configurare ASP.NET comportamento a livello di processo nel file aspnet.config nelle seguenti circostanze:</span><span class="sxs-lookup"><span data-stu-id="c1117-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="c1117-146">L'applicazione è ospitata in un pool di applicazioni IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="c1117-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="c1117-147">IIS 7.0 è in esecuzione in modalità integrata.</span><span class="sxs-lookup"><span data-stu-id="c1117-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="c1117-148">L'applicazione utilizza .NET Framework 3.5 SP1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c1117-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="c1117-149">I valori nell'esempio sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c1117-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="c1117-150">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="c1117-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1117-151">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c1117-151">Namespace</span></span>||  
|<span data-ttu-id="c1117-152">Schema Name</span><span class="sxs-lookup"><span data-stu-id="c1117-152">Schema Name</span></span>||  
|<span data-ttu-id="c1117-153">File di convalida</span><span class="sxs-lookup"><span data-stu-id="c1117-153">Validation File</span></span>||  
|<span data-ttu-id="c1117-154">Può essere Vuoto</span><span class="sxs-lookup"><span data-stu-id="c1117-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c1117-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1117-155">See also</span></span>

- [<span data-ttu-id="c1117-156">\<elemento> system.web (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="c1117-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
