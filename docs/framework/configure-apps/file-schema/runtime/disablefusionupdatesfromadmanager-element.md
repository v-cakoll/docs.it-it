---
title: <disableFusionUpdatesFromADManager> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1923e70143ea2a158447eccdb35d347fe4f51ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663776"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="4d347-102">\<Elemento > disableFusionUpdatesFromADManager</span><span class="sxs-lookup"><span data-stu-id="4d347-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="4d347-103">Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d347-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="4d347-104">\<Configuration >-elemento</span><span class="sxs-lookup"><span data-stu-id="4d347-104">\<configuration> Element</span></span>  
<span data-ttu-id="4d347-105">\<Elemento runtime ></span><span class="sxs-lookup"><span data-stu-id="4d347-105">\<runtime> Element</span></span>  
<span data-ttu-id="4d347-106">\<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="4d347-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d347-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d347-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d347-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d347-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4d347-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d347-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d347-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d347-110">Attributes</span></span>  
  
|<span data-ttu-id="4d347-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d347-111">Attribute</span></span>|<span data-ttu-id="4d347-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4d347-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d347-113">enabled</span><span class="sxs-lookup"><span data-stu-id="4d347-113">enabled</span></span>|<span data-ttu-id="4d347-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4d347-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d347-115">Specifica se la capacità predefinita di eseguire l'override delle impostazioni Fusion è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4d347-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4d347-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4d347-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4d347-117">Valore</span><span class="sxs-lookup"><span data-stu-id="4d347-117">Value</span></span>|<span data-ttu-id="4d347-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d347-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d347-119">0</span><span class="sxs-lookup"><span data-stu-id="4d347-119">0</span></span>|<span data-ttu-id="4d347-120">Non disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="4d347-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="4d347-121">Si tratta del comportamento predefinito, a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4d347-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="4d347-122">1</span><span class="sxs-lookup"><span data-stu-id="4d347-122">1</span></span>|<span data-ttu-id="4d347-123">Disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="4d347-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="4d347-124">In questo modo viene ripristinato il comportamento delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d347-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d347-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d347-125">Child Elements</span></span>  
 <span data-ttu-id="4d347-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d347-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d347-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d347-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4d347-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d347-128">Element</span></span>|<span data-ttu-id="4d347-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d347-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4d347-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d347-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4d347-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4d347-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d347-132">Note</span><span class="sxs-lookup"><span data-stu-id="4d347-132">Remarks</span></span>  
 <span data-ttu-id="4d347-133">A partire da .NET Framework 4, il comportamento predefinito consiste nel consentire all' <xref:System.AppDomainManager> oggetto di eseguire l'override delle impostazioni di <xref:System.AppDomainSetup.ConfigurationFile%2A> configurazione usando la <xref:System.AppDomainSetup.SetConfigurationBytes%2A> proprietà <xref:System.AppDomainSetup> o il metodo dell'oggetto passato all'implementazione del metodo, nella sottoclasse di <xref:System.AppDomainManager>. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4d347-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="4d347-134">Per il dominio applicazione predefinito, le impostazioni modificate sostituiscono le impostazioni specificate dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d347-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="4d347-135">Per gli altri domini applicazione, sostituiscono le impostazioni di configurazione passate al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> metodo o. <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4d347-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4d347-136">È possibile passare le nuove informazioni di configurazione o passare null (`Nothing` in Visual Basic) per eliminare le informazioni di configurazione passate.</span><span class="sxs-lookup"><span data-stu-id="4d347-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="4d347-137">Non passare le informazioni di configurazione sia <xref:System.AppDomainSetup.ConfigurationFile%2A> alla proprietà che al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4d347-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="4d347-138">Se si passano le informazioni di configurazione a entrambe, le informazioni passate alla <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà vengono ignorate, perché <xref:System.AppDomainSetup.SetConfigurationBytes%2A> il metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d347-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="4d347-139">Se si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null (`Nothing` <xref:System.AppDomainSetup.SetConfigurationBytes%2A> in Visual Basic) al metodo per eliminare tutti i byte di configurazione specificati nella chiamata al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> metodo o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4d347-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4d347-140">Oltre alle informazioni di configurazione, è possibile modificare le impostazioni <xref:System.AppDomainSetup> seguenti nell'oggetto passato all'implementazione <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> del metodo: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A>,,, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, e<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A></span><span class="sxs-lookup"><span data-stu-id="4d347-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="4d347-141">In alternativa all'uso dell' `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito creando un'impostazione del registro di sistema o impostando una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4d347-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="4d347-142">Nel registro di sistema creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` in `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`, quindi impostare il valore su 1.</span><span class="sxs-lookup"><span data-stu-id="4d347-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="4d347-143">Nella riga di comando impostare la variabile `COMPLUS_disableFusionUpdatesFromADManager` di ambiente su 1.</span><span class="sxs-lookup"><span data-stu-id="4d347-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d347-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d347-144">Example</span></span>  
 <span data-ttu-id="4d347-145">Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion `<disableFusionUpdatesFromADManager>` utilizzando l'elemento.</span><span class="sxs-lookup"><span data-stu-id="4d347-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d347-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d347-146">See also</span></span>

- [<span data-ttu-id="4d347-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4d347-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4d347-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4d347-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4d347-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="4d347-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
