---
title: '&lt;etwEnable&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b36c52338754df0f4fd3c963848e36afeb140501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltetwenablegt-element"></a><span data-ttu-id="b7103-102">&lt;etwEnable&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="b7103-102">&lt;etwEnable&gt; Element</span></span>
<span data-ttu-id="b7103-103">Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="b7103-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="b7103-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="b7103-104">\<configuration> Element</span></span>  
<span data-ttu-id="b7103-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="b7103-105">\<runtime> Element</span></span>  
<span data-ttu-id="b7103-106">\<etwEnabled ></span><span class="sxs-lookup"><span data-stu-id="b7103-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7103-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7103-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7103-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b7103-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b7103-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b7103-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7103-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b7103-110">Attributes</span></span>  
  
|<span data-ttu-id="b7103-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b7103-111">Attribute</span></span>|<span data-ttu-id="b7103-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7103-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7103-113">enabled</span><span class="sxs-lookup"><span data-stu-id="b7103-113">enabled</span></span>|<span data-ttu-id="b7103-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7103-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7103-115">Specifica se deve essere abilitato ETW.</span><span class="sxs-lookup"><span data-stu-id="b7103-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b7103-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b7103-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="b7103-117">Valore</span><span class="sxs-lookup"><span data-stu-id="b7103-117">Value</span></span>|<span data-ttu-id="b7103-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7103-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7103-119">true</span><span class="sxs-lookup"><span data-stu-id="b7103-119">true</span></span>|<span data-ttu-id="b7103-120">Attiva ETW.</span><span class="sxs-lookup"><span data-stu-id="b7103-120">Enable ETW.</span></span> <span data-ttu-id="b7103-121">Questo è il valore predefinito per le versioni di Windows a partire con i sistemi operativi Windows Vista e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="b7103-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="b7103-122">false</span><span class="sxs-lookup"><span data-stu-id="b7103-122">false</span></span>|<span data-ttu-id="b7103-123">Disabilitare ETW.</span><span class="sxs-lookup"><span data-stu-id="b7103-123">Disable ETW.</span></span> <span data-ttu-id="b7103-124">Questo è il valore predefinito per le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="b7103-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7103-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b7103-125">Child Elements</span></span>  
 <span data-ttu-id="b7103-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b7103-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7103-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b7103-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b7103-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7103-128">Element</span></span>|<span data-ttu-id="b7103-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7103-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7103-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7103-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b7103-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b7103-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7103-132">Note</span><span class="sxs-lookup"><span data-stu-id="b7103-132">Remarks</span></span>  
 <span data-ttu-id="b7103-133">A partire da Windows Vista, ETW è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b7103-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="b7103-134">Utilizzare questo elemento consente di disabilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7103-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="b7103-135">Nelle versioni precedenti di Windows, utilizzare questo elemento per abilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7103-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7103-136">ETW può essere abilitato o disabilitato a livello globale in un server utilizzando un'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b7103-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="b7103-137">Vedere [controllo della registrazione di .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b7103-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7103-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7103-138">Example</span></span>  
 <span data-ttu-id="b7103-139">Nell'esempio seguente viene illustrato come abilitare la traccia ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7103-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7103-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7103-140">See Also</span></span>  
 [<span data-ttu-id="b7103-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b7103-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b7103-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b7103-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="b7103-143">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7103-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
