---
title: '&lt;disableFusionUpdatesFromADManager&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d3a1214b4aecf56c9a6440e31459573a5922676
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a><span data-ttu-id="575bc-102">&lt;disableFusionUpdatesFromADManager&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="575bc-102">&lt;disableFusionUpdatesFromADManager&gt; Element</span></span>
<span data-ttu-id="575bc-103">Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="575bc-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="575bc-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="575bc-104">\<configuration> Element</span></span>  
<span data-ttu-id="575bc-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="575bc-105">\<runtime> Element</span></span>  
<span data-ttu-id="575bc-106">\<disableFusionUpdatesFromADManager ></span><span class="sxs-lookup"><span data-stu-id="575bc-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="575bc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575bc-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="575bc-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="575bc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="575bc-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="575bc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="575bc-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="575bc-110">Attributes</span></span>  
  
|<span data-ttu-id="575bc-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="575bc-111">Attribute</span></span>|<span data-ttu-id="575bc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575bc-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="575bc-113">enabled</span><span class="sxs-lookup"><span data-stu-id="575bc-113">enabled</span></span>|<span data-ttu-id="575bc-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="575bc-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="575bc-115">Specifica se l'opzione predefinita di eseguire l'override delle impostazioni Fusion è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="575bc-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="575bc-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="575bc-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="575bc-117">Valore</span><span class="sxs-lookup"><span data-stu-id="575bc-117">Value</span></span>|<span data-ttu-id="575bc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575bc-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="575bc-119">0</span><span class="sxs-lookup"><span data-stu-id="575bc-119">0</span></span>|<span data-ttu-id="575bc-120">Non disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="575bc-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="575bc-121">Si tratta del comportamento predefinito, a partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="575bc-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="575bc-122">1</span><span class="sxs-lookup"><span data-stu-id="575bc-122">1</span></span>|<span data-ttu-id="575bc-123">Disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="575bc-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="575bc-124">Viene ripristinato il comportamento delle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="575bc-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="575bc-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="575bc-125">Child Elements</span></span>  
 <span data-ttu-id="575bc-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="575bc-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="575bc-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="575bc-127">Parent Elements</span></span>  
  
|<span data-ttu-id="575bc-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="575bc-128">Element</span></span>|<span data-ttu-id="575bc-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575bc-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="575bc-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="575bc-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="575bc-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="575bc-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="575bc-132">Note</span><span class="sxs-lookup"><span data-stu-id="575bc-132">Remarks</span></span>  
 <span data-ttu-id="575bc-133">A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il comportamento predefinito consiste nel consentire la <xref:System.AppDomainManager> oggetto per eseguire l'override delle impostazioni di configurazione utilizzando il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà o <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo il <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> (metodo), in una sottoclasse di <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="575bc-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="575bc-134">Per il dominio applicazione predefinito, le impostazioni modificate si sostituiscono le impostazioni specificate dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="575bc-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="575bc-135">Per altri domini applicazione, sostituiscono le impostazioni di configurazione che sono state passate al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="575bc-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="575bc-136">È possibile passare nuove informazioni di configurazione o passare null (`Nothing` in Visual Basic) per eliminare le informazioni di configurazione che è state passate.</span><span class="sxs-lookup"><span data-stu-id="575bc-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="575bc-137">Non passare le informazioni di configurazione sia il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà e <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="575bc-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="575bc-138">Se si passano le informazioni di configurazione per entrambi, le informazioni passate per il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà viene ignorata, poiché il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="575bc-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="575bc-139">Se si utilizza il <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null (`Nothing` in Visual Basic) per il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> eliminare qualsiasi byte di configurazione che sono state specificate nella chiamata al metodo di <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="575bc-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="575bc-140">Oltre alle informazioni di configurazione, è possibile modificare le impostazioni seguenti nella <xref:System.AppDomainSetup> oggetto che viene passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, e <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="575bc-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="575bc-141">Come alternativa all'utilizzo di `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito creando un'impostazione del Registro di sistema o impostando una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="575bc-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="575bc-142">Nel Registro di sistema, creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` in `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`e impostare il valore su 1.</span><span class="sxs-lookup"><span data-stu-id="575bc-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="575bc-143">Nella riga di comando, impostare la variabile di ambiente `COMPLUS_disableFusionUpdatesFromADManager` su 1.</span><span class="sxs-lookup"><span data-stu-id="575bc-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="575bc-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="575bc-144">Example</span></span>  
 <span data-ttu-id="575bc-145">Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion utilizzando il `<disableFusionUpdatesFromADManager>` elemento.</span><span class="sxs-lookup"><span data-stu-id="575bc-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="575bc-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="575bc-146">See Also</span></span>  
 [<span data-ttu-id="575bc-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="575bc-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="575bc-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="575bc-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="575bc-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="575bc-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
