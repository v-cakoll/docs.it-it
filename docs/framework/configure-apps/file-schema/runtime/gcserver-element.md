---
title: <gcServer> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9125ee35b081a1723f379bd3fbdec808d085c675
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674451"
---
# <a name="gcserver-element"></a><span data-ttu-id="4a658-102">\<gcServer> Element</span><span class="sxs-lookup"><span data-stu-id="4a658-102">\<gcServer> Element</span></span>
<span data-ttu-id="4a658-103">Specifica se Common Language Runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="4a658-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4a658-104">\<configuration></span></span>  
<span data-ttu-id="4a658-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="4a658-105">\<runtime></span></span>  
<span data-ttu-id="4a658-106">\<gcServer></span><span class="sxs-lookup"><span data-stu-id="4a658-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a658-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a658-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a658-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4a658-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4a658-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4a658-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a658-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4a658-110">Attributes</span></span>  
  
|<span data-ttu-id="4a658-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4a658-111">Attribute</span></span>|<span data-ttu-id="4a658-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a658-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4a658-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4a658-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4a658-114">Specifica se il runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4a658-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4a658-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4a658-116">Valore</span><span class="sxs-lookup"><span data-stu-id="4a658-116">Value</span></span>|<span data-ttu-id="4a658-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a658-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4a658-118">Non esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-118">Does not run server garbage collection.</span></span> <span data-ttu-id="4a658-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4a658-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4a658-120">Esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a658-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4a658-121">Child Elements</span></span>  
 <span data-ttu-id="4a658-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4a658-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a658-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4a658-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4a658-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a658-124">Element</span></span>|<span data-ttu-id="4a658-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a658-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4a658-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a658-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4a658-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4a658-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a658-128">Note</span><span class="sxs-lookup"><span data-stu-id="4a658-128">Remarks</span></span>  
 <span data-ttu-id="4a658-129">Common Language Runtime (CLR) supporta due tipi di Garbage Collection: Garbage Collection per workstation, disponibile in tutti i sistemi, e Garbage Collection per server, disponibile nei sistemi con più processori.</span><span class="sxs-lookup"><span data-stu-id="4a658-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="4a658-130">Si usa l'elemento `<gcServer>` per controllare il tipo di Garbage Collection eseguito da CLR.</span><span class="sxs-lookup"><span data-stu-id="4a658-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="4a658-131">Usare la proprietà <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> per determinare se l'operazione Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4a658-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="4a658-132">Per i computer con un solo processore, l'operazione di Garbage Collection per workstation predefinita dovrebbe essere l'opzione più rapida.</span><span class="sxs-lookup"><span data-stu-id="4a658-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="4a658-133">Per i computer con due processori, si può usare quella per workstation o quella per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="4a658-134">L'operazione di Garbage Collection per server dovrebbe essere l'opzione più rapida per più di due processori.</span><span class="sxs-lookup"><span data-stu-id="4a658-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="4a658-135">Questo elemento può essere usato solo nel file di configurazione dell'applicazione. Se è nel file di configurazione del computer, viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="4a658-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a658-136">In .NET Framework 4 e versioni precedenti, la modalità di Garbage Collection simultanea non è disponibile quando l'operazione di Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4a658-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="4a658-137">A partire da [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], l'operazione di Garbage Collection per server è simultanea.</span><span class="sxs-lookup"><span data-stu-id="4a658-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="4a658-138">Per usare garbage collection del server non simultanea, impostare il `<gcServer>` elemento `true` e il [ \<gcConcurrent > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) a `false`.</span><span class="sxs-lookup"><span data-stu-id="4a658-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a658-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a658-139">Example</span></span>  
 <span data-ttu-id="4a658-140">L'esempio seguente abilita l'operazione di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4a658-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a658-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a658-141">See also</span></span>
- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4a658-142">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4a658-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4a658-143">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4a658-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4a658-144">Per disabilitare la garbage collection simultanea</span><span class="sxs-lookup"><span data-stu-id="4a658-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
