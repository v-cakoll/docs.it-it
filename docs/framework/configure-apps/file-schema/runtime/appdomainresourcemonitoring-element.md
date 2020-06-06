---
title: <appDomainResourceMonitoring> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154376"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="72263-102">\<appDomainResourceMonitoring> Elemento</span><span class="sxs-lookup"><span data-stu-id="72263-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="72263-103">Indica al runtime di raccogliere statistiche su tutti i domini applicazione nel processo per la durata del processo.</span><span class="sxs-lookup"><span data-stu-id="72263-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="72263-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72263-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72263-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="72263-105">Attributes and Elements</span></span>  
 <span data-ttu-id="72263-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="72263-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72263-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="72263-107">Attributes</span></span>  
  
|<span data-ttu-id="72263-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="72263-108">Attribute</span></span>|<span data-ttu-id="72263-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72263-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="72263-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="72263-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="72263-111">Specifica se il runtime raccoglie le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="72263-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="72263-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="72263-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="72263-113">Valore</span><span class="sxs-lookup"><span data-stu-id="72263-113">Value</span></span>|<span data-ttu-id="72263-114">Description</span><span class="sxs-lookup"><span data-stu-id="72263-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="72263-115">Vengono raccolte le statistiche per il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="72263-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="72263-116">Le statistiche per il monitoraggio delle risorse del dominio applicazione non vengono raccolte.</span><span class="sxs-lookup"><span data-stu-id="72263-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72263-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="72263-117">Child Elements</span></span>  
 <span data-ttu-id="72263-118">No.</span><span class="sxs-lookup"><span data-stu-id="72263-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72263-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="72263-119">Parent Elements</span></span>  
  
|<span data-ttu-id="72263-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="72263-120">Element</span></span>|<span data-ttu-id="72263-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72263-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="72263-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72263-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="72263-123">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72263-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72263-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="72263-124">Remarks</span></span>  
 <span data-ttu-id="72263-125">Il monitoraggio delle risorse del dominio applicazione è disponibile tramite la classe di dominio dell'applicazione gestita, l'interfaccia [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) di hosting e Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="72263-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="72263-126">Quando il monitoraggio è abilitato, le statistiche vengono raccolte per tutti i domini applicazione nel processo per il ciclo di vita del processo.</span><span class="sxs-lookup"><span data-stu-id="72263-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="72263-127">Per abilitare il monitoraggio dal codice gestito, usare la <xref:System.AppDomain.MonitoringIsEnabled%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="72263-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="72263-128">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="72263-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72263-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="72263-129">Example</span></span>  
 <span data-ttu-id="72263-130">Nell'esempio seguente viene illustrato come abilitare il monitoraggio delle risorse del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="72263-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72263-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="72263-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="72263-132">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="72263-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="72263-133">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="72263-133">Configuration File Schema</span></span>](../index.md)
