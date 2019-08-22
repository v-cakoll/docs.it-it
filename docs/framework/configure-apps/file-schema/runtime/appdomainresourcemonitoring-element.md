---
title: <appDomainResourceMonitoring> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b82be30c18cde361aa412ee1b631c8368c8de1b3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663935"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="b842c-102">\<Elemento > appDomainResourceMonitoring</span><span class="sxs-lookup"><span data-stu-id="b842c-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="b842c-103">Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.</span><span class="sxs-lookup"><span data-stu-id="b842c-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="b842c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b842c-104">\<configuration></span></span>  
<span data-ttu-id="b842c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b842c-105">\<runtime></span></span>  
<span data-ttu-id="b842c-106">\<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="b842c-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b842c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b842c-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b842c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b842c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b842c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b842c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b842c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b842c-110">Attributes</span></span>  
  
|<span data-ttu-id="b842c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b842c-111">Attribute</span></span>|<span data-ttu-id="b842c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b842c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b842c-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b842c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b842c-114">Specifica se il runtime raccoglie le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b842c-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b842c-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b842c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b842c-116">Valore</span><span class="sxs-lookup"><span data-stu-id="b842c-116">Value</span></span>|<span data-ttu-id="b842c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b842c-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b842c-118">Vengono raccolte le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b842c-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="b842c-119">Le statistiche per il monitoraggio delle risorse del dominio applicazione non vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="b842c-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b842c-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b842c-120">Child Elements</span></span>  
 <span data-ttu-id="b842c-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b842c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b842c-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b842c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b842c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b842c-123">Element</span></span>|<span data-ttu-id="b842c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b842c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b842c-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b842c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b842c-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b842c-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b842c-127">Note</span><span class="sxs-lookup"><span data-stu-id="b842c-127">Remarks</span></span>  
 <span data-ttu-id="b842c-128">Il monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio dell'applicazione gestita, l'interfaccia [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) di hosting e Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b842c-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="b842c-129">Quando il monitoraggio è abilitato, le statistiche vengono raccolte per tutti i domini applicazione nel processo per il ciclo di vita del processo.</span><span class="sxs-lookup"><span data-stu-id="b842c-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="b842c-130">Per abilitare il monitoraggio dal codice gestito, usare <xref:System.AppDomain.MonitoringIsEnabled%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b842c-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="b842c-131">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b842c-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b842c-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="b842c-132">Example</span></span>  
 <span data-ttu-id="b842c-133">Nell'esempio seguente viene illustrato come abilitare il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b842c-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b842c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b842c-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b842c-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b842c-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b842c-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b842c-136">Configuration File Schema</span></span>](../index.md)
