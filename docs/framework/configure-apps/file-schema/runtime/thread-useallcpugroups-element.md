---
title: '&lt;Thread_UseAllCpuGroups&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c574d6f5598616776e891ab282c703ce20bc6960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltthreaduseallcpugroupsgt-element"></a><span data-ttu-id="99e49-102">&lt;Thread_UseAllCpuGroups&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="99e49-102">&lt;Thread_UseAllCpuGroups&gt; Element</span></span>
<span data-ttu-id="99e49-103">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="99e49-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="99e49-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="99e49-104">\<configuration></span></span>  
<span data-ttu-id="99e49-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="99e49-105">\<runtime></span></span>  
<span data-ttu-id="99e49-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="99e49-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e49-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99e49-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99e49-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99e49-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99e49-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99e49-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99e49-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="99e49-110">Attributes</span></span>  
  
|<span data-ttu-id="99e49-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="99e49-111">Attribute</span></span>|<span data-ttu-id="99e49-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99e49-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="99e49-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="99e49-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="99e49-114">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="99e49-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="99e49-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="99e49-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="99e49-116">Valore</span><span class="sxs-lookup"><span data-stu-id="99e49-116">Value</span></span>|<span data-ttu-id="99e49-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99e49-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="99e49-118">Il runtime non distribuisce i thread gestiti in più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="99e49-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="99e49-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="99e49-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="99e49-120">Il runtime distribuisce i thread gestiti in più gruppi di CPU, se il computer dispone di più gruppi di CPU e [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento è abilitato.</span><span class="sxs-lookup"><span data-stu-id="99e49-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99e49-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99e49-121">Child Elements</span></span>  
 <span data-ttu-id="99e49-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="99e49-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99e49-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99e49-123">Parent Elements</span></span>  
  
|<span data-ttu-id="99e49-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="99e49-124">Element</span></span>|<span data-ttu-id="99e49-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99e49-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="99e49-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99e49-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="99e49-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="99e49-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e49-128">Note</span><span class="sxs-lookup"><span data-stu-id="99e49-128">Remarks</span></span>  
 <span data-ttu-id="99e49-129">Quando un computer dispone di più gruppi di CPU, abilitazione di questo elemento, il runtime di distribuire i thread gestiti in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="99e49-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="99e49-130">Per utilizzare questa funzionalità, è necessario abilitare il [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento, che estende l'operazione di garbage collection a tutti i gruppi di CPU e tiene conto durante la creazione e bilanciamento degli heap di tutti i core.</span><span class="sxs-lookup"><span data-stu-id="99e49-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="99e49-131">Abilitazione di [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento richiede l'abilitazione di [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="99e49-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="99e49-132">Se questi elementi non sono abilitati, l'abilitazione di `<Thread_UseAllCpuGroups>` elemento non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="99e49-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e49-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="99e49-133">Example</span></span>  
 <span data-ttu-id="99e49-134">Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="99e49-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99e49-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99e49-135">See Also</span></span>  
 [<span data-ttu-id="99e49-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="99e49-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="99e49-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="99e49-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="99e49-138">\<GCCpuGroup > elemento</span><span class="sxs-lookup"><span data-stu-id="99e49-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
