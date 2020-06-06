---
title: <disableFusionUpdatesFromADManager> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: 4e7375fddaa98b45766b29d911d555f773edcafa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117448"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="f0b7a-102">\<disableFusionUpdatesFromADManager> Elemento</span><span class="sxs-lookup"><span data-stu-id="f0b7a-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="f0b7a-103">Specifica se è disabilitato il comportamento predefinito, ovvero consentire all'host di runtime di eseguire l'override delle impostazioni di configurazione per un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a><span data-ttu-id="f0b7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0b7a-104">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0b7a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0b7a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f0b7a-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0b7a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0b7a-107">Attributes</span></span>  
  
|<span data-ttu-id="f0b7a-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f0b7a-108">Attribute</span></span>|<span data-ttu-id="f0b7a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0b7a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0b7a-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="f0b7a-110">enabled</span></span>|<span data-ttu-id="f0b7a-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f0b7a-112">Specifica se la capacità predefinita di eseguire l'override delle impostazioni Fusion è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-112">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f0b7a-113">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f0b7a-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="f0b7a-114">Valore</span><span class="sxs-lookup"><span data-stu-id="f0b7a-114">Value</span></span>|<span data-ttu-id="f0b7a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0b7a-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f0b7a-116">0</span><span class="sxs-lookup"><span data-stu-id="f0b7a-116">0</span></span>|<span data-ttu-id="f0b7a-117">Non disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-117">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="f0b7a-118">Si tratta del comportamento predefinito, a partire da .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-118">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="f0b7a-119">1</span><span class="sxs-lookup"><span data-stu-id="f0b7a-119">1</span></span>|<span data-ttu-id="f0b7a-120">Disabilitare la possibilità di eseguire l'override delle impostazioni Fusion.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-120">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="f0b7a-121">In questo modo viene ripristinato il comportamento delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-121">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0b7a-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0b7a-122">Child Elements</span></span>  
 <span data-ttu-id="f0b7a-123">No.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0b7a-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0b7a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f0b7a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0b7a-125">Element</span></span>|<span data-ttu-id="f0b7a-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0b7a-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f0b7a-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f0b7a-128">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0b7a-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="f0b7a-129">Remarks</span></span>  
 <span data-ttu-id="f0b7a-130">A partire da .NET Framework 4, il comportamento predefinito consiste nel consentire all' <xref:System.AppDomainManager> oggetto di eseguire l'override delle impostazioni di configurazione usando la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà o il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo dell' <xref:System.AppDomainSetup> oggetto passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo, nella sottoclasse di <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="f0b7a-130">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="f0b7a-131">Per il dominio applicazione predefinito, le impostazioni modificate sostituiscono le impostazioni specificate dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-131">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="f0b7a-132">Per gli altri domini applicazione, sostituiscono le impostazioni di configurazione passate al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> metodo o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f0b7a-132">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f0b7a-133">È possibile passare le nuove informazioni di configurazione o passare null ( `Nothing` in Visual Basic) per eliminare le informazioni di configurazione passate.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-133">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="f0b7a-134">Non passare le informazioni di configurazione sia alla <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà che al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-134">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="f0b7a-135">Se si passano le informazioni di configurazione a entrambe, le informazioni passate alla <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà vengono ignorate, perché il <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo esegue l'override delle informazioni di configurazione dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-135">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="f0b7a-136">Se si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> proprietà, è possibile passare null ( `Nothing` in Visual Basic) al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> metodo per eliminare tutti i byte di configurazione specificati nella chiamata al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> metodo o.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-136">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f0b7a-137">Oltre alle informazioni di configurazione, è possibile modificare le impostazioni seguenti nell' <xref:System.AppDomainSetup> oggetto passato all'implementazione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Metodo: <xref:System.AppDomainSetup.ApplicationBase%2A> ,, <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A> , <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> , <xref:System.AppDomainSetup.LoaderOptimization%2A> , <xref:System.AppDomainSetup.PrivateBinPath%2A> , <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> , <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> e <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="f0b7a-137">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="f0b7a-138">In alternativa all'uso dell' `<disableFusionUpdatesFromADManager>` elemento, è possibile disabilitare il comportamento predefinito creando un'impostazione del registro di sistema o impostando una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-138">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="f0b7a-139">Nel registro di sistema creare un valore DWORD denominato `COMPLUS_disableFusionUpdatesFromADManager` in `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework` , quindi impostare il valore su 1.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-139">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="f0b7a-140">Nella riga di comando impostare la variabile di ambiente `COMPLUS_disableFusionUpdatesFromADManager` su 1.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-140">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0b7a-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0b7a-141">Example</span></span>  
 <span data-ttu-id="f0b7a-142">Nell'esempio seguente viene illustrato come disabilitare la possibilità di eseguire l'override delle impostazioni Fusion utilizzando l' `<disableFusionUpdatesFromADManager>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f0b7a-142">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0b7a-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f0b7a-143">See also</span></span>

- [<span data-ttu-id="f0b7a-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f0b7a-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f0b7a-145">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f0b7a-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f0b7a-146">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="f0b7a-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
