---
title: '&lt;disableCommitThreadStack&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b02a5365aa2dc2292b0917820782405ba35ad92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534069"
---
# <a name="ltdisablecommitthreadstackgt-element"></a><span data-ttu-id="ed114-102">&lt;disableCommitThreadStack&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ed114-102">&lt;disableCommitThreadStack&gt; Element</span></span>
<span data-ttu-id="ed114-103">Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="ed114-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ed114-104">\<configuration></span></span>  
<span data-ttu-id="ed114-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ed114-105">\<runtime></span></span>  
<span data-ttu-id="ed114-106">\<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="ed114-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed114-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed114-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed114-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ed114-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ed114-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ed114-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed114-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ed114-110">Attributes</span></span>  
  
|<span data-ttu-id="ed114-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ed114-111">Attribute</span></span>|<span data-ttu-id="ed114-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed114-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed114-113">enabled</span><span class="sxs-lookup"><span data-stu-id="ed114-113">enabled</span></span>|<span data-ttu-id="ed114-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ed114-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ed114-115">Specifica se il commit dello stack di thread completo all'avvio del thread (comportamento predefinito) è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="ed114-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ed114-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="ed114-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="ed114-117">Valore</span><span class="sxs-lookup"><span data-stu-id="ed114-117">Value</span></span>|<span data-ttu-id="ed114-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed114-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed114-119">0</span><span class="sxs-lookup"><span data-stu-id="ed114-119">0</span></span>|<span data-ttu-id="ed114-120">Non disabilitare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="ed114-121">1</span><span class="sxs-lookup"><span data-stu-id="ed114-121">1</span></span>|<span data-ttu-id="ed114-122">Disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed114-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ed114-123">Child Elements</span></span>  
 <span data-ttu-id="ed114-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ed114-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed114-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ed114-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ed114-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed114-126">Element</span></span>|<span data-ttu-id="ed114-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed114-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ed114-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed114-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="ed114-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ed114-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed114-130">Note</span><span class="sxs-lookup"><span data-stu-id="ed114-130">Remarks</span></span>  
 <span data-ttu-id="ed114-131">Il comportamento predefinito del Common Language Runtime è eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="ed114-132">Se un numero elevato di thread deve essere creato in un server con memoria limitata e la maggior parte dei thread utilizzerà pochissimo spazio dello stack, il server potrebbe avere prestazioni migliori se il Common Language Runtime non esegue il commit dello stack di thread completo immediatamente quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed114-133">Gli host non gestiti possono usare il flag di avvio `STARTUP_DISABLE_COMMITTHREADSTACK` nell'enumerazione [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="ed114-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed114-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed114-134">Example</span></span>  
 <span data-ttu-id="ed114-135">L'esempio seguente mostra come disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo all'avvio del thread.</span><span class="sxs-lookup"><span data-stu-id="ed114-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed114-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed114-136">See also</span></span>
- [<span data-ttu-id="ed114-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ed114-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ed114-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ed114-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
