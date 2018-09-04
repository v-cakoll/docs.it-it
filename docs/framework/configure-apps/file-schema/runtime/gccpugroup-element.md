---
title: '&lt;GCCpuGroup&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ab18cded2b9a16fe2520547287198d3cfe6b74
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529311"
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="77361-102">&lt;GCCpuGroup&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="77361-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="77361-103">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="77361-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="77361-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="77361-104">\<configuration></span></span>  
<span data-ttu-id="77361-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="77361-105">\<runtime></span></span>  
<span data-ttu-id="77361-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="77361-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77361-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77361-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77361-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77361-108">Attributes and Elements</span></span>  
 <span data-ttu-id="77361-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77361-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77361-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="77361-110">Attributes</span></span>  
  
|<span data-ttu-id="77361-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="77361-111">Attribute</span></span>|<span data-ttu-id="77361-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77361-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="77361-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="77361-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="77361-114">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="77361-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="77361-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="77361-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="77361-116">Valore</span><span class="sxs-lookup"><span data-stu-id="77361-116">Value</span></span>|<span data-ttu-id="77361-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77361-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="77361-118">Operazione di Garbage collection non supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="77361-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="77361-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="77361-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="77361-120">Operazione di Garbage collection supporta più gruppi di CPU, se garbage collection per server è abilitato.</span><span class="sxs-lookup"><span data-stu-id="77361-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77361-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77361-121">Child Elements</span></span>  
 <span data-ttu-id="77361-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="77361-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77361-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77361-123">Parent Elements</span></span>  
  
|<span data-ttu-id="77361-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="77361-124">Element</span></span>|<span data-ttu-id="77361-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77361-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="77361-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77361-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="77361-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="77361-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77361-128">Note</span><span class="sxs-lookup"><span data-stu-id="77361-128">Remarks</span></span>  
 <span data-ttu-id="77361-129">Quando un computer con più gruppi di CPU, garbage collection per server è abilitata (vedere la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento), abilitazione di questo elemento consente di estendere la garbage collection in tutti i gruppi di CPU e accetta tutte le memorie centrali in account durante la creazione e bilanciamento degli heap.</span><span class="sxs-lookup"><span data-stu-id="77361-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77361-130">Questo elemento si applica solo ai thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="77361-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="77361-131">Per abilitare il runtime distribuisca i thread utente in tutti i gruppi di CPU, è necessario abilitare anche il [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="77361-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77361-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="77361-132">Example</span></span>  
 <span data-ttu-id="77361-133">Nell'esempio seguente viene illustrato come abilitare la procedura di garbage collection per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="77361-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77361-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77361-134">See Also</span></span>  
 [<span data-ttu-id="77361-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="77361-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="77361-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="77361-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="77361-137">Procedura: disabilitare la Garbage Collection simultanea</span><span class="sxs-lookup"><span data-stu-id="77361-137">How to: Disable Concurrent Garbage Collection</span></span>](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="77361-138">Operazione di garbage collection workstation e server</span><span class="sxs-lookup"><span data-stu-id="77361-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
