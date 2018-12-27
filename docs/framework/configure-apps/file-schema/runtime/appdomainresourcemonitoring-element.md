---
title: '&lt;appDomainResourceMonitoring&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32ffe48e7a65ab4ca2250eee65d188c0c7270c11
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611334"
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="86c15-102">&lt;appDomainResourceMonitoring&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="86c15-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="86c15-103">Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.</span><span class="sxs-lookup"><span data-stu-id="86c15-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="86c15-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="86c15-104">\<configuration></span></span>  
<span data-ttu-id="86c15-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="86c15-105">\<runtime></span></span>  
<span data-ttu-id="86c15-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="86c15-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c15-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86c15-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86c15-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="86c15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="86c15-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="86c15-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86c15-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="86c15-110">Attributes</span></span>  
  
|<span data-ttu-id="86c15-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="86c15-111">Attribute</span></span>|<span data-ttu-id="86c15-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86c15-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="86c15-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="86c15-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="86c15-114">Specifica se il runtime raccoglie le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="86c15-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="86c15-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="86c15-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="86c15-116">Valore</span><span class="sxs-lookup"><span data-stu-id="86c15-116">Value</span></span>|<span data-ttu-id="86c15-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86c15-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="86c15-118">Statistiche di monitoraggio delle risorse del dominio dell'applicazione vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="86c15-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="86c15-119">Statistiche di monitoraggio delle risorse del dominio applicazione non vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="86c15-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86c15-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="86c15-120">Child Elements</span></span>  
 <span data-ttu-id="86c15-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="86c15-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86c15-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="86c15-122">Parent Elements</span></span>  
  
|<span data-ttu-id="86c15-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="86c15-123">Element</span></span>|<span data-ttu-id="86c15-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86c15-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="86c15-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86c15-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="86c15-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="86c15-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c15-127">Note</span><span class="sxs-lookup"><span data-stu-id="86c15-127">Remarks</span></span>  
 <span data-ttu-id="86c15-128">Monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio di applicazione gestita, l'hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaccia e event tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="86c15-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="86c15-129">Quando il monitoraggio è abilitato, vengono raccolte statistiche per tutti i domini applicazione del processo per il ciclo di vita del processo.</span><span class="sxs-lookup"><span data-stu-id="86c15-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="86c15-130">Per abilitare il monitoraggio dal codice gestito, usare il <xref:System.AppDomain.MonitoringIsEnabled%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="86c15-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="86c15-131">Questo elemento di configurazione è disponibile solo nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="86c15-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c15-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="86c15-132">Example</span></span>  
 <span data-ttu-id="86c15-133">Nell'esempio seguente viene illustrato come abilitare Monitoraggio risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="86c15-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86c15-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86c15-134">See Also</span></span>  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="86c15-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="86c15-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="86c15-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="86c15-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
