---
title: <etwEnable> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117389"
---
# <a name="etwenable-element"></a><span data-ttu-id="0d443-102">\<etwEnable> Elemento</span><span class="sxs-lookup"><span data-stu-id="0d443-102">\<etwEnable> Element</span></span>
<span data-ttu-id="0d443-103">Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="0d443-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a><span data-ttu-id="0d443-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d443-104">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d443-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0d443-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0d443-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0d443-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d443-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d443-107">Attributes</span></span>  
  
|<span data-ttu-id="0d443-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0d443-108">Attribute</span></span>|<span data-ttu-id="0d443-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d443-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d443-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="0d443-110">enabled</span></span>|<span data-ttu-id="0d443-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0d443-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="0d443-112">Specifica se ETW deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="0d443-112">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0d443-113">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0d443-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="0d443-114">Valore</span><span class="sxs-lookup"><span data-stu-id="0d443-114">Value</span></span>|<span data-ttu-id="0d443-115">Description</span><span class="sxs-lookup"><span data-stu-id="0d443-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0d443-116">true</span><span class="sxs-lookup"><span data-stu-id="0d443-116">true</span></span>|<span data-ttu-id="0d443-117">Abilita ETW.</span><span class="sxs-lookup"><span data-stu-id="0d443-117">Enable ETW.</span></span> <span data-ttu-id="0d443-118">Si tratta dell'impostazione predefinita per le versioni di Windows che iniziano con i sistemi operativi Windows Vista e Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="0d443-118">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="0d443-119">false</span><span class="sxs-lookup"><span data-stu-id="0d443-119">false</span></span>|<span data-ttu-id="0d443-120">Disabilitare ETW.</span><span class="sxs-lookup"><span data-stu-id="0d443-120">Disable ETW.</span></span> <span data-ttu-id="0d443-121">Si tratta dell'impostazione predefinita per le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="0d443-121">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d443-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0d443-122">Child Elements</span></span>  
 <span data-ttu-id="0d443-123">No.</span><span class="sxs-lookup"><span data-stu-id="0d443-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d443-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0d443-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0d443-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d443-125">Element</span></span>|<span data-ttu-id="0d443-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d443-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0d443-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d443-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0d443-128">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0d443-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d443-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="0d443-129">Remarks</span></span>  
 <span data-ttu-id="0d443-130">A partire da Windows Vista, ETW è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d443-130">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="0d443-131">Utilizzare questo elemento per disabilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d443-131">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="0d443-132">Nelle versioni precedenti di Windows, utilizzare questo elemento per abilitare ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d443-132">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d443-133">ETW può essere abilitato o disabilitato a livello globale in un server tramite un'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0d443-133">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="0d443-134">Vedere [controllo .NET Framework registrazione](../../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="0d443-134">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d443-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d443-135">Example</span></span>  
 <span data-ttu-id="0d443-136">Nell'esempio seguente viene illustrato come abilitare la traccia ETW per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d443-136">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d443-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0d443-137">See also</span></span>

- [<span data-ttu-id="0d443-138">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0d443-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0d443-139">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0d443-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0d443-140">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d443-140">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
