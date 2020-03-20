---
title: <appDomainResourceMonitoring> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154376"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="bc51a-102">\<AppDomainResourceMonitoring elemento></span><span class="sxs-lookup"><span data-stu-id="bc51a-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="bc51a-103">Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.</span><span class="sxs-lookup"><span data-stu-id="bc51a-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="bc51a-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc51a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bc51a-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bc51a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bc51a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>appDomainResourceMonitoring**</span><span class="sxs-lookup"><span data-stu-id="bc51a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc51a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc51a-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc51a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bc51a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bc51a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bc51a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc51a-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="bc51a-110">Attributes</span></span>  
  
|<span data-ttu-id="bc51a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="bc51a-111">Attribute</span></span>|<span data-ttu-id="bc51a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc51a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bc51a-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bc51a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc51a-114">Specifica se il runtime raccoglie statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc51a-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bc51a-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="bc51a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bc51a-116">valore</span><span class="sxs-lookup"><span data-stu-id="bc51a-116">Value</span></span>|<span data-ttu-id="bc51a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc51a-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="bc51a-118">Vengono raccolte le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc51a-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="bc51a-119">Le statistiche per il monitoraggio delle risorse del dominio applicazione non vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="bc51a-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc51a-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bc51a-120">Child Elements</span></span>  
 <span data-ttu-id="bc51a-121">No.</span><span class="sxs-lookup"><span data-stu-id="bc51a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc51a-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bc51a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bc51a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc51a-123">Element</span></span>|<span data-ttu-id="bc51a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc51a-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bc51a-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc51a-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bc51a-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bc51a-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc51a-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bc51a-127">Remarks</span></span>  
 <span data-ttu-id="bc51a-128">Il monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio applicazione gestito, l'interfaccia [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) di hosting e la traccia degli eventi per Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="bc51a-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="bc51a-129">Quando il monitoraggio è abilitato, le statistiche vengono raccolte per tutti i domini applicazione nel processo per tutta la durata del processo.</span><span class="sxs-lookup"><span data-stu-id="bc51a-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="bc51a-130">Per abilitare il monitoraggio <xref:System.AppDomain.MonitoringIsEnabled%2A> dal codice gestito, usare la proprietà .</span><span class="sxs-lookup"><span data-stu-id="bc51a-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="bc51a-131">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="bc51a-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc51a-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc51a-132">Example</span></span>  
 <span data-ttu-id="bc51a-133">Nell'esempio seguente viene illustrato come abilitare il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bc51a-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc51a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc51a-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bc51a-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="bc51a-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc51a-136">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bc51a-136">Configuration File Schema</span></span>](../index.md)
