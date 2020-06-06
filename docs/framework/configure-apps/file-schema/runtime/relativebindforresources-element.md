---
title: <relativeBindForResources> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153906"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="91a3b-102">\<relativeBindForResources> Elemento</span><span class="sxs-lookup"><span data-stu-id="91a3b-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="91a3b-103">Ottimizza le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="91a3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91a3b-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91a3b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91a3b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="91a3b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91a3b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91a3b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="91a3b-107">Attributes</span></span>  
  
|<span data-ttu-id="91a3b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="91a3b-108">Attribute</span></span>|<span data-ttu-id="91a3b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a3b-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="91a3b-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="91a3b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="91a3b-111">Specifica se tramite Common Language Runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="91a3b-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="91a3b-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="91a3b-113">Valore</span><span class="sxs-lookup"><span data-stu-id="91a3b-113">Value</span></span>|<span data-ttu-id="91a3b-114">Description</span><span class="sxs-lookup"><span data-stu-id="91a3b-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="91a3b-115">Tramite il runtime non vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="91a3b-116">Si tratta del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="91a3b-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="91a3b-117">Tramite il runtime vengono ottimizzate le ricerche degli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91a3b-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91a3b-118">Child Elements</span></span>  
 <span data-ttu-id="91a3b-119">No.</span><span class="sxs-lookup"><span data-stu-id="91a3b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91a3b-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91a3b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="91a3b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a3b-121">Element</span></span>|<span data-ttu-id="91a3b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a3b-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91a3b-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91a3b-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="91a3b-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91a3b-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91a3b-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="91a3b-125">Remarks</span></span>  
 <span data-ttu-id="91a3b-126">In generale, Gestione risorse Probe per le risorse, come documentato nell'argomento Creazione di [pacchetti e distribuzione delle risorse](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="91a3b-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="91a3b-127">Ciò significa che per la ricerca di una particolare versione localizzata di una risorsa da parte di Gestione risorse l'operazione potrebbe essere eseguita nella Global Assembly Cache, in una cartella di impostazioni cultura specifiche nella codebase dell'applicazione, potrebbe essere eseguita una query su Windows Installer per gli assembly satellite e potrebbe essere generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91a3b-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="91a3b-128">Tramite l'elemento `<relativeBindForResources>` viene ottimizzata la modalità di ricerca degli assembly satellite tramite Gestione Risorse.</span><span class="sxs-lookup"><span data-stu-id="91a3b-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="91a3b-129">Le prestazioni possono migliorare durante la ricerca delle risorse nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="91a3b-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="91a3b-130">Quando l'assembly satellite viene distribuito nello stesso percorso dell'assembly di codice.</span><span class="sxs-lookup"><span data-stu-id="91a3b-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="91a3b-131">In altre parole, se l'assembly di codice è installato nella Global Assembly Cache, anche gli assembly satellite devono essere installati in questa posizione.</span><span class="sxs-lookup"><span data-stu-id="91a3b-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="91a3b-132">Se l'assembly di codice è installato nella codebase dell'applicazione, anche gli assembly satellite devono essere installati in una cartella di impostazioni cultura specifiche nella codebase.</span><span class="sxs-lookup"><span data-stu-id="91a3b-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="91a3b-133">Quando Windows Installer non viene utilizzato o viene utilizzato solo raramente per installazioni su richiesta di assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="91a3b-134">Quando l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> non viene gestito dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="91a3b-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="91a3b-135">L'impostazione dell'attributo `enabled` dell'elemento `<relativeBindForResources>` su `true` consente di ottimizzare la ricerca di assembly satellite da parte di Gestione risorse nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="91a3b-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="91a3b-136">Viene utilizzato il percorso dell'assembly del codice padre per cercare l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="91a3b-137">Non viene eseguita una query su Windows Installer per gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="91a3b-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="91a3b-138">Non viene generato l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="91a3b-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a3b-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="91a3b-139">See also</span></span>

- [<span data-ttu-id="91a3b-140">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="91a3b-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="91a3b-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="91a3b-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91a3b-142">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="91a3b-142">Configuration File Schema</span></span>](../index.md)
