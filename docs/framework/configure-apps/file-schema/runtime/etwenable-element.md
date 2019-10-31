---
title: <etwEnable> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117389"
---
# <a name="etwenable-element"></a><span data-ttu-id="cfef3-102">\<elemento > etwEnable</span><span class="sxs-lookup"><span data-stu-id="cfef3-102">\<etwEnable> Element</span></span>
<span data-ttu-id="cfef3-103">Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="cfef3-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
<span data-ttu-id="cfef3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfef3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfef3-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="cfef3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cfef3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<etwEnabled >**</span><span class="sxs-lookup"><span data-stu-id="cfef3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfef3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfef3-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfef3-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfef3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cfef3-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfef3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfef3-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfef3-110">Attributes</span></span>  
  
|<span data-ttu-id="cfef3-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfef3-111">Attribute</span></span>|<span data-ttu-id="cfef3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfef3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfef3-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cfef3-113">enabled</span></span>|<span data-ttu-id="cfef3-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cfef3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cfef3-115">Specifica se ETW deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="cfef3-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cfef3-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="cfef3-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cfef3-117">Value</span><span class="sxs-lookup"><span data-stu-id="cfef3-117">Value</span></span>|<span data-ttu-id="cfef3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfef3-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cfef3-119">true</span><span class="sxs-lookup"><span data-stu-id="cfef3-119">true</span></span>|<span data-ttu-id="cfef3-120">Abilita ETW.</span><span class="sxs-lookup"><span data-stu-id="cfef3-120">Enable ETW.</span></span> <span data-ttu-id="cfef3-121">Si tratta dell'impostazione predefinita per le versioni di Windows che iniziano con i sistemi operativi Windows Vista e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="cfef3-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="cfef3-122">False</span><span class="sxs-lookup"><span data-stu-id="cfef3-122">false</span></span>|<span data-ttu-id="cfef3-123">Disabilitare ETW.</span><span class="sxs-lookup"><span data-stu-id="cfef3-123">Disable ETW.</span></span> <span data-ttu-id="cfef3-124">Si tratta dell'impostazione predefinita per le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="cfef3-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfef3-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfef3-125">Child Elements</span></span>  
 <span data-ttu-id="cfef3-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="cfef3-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfef3-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfef3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cfef3-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfef3-128">Element</span></span>|<span data-ttu-id="cfef3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfef3-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cfef3-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cfef3-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cfef3-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cfef3-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfef3-132">Note</span><span class="sxs-lookup"><span data-stu-id="cfef3-132">Remarks</span></span>  
 <span data-ttu-id="cfef3-133">A partire da Windows Vista, ETW è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cfef3-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="cfef3-134">Utilizzare questo elemento per disabilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cfef3-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="cfef3-135">Nelle versioni precedenti di Windows, utilizzare questo elemento per abilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cfef3-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfef3-136">ETW può essere abilitato o disabilitato a livello globale in un server tramite un'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="cfef3-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="cfef3-137">Vedere [controllo .NET Framework registrazione](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="cfef3-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfef3-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfef3-138">Example</span></span>  
 <span data-ttu-id="cfef3-139">Nell'esempio seguente viene illustrato come abilitare la traccia ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cfef3-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfef3-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfef3-140">See also</span></span>

- [<span data-ttu-id="cfef3-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="cfef3-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cfef3-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="cfef3-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cfef3-143">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cfef3-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
