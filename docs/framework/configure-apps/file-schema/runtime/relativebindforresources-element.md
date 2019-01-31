---
title: <relativeBindForResources> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51129f9bb3a278d32a5da723dcc339f5e918c0f4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289809"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="69eb9-102">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="69eb9-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="69eb9-103">Ottimizza le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="69eb9-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="69eb9-104">\<configuration> Element</span></span>  
<span data-ttu-id="69eb9-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="69eb9-105">\<runtime> Element</span></span>  
<span data-ttu-id="69eb9-106">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="69eb9-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69eb9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69eb9-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69eb9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="69eb9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69eb9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="69eb9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69eb9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="69eb9-110">Attributes</span></span>  
  
|<span data-ttu-id="69eb9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="69eb9-111">Attribute</span></span>|<span data-ttu-id="69eb9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69eb9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="69eb9-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="69eb9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="69eb9-114">Specifica se tramite Common Language Runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="69eb9-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="69eb9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="69eb9-116">Valore</span><span class="sxs-lookup"><span data-stu-id="69eb9-116">Value</span></span>|<span data-ttu-id="69eb9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69eb9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="69eb9-118">Tramite il runtime non vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="69eb9-119">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="69eb9-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="69eb9-120">Tramite il runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69eb9-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="69eb9-121">Child Elements</span></span>  
 <span data-ttu-id="69eb9-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="69eb9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69eb9-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="69eb9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="69eb9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="69eb9-124">Element</span></span>|<span data-ttu-id="69eb9-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69eb9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69eb9-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69eb9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="69eb9-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="69eb9-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69eb9-128">Note</span><span class="sxs-lookup"><span data-stu-id="69eb9-128">Remarks</span></span>  
 <span data-ttu-id="69eb9-129">In generale, Resource Manager vengono cercate le risorse, come documentato nel [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="69eb9-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="69eb9-130">Ciò significa che per la ricerca di una particolare versione localizzata di una risorsa da parte di Gestione risorse l'operazione potrebbe essere eseguita nella Global Assembly Cache, in una cartella di impostazioni cultura specifiche nella codebase dell'applicazione, potrebbe essere eseguita una query su Windows Installer per gli assembly satellite e potrebbe essere generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69eb9-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="69eb9-131">Tramite l'elemento `<relativeBindForResources>` viene ottimizzata la modalità di ricerca degli assembly satellite tramite Gestione Risorse.</span><span class="sxs-lookup"><span data-stu-id="69eb9-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="69eb9-132">Le prestazioni possono migliorare durante la ricerca delle risorse nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="69eb9-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="69eb9-133">Quando l'assembly satellite viene distribuito nello stesso percorso dell'assembly di codice.</span><span class="sxs-lookup"><span data-stu-id="69eb9-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="69eb9-134">In altre parole, se l'assembly di codice è installato nella Global Assembly Cache, anche gli assembly satellite devono essere installati in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="69eb9-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="69eb9-135">Se l'assembly di codice è installato nella codebase dell'applicazione, anche gli assembly satellite devono essere installati in una cartella di impostazioni cultura specifiche nella codebase.</span><span class="sxs-lookup"><span data-stu-id="69eb9-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="69eb9-136">Quando Windows Installer non viene utilizzato o viene utilizzato solo raramente per installazioni su richiesta di assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="69eb9-137">Quando l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> non viene gestito dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69eb9-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="69eb9-138">L'impostazione dell'attributo `enabled` dell'elemento `<relativeBindForResources>` su `true` consente di ottimizzare la ricerca di assembly satellite da parte di Gestione risorse nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="69eb9-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="69eb9-139">Viene utilizzato il percorso dell'assembly del codice padre per cercare l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="69eb9-140">Non viene eseguita una query su Windows Installer per gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="69eb9-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="69eb9-141">Non viene generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69eb9-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69eb9-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69eb9-142">See also</span></span>
- [<span data-ttu-id="69eb9-143">Creazione del pacchetto e distribuzione delle risorse</span><span class="sxs-lookup"><span data-stu-id="69eb9-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="69eb9-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="69eb9-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="69eb9-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="69eb9-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
