---
title: '&lt;relativeBindForResources&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffd5b62e0759b3a4f97e105e884912a41f0117de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltrelativebindforresourcesgt-element"></a><span data-ttu-id="6ad2e-102">&lt;relativeBindForResources&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2e-102">&lt;relativeBindForResources&gt; Element</span></span>
<span data-ttu-id="6ad2e-103">Ottimizza le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="6ad2e-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2e-104">\<configuration> Element</span></span>  
<span data-ttu-id="6ad2e-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2e-105">\<runtime> Element</span></span>  
<span data-ttu-id="6ad2e-106">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2e-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad2e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ad2e-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ad2e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6ad2e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6ad2e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ad2e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6ad2e-110">Attributes</span></span>  
  
|<span data-ttu-id="6ad2e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6ad2e-111">Attribute</span></span>|<span data-ttu-id="6ad2e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ad2e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6ad2e-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6ad2e-114">Specifica se tramite Common Language Runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6ad2e-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="6ad2e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6ad2e-116">Valore</span><span class="sxs-lookup"><span data-stu-id="6ad2e-116">Value</span></span>|<span data-ttu-id="6ad2e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ad2e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6ad2e-118">Tramite il runtime non vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="6ad2e-119">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="6ad2e-120">Tramite il runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ad2e-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6ad2e-121">Child Elements</span></span>  
 <span data-ttu-id="6ad2e-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ad2e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6ad2e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6ad2e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ad2e-124">Element</span></span>|<span data-ttu-id="6ad2e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ad2e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6ad2e-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6ad2e-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ad2e-128">Note</span><span class="sxs-lookup"><span data-stu-id="6ad2e-128">Remarks</span></span>  
 <span data-ttu-id="6ad2e-129">In generale, Gestione risorse di probe per le risorse, come documentato nel [package e distribuzione delle risorse](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="6ad2e-130">Ciò significa che per la ricerca di una particolare versione localizzata di una risorsa da parte di Gestione risorse l'operazione potrebbe essere eseguita nella Global Assembly Cache, in una cartella di impostazioni cultura specifiche nella codebase dell'applicazione, potrebbe essere eseguita una query su Windows Installer per gli assembly satellite e potrebbe essere generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="6ad2e-131">Tramite l'elemento `<relativeBindForResources>` viene ottimizzata la modalità di ricerca degli assembly satellite tramite Gestione Risorse.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="6ad2e-132">Le prestazioni possono migliorare durante la ricerca delle risorse nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="6ad2e-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="6ad2e-133">Quando l'assembly satellite viene distribuito nello stesso percorso dell'assembly di codice.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="6ad2e-134">In altre parole, se l'assembly di codice è installato nella Global Assembly Cache, anche gli assembly satellite devono essere installati in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="6ad2e-135">Se l'assembly di codice è installato nella codebase dell'applicazione, anche gli assembly satellite devono essere installati in una cartella di impostazioni cultura specifiche nella codebase.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="6ad2e-136">Quando Windows Installer non viene utilizzato o viene utilizzato solo raramente per installazioni su richiesta di assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="6ad2e-137">Quando l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> non viene gestito dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="6ad2e-138">L'impostazione dell'attributo `enabled` dell'elemento `<relativeBindForResources>` su `true` consente di ottimizzare la ricerca di assembly satellite da parte di Gestione risorse nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="6ad2e-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="6ad2e-139">Viene utilizzato il percorso dell'assembly del codice padre per cercare l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="6ad2e-140">Non viene eseguita una query su Windows Installer per gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="6ad2e-141">Non viene generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ad2e-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad2e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ad2e-142">See Also</span></span>  
 [<span data-ttu-id="6ad2e-143">Creazione del pacchetto e distribuzione delle risorse</span><span class="sxs-lookup"><span data-stu-id="6ad2e-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [<span data-ttu-id="6ad2e-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6ad2e-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6ad2e-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6ad2e-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
