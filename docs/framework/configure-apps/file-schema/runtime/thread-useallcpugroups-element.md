---
title: Elemento < Thread_UseAllCpuGroups >
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95411f5adde07c0d00124b2793b495c7ed8f49ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288938"
---
# <a name="threaduseallcpugroups-element"></a><span data-ttu-id="57bf8-102">\<Thread_UseAllCpuGroups > elemento</span><span class="sxs-lookup"><span data-stu-id="57bf8-102">\<Thread_UseAllCpuGroups> Element</span></span>
<span data-ttu-id="57bf8-103">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="57bf8-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="57bf8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="57bf8-104">\<configuration></span></span>  
<span data-ttu-id="57bf8-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="57bf8-105">\<runtime></span></span>  
<span data-ttu-id="57bf8-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="57bf8-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bf8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57bf8-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57bf8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57bf8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="57bf8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57bf8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57bf8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="57bf8-110">Attributes</span></span>  
  
|<span data-ttu-id="57bf8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="57bf8-111">Attribute</span></span>|<span data-ttu-id="57bf8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57bf8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="57bf8-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="57bf8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="57bf8-114">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="57bf8-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="57bf8-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="57bf8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="57bf8-116">Valore</span><span class="sxs-lookup"><span data-stu-id="57bf8-116">Value</span></span>|<span data-ttu-id="57bf8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57bf8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="57bf8-118">Il runtime non distribuisce i thread gestiti in più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="57bf8-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="57bf8-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="57bf8-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="57bf8-120">Il runtime distribuisce i thread gestiti tra più gruppi di CPU, se il computer dispone di più gruppi di CPU e il [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento è abilitato.</span><span class="sxs-lookup"><span data-stu-id="57bf8-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57bf8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57bf8-121">Child Elements</span></span>  
 <span data-ttu-id="57bf8-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="57bf8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57bf8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57bf8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="57bf8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="57bf8-124">Element</span></span>|<span data-ttu-id="57bf8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57bf8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="57bf8-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57bf8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="57bf8-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="57bf8-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57bf8-128">Note</span><span class="sxs-lookup"><span data-stu-id="57bf8-128">Remarks</span></span>  
 <span data-ttu-id="57bf8-129">Quando un computer ha più gruppi di CPU, abilitazione di questo elemento fa sì che il runtime distribuisca i thread gestiti in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="57bf8-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="57bf8-130">Per usare questa funzionalità, è necessario abilitare anche il [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento, che estende la garbage collection a tutti i gruppi di CPU e tiene conto durante la creazione e bilanciamento degli heap di tutte le memorie centrali.</span><span class="sxs-lookup"><span data-stu-id="57bf8-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="57bf8-131">Abilitare la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento richiede l'abilitazione di [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="57bf8-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="57bf8-132">Se questi elementi non sono abilitati, abilitando il `<Thread_UseAllCpuGroups>` elemento non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="57bf8-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57bf8-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="57bf8-133">Example</span></span>  
 <span data-ttu-id="57bf8-134">Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="57bf8-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57bf8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57bf8-135">See also</span></span>
- [<span data-ttu-id="57bf8-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="57bf8-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="57bf8-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="57bf8-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="57bf8-138">\<GCCpuGroup > elemento</span><span class="sxs-lookup"><span data-stu-id="57bf8-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
