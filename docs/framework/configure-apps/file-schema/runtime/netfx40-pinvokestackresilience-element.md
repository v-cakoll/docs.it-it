---
title: '&lt;NetFx40_PInvokeStackResilience&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b17816ee6134dc6b3074256093c0cba07419baf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="1c96c-102">&lt;NetFx40_PInvokeStackResilience&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="1c96c-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="1c96c-103">Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.</span><span class="sxs-lookup"><span data-stu-id="1c96c-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="1c96c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c96c-104">\<configuration></span></span>  
<span data-ttu-id="1c96c-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="1c96c-105">\<runtime></span></span>  
<span data-ttu-id="1c96c-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="1c96c-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c96c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c96c-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c96c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c96c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1c96c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c96c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c96c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c96c-110">Attributes</span></span>  
  
|<span data-ttu-id="1c96c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c96c-111">Attribute</span></span>|<span data-ttu-id="1c96c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c96c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1c96c-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c96c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1c96c-114">Specifica se il runtime rileva la piattaforma corretta dichiarazioni invoke e consente di correggere automaticamente lo stack in fase di esecuzione su piattaforme a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="1c96c-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1c96c-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="1c96c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1c96c-116">Valore</span><span class="sxs-lookup"><span data-stu-id="1c96c-116">Value</span></span>|<span data-ttu-id="1c96c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c96c-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="1c96c-118">Il runtime Usa introdotto nell'architettura di marshalling di interoperabilità più veloce la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], che non rileva e Correggi dichiarazioni platform invoke errate.</span><span class="sxs-lookup"><span data-stu-id="1c96c-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="1c96c-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1c96c-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="1c96c-120">Dichiarazioni di richiamo il runtime utilizza transizioni più lente che rileva e Correggi piattaforma non corretta.</span><span class="sxs-lookup"><span data-stu-id="1c96c-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c96c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c96c-121">Child Elements</span></span>  
 <span data-ttu-id="1c96c-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1c96c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c96c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c96c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1c96c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c96c-124">Element</span></span>|<span data-ttu-id="1c96c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c96c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1c96c-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c96c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1c96c-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1c96c-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c96c-128">Note</span><span class="sxs-lookup"><span data-stu-id="1c96c-128">Remarks</span></span>  
 <span data-ttu-id="1c96c-129">Questo elemento consente gli scambi più veloce il marshalling di interoperabilità per dichiarazioni di richiamo di resilienza in fase di esecuzione per la piattaforma non corretta.</span><span class="sxs-lookup"><span data-stu-id="1c96c-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="1c96c-130">A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], un'architettura di marshalling di interoperabilità semplificata fornisce un miglioramento significativo delle prestazioni per le transizioni da codice gestito a codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1c96c-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="1c96c-131">Nelle versioni precedenti di .NET Framework, la piattaforma non corretto a livello rilevato marshalling richiamare dichiarazioni in piattaforme a 32 bit e corrette automaticamente lo stack.</span><span class="sxs-lookup"><span data-stu-id="1c96c-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="1c96c-132">La nuova architettura di marshalling elimina questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1c96c-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="1c96c-133">Di conseguenza, le transizioni sono molto veloci, ma una dichiarazione platform invoke errata può causare un errore del programma.</span><span class="sxs-lookup"><span data-stu-id="1c96c-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="1c96c-134">Per consentire un facile rilevare le dichiarazioni non corrette durante lo sviluppo, è stato migliorato l'esperienza di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c96c-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="1c96c-135">Il [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) assistente al debug gestito (MDA) notifica della piattaforma non corretta invoke dichiarazioni quando l'applicazione è in esecuzione con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="1c96c-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="1c96c-136">Per scenari in cui l'applicazione utilizza componenti che non è possibile ricompilare e che sono dichiarazioni platform invoke errate, è possibile utilizzare il `NetFx40_PInvokeStackResilience` elemento.</span><span class="sxs-lookup"><span data-stu-id="1c96c-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="1c96c-137">Aggiunta di questo elemento al file di configurazione dell'applicazione con `enabled="1"` opts in una modalità di compatibilità con il comportamento delle versioni precedenti di .NET Framework, al costo di transizioni più lente.</span><span class="sxs-lookup"><span data-stu-id="1c96c-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="1c96c-138">Gli assembly che sono stati compilati con le versioni precedenti di .NET Framework vengono scelti automaticamente in questa modalità di compatibilità e non è necessario questo elemento.</span><span class="sxs-lookup"><span data-stu-id="1c96c-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1c96c-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1c96c-139">Configuration File</span></span>  
 <span data-ttu-id="1c96c-140">Questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1c96c-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c96c-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c96c-141">Example</span></span>  
 <span data-ttu-id="1c96c-142">L'esempio seguente viene illustrata la modalità per acconsentire esplicitamente una maggiore flessibilità rispetto corretto dichiarazioni platform invoke per un'applicazione, al costo di transizioni più lente tra codice gestito e.</span><span class="sxs-lookup"><span data-stu-id="1c96c-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c96c-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c96c-143">See Also</span></span>  
 [<span data-ttu-id="1c96c-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1c96c-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="1c96c-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1c96c-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1c96c-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="1c96c-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
