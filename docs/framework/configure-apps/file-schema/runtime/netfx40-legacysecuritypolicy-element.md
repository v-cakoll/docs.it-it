---
title: Elemento < NetFx40_LegacySecurityPolicy >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 868c5f0742fa4dc963539fd70414752092156c64
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489426"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="8da9b-102">\<NetFx40_LegacySecurityPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="8da9b-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>
<span data-ttu-id="8da9b-103">Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.</span><span class="sxs-lookup"><span data-stu-id="8da9b-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="8da9b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8da9b-104">\<configuration></span></span>  
<span data-ttu-id="8da9b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="8da9b-105">\<runtime></span></span>  
<span data-ttu-id="8da9b-106"><NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="8da9b-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da9b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8da9b-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8da9b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8da9b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8da9b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8da9b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8da9b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="8da9b-110">Attributes</span></span>  
  
|<span data-ttu-id="8da9b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="8da9b-111">Attribute</span></span>|<span data-ttu-id="8da9b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8da9b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8da9b-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8da9b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8da9b-114">Specifica se il runtime Usa criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="8da9b-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8da9b-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="8da9b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8da9b-116">Valore</span><span class="sxs-lookup"><span data-stu-id="8da9b-116">Value</span></span>|<span data-ttu-id="8da9b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8da9b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8da9b-118">Il runtime non usa criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="8da9b-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="8da9b-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8da9b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8da9b-120">Il runtime Usa criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="8da9b-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8da9b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8da9b-121">Child Elements</span></span>  
 <span data-ttu-id="8da9b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8da9b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8da9b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8da9b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8da9b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8da9b-124">Element</span></span>|<span data-ttu-id="8da9b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8da9b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8da9b-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8da9b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8da9b-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8da9b-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8da9b-128">Note</span><span class="sxs-lookup"><span data-stu-id="8da9b-128">Remarks</span></span>  
 <span data-ttu-id="8da9b-129">In .NET Framework versione 3.5 e versioni precedenti, il criterio CAS è sempre attivo.</span><span class="sxs-lookup"><span data-stu-id="8da9b-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="8da9b-130">In .NET Framework 4, è necessario abilitare il criterio CAS.</span><span class="sxs-lookup"><span data-stu-id="8da9b-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="8da9b-131">Questi criteri sono specifica della versione.</span><span class="sxs-lookup"><span data-stu-id="8da9b-131">CAS policy is version-specific.</span></span> <span data-ttu-id="8da9b-132">Criteri personalizzati di autorità di certificazione presenti nelle versioni precedenti di .NET Framework devono essere specificati nuovamente in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8da9b-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="8da9b-133">Applicando la `<NetFx40_LegacySecurityPolicy>` elemento a un assembly .NET Framework 4 non influisce sul [codice SecurityTransparent](../../../../../docs/framework/misc/security-transparent-code.md); le regole di trasparenza vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="8da9b-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8da9b-134">Applicando il `<NetFx40_LegacySecurityPolicy>` elemento può comportare riduzioni significative delle prestazioni per gli assembly di immagini native creati dal [generatore di immagini Native (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) che non sono installati nel [cache assembly globali ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="8da9b-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="8da9b-135">La riduzione delle prestazioni è causato dall'impossibilità di runtime di caricare gli assembly come le immagini native quando è applicato l'attributo, determinando che ne caricati gli assembly come just-in-time.</span><span class="sxs-lookup"><span data-stu-id="8da9b-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8da9b-136">Se si specifica una versione di .NET Framework di destinazione precedente a .NET Framework 4 nelle impostazioni del progetto per il progetto di Visual Studio, le autorità di certificazione criteri saranno abilitati, inclusi i criteri personalizzati di autorità di certificazione specificata per tale versione.</span><span class="sxs-lookup"><span data-stu-id="8da9b-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="8da9b-137">Tuttavia, non sarà in grado di utilizzare i membri e i nuovi tipi di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8da9b-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="8da9b-138">È anche possibile specificare una versione precedente di .NET Framework usando il [ \<supportedRuntime > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) nello schema delle impostazioni di avvio nel [file di configurazione dell'applicazione](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="8da9b-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8da9b-139">Sintassi dei file di configurazione è tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="8da9b-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="8da9b-140">È necessario usare la sintassi come specificato nelle sezioni di esempio e sintassi.</span><span class="sxs-lookup"><span data-stu-id="8da9b-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="8da9b-141">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8da9b-141">Configuration File</span></span>  
 <span data-ttu-id="8da9b-142">Questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8da9b-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8da9b-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="8da9b-143">Example</span></span>  
 <span data-ttu-id="8da9b-144">Nell'esempio seguente viene illustrato come abilitare i criteri CAS legacy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8da9b-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8da9b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8da9b-145">See also</span></span>

- [<span data-ttu-id="8da9b-146">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="8da9b-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="8da9b-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8da9b-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
