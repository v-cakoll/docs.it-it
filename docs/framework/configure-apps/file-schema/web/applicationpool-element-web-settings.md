---
title: Elemento <applicationPool> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 9783844ff0fe719b0581c1c9e1fb96eb31933b89
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801866"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="24c5e-102">\<elemento > applicationPool (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="24c5e-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="24c5e-103">Specifica le impostazioni di configurazione usate da ASP.NET per gestire il comportamento a livello di processo quando un'applicazione ASP.NET è in esecuzione in modalità integrata in IIS 7,0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="24c5e-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="24c5e-104">Questo elemento e la funzionalità che supporta funzionano solo se l'applicazione ASP.NET è ospitata in IIS 7,0 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="24c5e-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="24c5e-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="24c5e-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="24c5e-106">&nbsp;&nbsp;[ **\<> System. Web**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="24c5e-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="24c5e-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<applicationPool >**</span><span class="sxs-lookup"><span data-stu-id="24c5e-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c5e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24c5e-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24c5e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24c5e-109">Attributes and Elements</span></span>  

<span data-ttu-id="24c5e-110">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24c5e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24c5e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="24c5e-111">Attributes</span></span>  
  
|<span data-ttu-id="24c5e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="24c5e-112">Attribute</span></span>|<span data-ttu-id="24c5e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24c5e-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="24c5e-114">Specifica il numero di richieste simultanee consentite da ASP.NET per CPU.</span><span class="sxs-lookup"><span data-stu-id="24c5e-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="24c5e-115">Specifica il numero di thread simultanei che possono essere in esecuzione per un pool di applicazioni per ogni CPU.</span><span class="sxs-lookup"><span data-stu-id="24c5e-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="24c5e-116">Si tratta di un metodo alternativo per controllare la concorrenza ASP.NET, in quanto è possibile limitare il numero di thread gestiti che possono essere usati per CPU per gestire le richieste.</span><span class="sxs-lookup"><span data-stu-id="24c5e-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="24c5e-117">Per impostazione predefinita, questa impostazione è 0, il che significa che ASP.NET non limita il numero di thread che possono essere creati per CPU, anche se il pool di thread CLR limita anche il numero di thread che è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="24c5e-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="24c5e-118">Specifica il numero massimo di richieste che possono essere accodate per ASP.NET in un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="24c5e-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="24c5e-119">Quando due o più applicazioni ASP.NET vengono eseguite in un unico pool di applicazioni, il set cumulativo di richieste effettuate a qualsiasi applicazione nel pool di applicazioni è soggetto a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="24c5e-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24c5e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24c5e-120">Child Elements</span></span>  
 <span data-ttu-id="24c5e-121">nessuna.</span><span class="sxs-lookup"><span data-stu-id="24c5e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24c5e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24c5e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="24c5e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="24c5e-123">Element</span></span>|<span data-ttu-id="24c5e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24c5e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24c5e-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="24c5e-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="24c5e-126">Contiene informazioni sul modo in cui ASP.NET interagisce con un'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="24c5e-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24c5e-127">Note</span><span class="sxs-lookup"><span data-stu-id="24c5e-127">Remarks</span></span>  

<span data-ttu-id="24c5e-128">Quando si esegue IIS 7,0 o una versione successiva in modalità integrata, questa combinazione di elementi consente di configurare il modo in cui ASP.NET gestisce i thread e le richieste di Accodamento quando l'applicazione è ospitata in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="24c5e-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="24c5e-129">Se si esegue IIS 6 oppure si esegue IIS 7,0 in modalità classica o in modalità ISAPI, queste impostazioni verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="24c5e-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="24c5e-130">Le impostazioni `applicationPool` si applicano a tutti i pool di applicazioni eseguiti in una determinata versione del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24c5e-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="24c5e-131">Le impostazioni sono contenute in un file Aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="24c5e-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="24c5e-132">Esiste una versione di questo file per le versioni 2,0 e 4,0 del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24c5e-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="24c5e-133">(Le versioni 3,0 e 3,5 del .NET Framework condividono il file Aspnet. config con la versione 2,0).</span><span class="sxs-lookup"><span data-stu-id="24c5e-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="24c5e-134">Se si esegue IIS 7,0 in Windows 7, è possibile configurare un file Aspnet. config separato per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="24c5e-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="24c5e-135">In questo modo è possibile personalizzare le prestazioni dei thread per ogni pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="24c5e-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="24c5e-136">Per l'impostazione di `maxConcurrentRequestsPerCPU`, l'impostazione predefinita di "5000" nella .NET Framework 4 Disattiva in modo efficace la limitazione delle richieste controllata da ASP.NET, a meno che non siano effettivamente presenti 5000 o più richieste per CPU.</span><span class="sxs-lookup"><span data-stu-id="24c5e-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="24c5e-137">L'impostazione predefinita dipende invece dal pool di thread CLR per la gestione automatica della concorrenza per CPU.</span><span class="sxs-lookup"><span data-stu-id="24c5e-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="24c5e-138">Le applicazioni che usano in modo esteso l'elaborazione di richieste asincrone o con numerose richieste a esecuzione prolungata bloccate sull'I/O di rete trarranno vantaggio dall'aumento del limite predefinito nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="24c5e-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="24c5e-139">Impostando `maxConcurrentRequestsPerCPU` su zero si disattiva l'uso di thread gestiti per l'elaborazione delle richieste ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="24c5e-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="24c5e-140">Quando un'applicazione viene eseguita in un pool di applicazioni IIS, le richieste vengono mantenute nel thread di I/O di IIS e pertanto la concorrenza è limitata dalle impostazioni del thread IIS.</span><span class="sxs-lookup"><span data-stu-id="24c5e-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="24c5e-141">L'impostazione `requestQueueLimit` funziona allo stesso modo dell'attributo `requestQueueLimit` dell'elemento [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , che viene impostato nei file Web. config per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="24c5e-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="24c5e-142">Tuttavia, l'impostazione `requestQueueLimit` in un file Aspnet. config sostituisce l'impostazione di `requestQueueLimit` in un file Web. config.</span><span class="sxs-lookup"><span data-stu-id="24c5e-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="24c5e-143">In altre parole, se entrambi gli attributi sono impostati (per impostazione predefinita, questo è true), l'impostazione `requestQueueLimit` nel file Aspnet. config ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="24c5e-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24c5e-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="24c5e-144">Example</span></span>  

<span data-ttu-id="24c5e-145">Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo di ASP.NET nel file Aspnet. config nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="24c5e-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="24c5e-146">L'applicazione è ospitata in un pool di applicazioni IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="24c5e-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="24c5e-147">IIS 7,0 viene eseguito in modalità integrata.</span><span class="sxs-lookup"><span data-stu-id="24c5e-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="24c5e-148">L'applicazione usa la .NET Framework 3,5 SP1 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="24c5e-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="24c5e-149">I valori nell'esempio sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="24c5e-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="24c5e-150">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="24c5e-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24c5e-151">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="24c5e-151">Namespace</span></span>||  
|<span data-ttu-id="24c5e-152">Nome schema</span><span class="sxs-lookup"><span data-stu-id="24c5e-152">Schema Name</span></span>||  
|<span data-ttu-id="24c5e-153">File di convalida</span><span class="sxs-lookup"><span data-stu-id="24c5e-153">Validation File</span></span>||  
|<span data-ttu-id="24c5e-154">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="24c5e-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="24c5e-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c5e-155">See also</span></span>

- [<span data-ttu-id="24c5e-156">Elemento \<system.web> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="24c5e-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
