---
title: <etwEnable> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135070"
---
# <a name="etwenable-element"></a><span data-ttu-id="b726b-102">\<etwEnable > elemento</span><span class="sxs-lookup"><span data-stu-id="b726b-102">\<etwEnable> Element</span></span>
<span data-ttu-id="b726b-103">Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="b726b-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="b726b-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="b726b-104">\<configuration> Element</span></span>  
<span data-ttu-id="b726b-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="b726b-105">\<runtime> Element</span></span>  
<span data-ttu-id="b726b-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="b726b-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b726b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b726b-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b726b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b726b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b726b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b726b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b726b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b726b-110">Attributes</span></span>  
  
|<span data-ttu-id="b726b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b726b-111">Attribute</span></span>|<span data-ttu-id="b726b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b726b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b726b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="b726b-113">enabled</span></span>|<span data-ttu-id="b726b-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b726b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="b726b-115">Specifica se devono essere abilitati ETW.</span><span class="sxs-lookup"><span data-stu-id="b726b-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b726b-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b726b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="b726b-117">Valore</span><span class="sxs-lookup"><span data-stu-id="b726b-117">Value</span></span>|<span data-ttu-id="b726b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b726b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b726b-119">true</span><span class="sxs-lookup"><span data-stu-id="b726b-119">true</span></span>|<span data-ttu-id="b726b-120">Abilita ETW.</span><span class="sxs-lookup"><span data-stu-id="b726b-120">Enable ETW.</span></span> <span data-ttu-id="b726b-121">Questo è il valore predefinito per le versioni di Windows partire con i sistemi operativi Windows Vista e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="b726b-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="b726b-122">False</span><span class="sxs-lookup"><span data-stu-id="b726b-122">false</span></span>|<span data-ttu-id="b726b-123">Disabilitare ETW.</span><span class="sxs-lookup"><span data-stu-id="b726b-123">Disable ETW.</span></span> <span data-ttu-id="b726b-124">Questo è il valore predefinito per le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="b726b-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b726b-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b726b-125">Child Elements</span></span>  
 <span data-ttu-id="b726b-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b726b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b726b-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b726b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="b726b-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="b726b-128">Element</span></span>|<span data-ttu-id="b726b-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b726b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b726b-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b726b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b726b-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b726b-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b726b-132">Note</span><span class="sxs-lookup"><span data-stu-id="b726b-132">Remarks</span></span>  
 <span data-ttu-id="b726b-133">A partire da Windows Vista, ETW è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b726b-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="b726b-134">Usare questo elemento consente di disabilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b726b-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="b726b-135">Nelle versioni precedenti di Windows, usare questo elemento per attivare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b726b-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b726b-136">ETW può essere abilitato o disabilitato a livello globale in un server usando un'impostazione del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b726b-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="b726b-137">Visualizzare [controllo della registrazione di .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b726b-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b726b-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="b726b-138">Example</span></span>  
 <span data-ttu-id="b726b-139">Nell'esempio seguente viene illustrato come attivare ETW tracing per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b726b-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b726b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b726b-140">See also</span></span>

- [<span data-ttu-id="b726b-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b726b-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b726b-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b726b-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b726b-143">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b726b-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
