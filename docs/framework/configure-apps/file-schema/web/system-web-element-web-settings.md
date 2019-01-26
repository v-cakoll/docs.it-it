---
title: '&lt;System. Web&gt; (impostazioni Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 29aa97808f3595313b68072a910afb1354d45c6d
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084419"
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="1770a-102">&lt;System. Web&gt; (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="1770a-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="1770a-103">Contiene informazioni su come il livello di hosting ASP.NET gestisce il comportamento a livello di processo.</span><span class="sxs-lookup"><span data-stu-id="1770a-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="1770a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1770a-104">\<configuration></span></span>  
<span data-ttu-id="1770a-105">\<System. Web > (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="1770a-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1770a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1770a-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1770a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1770a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1770a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1770a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1770a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="1770a-109">Attributes</span></span>  
 <span data-ttu-id="1770a-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1770a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1770a-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1770a-111">Child Elements</span></span>  
  
|<span data-ttu-id="1770a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1770a-112">Element</span></span>|<span data-ttu-id="1770a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1770a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1770a-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="1770a-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="1770a-115">Specifica le impostazioni di configurazione per i pool di applicazioni IIS in un file ASPNET config.</span><span class="sxs-lookup"><span data-stu-id="1770a-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1770a-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1770a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1770a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1770a-117">Element</span></span>|<span data-ttu-id="1770a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1770a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1770a-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1770a-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1770a-120">Specifica l'elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1770a-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1770a-121">Note</span><span class="sxs-lookup"><span data-stu-id="1770a-121">Remarks</span></span>  
 <span data-ttu-id="1770a-122">Il `system.web` elemento e dal relativo elemento figlio `applicationPool` elemento sono stati aggiunti per il [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] come di [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1770a-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="1770a-123">Quando si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare come ASP.NET gestisce i thread e mette in coda le richieste quando ASP.NET è ospitato in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="1770a-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="1770a-124">Se si esegue [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versioni successive in modalità classica o di ISAPI, queste impostazioni verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="1770a-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1770a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="1770a-125">Example</span></span>  
 <span data-ttu-id="1770a-126">Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo ASP.NET nel file Aspnet. config quando ASP.NET è ospitato in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="1770a-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="1770a-127">Nell'esempio si presuppone che IIS sia in esecuzione in modalità integrata modalità e che l'applicazione usi il [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1770a-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="1770a-128">Questo comportamento non si verifica nelle versioni del [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] precedenti al [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1770a-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="1770a-129">I valori nell'esempio sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1770a-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="1770a-130">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="1770a-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1770a-131">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1770a-131">Namespace</span></span>||  
|<span data-ttu-id="1770a-132">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="1770a-132">Schema Name</span></span>||  
|<span data-ttu-id="1770a-133">File di convalida</span><span class="sxs-lookup"><span data-stu-id="1770a-133">Validation File</span></span>||  
|<span data-ttu-id="1770a-134">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="1770a-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="1770a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1770a-135">See also</span></span>
- [<span data-ttu-id="1770a-136">Elemento \<applicationPool> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="1770a-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
