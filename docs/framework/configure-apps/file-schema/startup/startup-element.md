---
title: '&lt;avvio&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d39dc28082fbed932a60228ac216f2f700c2e9f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185545"
---
# <a name="ltstartupgt-element"></a><span data-ttu-id="250c5-102">&lt;avvio&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="250c5-102">&lt;startup&gt; Element</span></span>
<span data-ttu-id="250c5-103">Specifica informazioni di avvio di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="250c5-103">Specifies common language runtime startup information.</span></span>  
  
 <span data-ttu-id="250c5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="250c5-104">\<configuration></span></span>  
<span data-ttu-id="250c5-105">\<startup></span><span class="sxs-lookup"><span data-stu-id="250c5-105">\<startup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="250c5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="250c5-106">Syntax</span></span>  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="250c5-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="250c5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="250c5-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="250c5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="250c5-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="250c5-109">Attributes</span></span>  
  
|<span data-ttu-id="250c5-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="250c5-110">Attribute</span></span>|<span data-ttu-id="250c5-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250c5-111">Description</span></span>|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="250c5-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="250c5-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="250c5-113">Specifica se abilitare la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime o usare il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] criteri di attivazione.</span><span class="sxs-lookup"><span data-stu-id="250c5-113">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="250c5-114">Attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="250c5-114">useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
  
|<span data-ttu-id="250c5-115">Valore</span><span class="sxs-lookup"><span data-stu-id="250c5-115">Value</span></span>|<span data-ttu-id="250c5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250c5-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="250c5-117">Abilitare [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime per il runtime scelto, ovvero per associare le tecniche di attivazione di runtime legacy (ad esempio il [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione invece di limitazione di essi in CLR versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="250c5-117">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="250c5-118">Di conseguenza, se CLR 4 o versione successiva viene scelto dal file di configurazione, gli assembly in modalità mista creati con le versioni precedenti di .NET Framework vengono caricati con la versione di Common Language Runtime scelta.</span><span class="sxs-lookup"><span data-stu-id="250c5-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="250c5-119">Impostazione di questo valore impedisce CLR versione 1.1 o CLR versione 2.0 di caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="250c5-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|  
|`false`|<span data-ttu-id="250c5-120">Usare i criteri di attivazione predefinite per il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive, ovvero per consentire le tecniche di attivazione per caricare la versione 1.1 o 2.0 di CLR nel processo di runtime legacy.</span><span class="sxs-lookup"><span data-stu-id="250c5-120">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="250c5-121">Impostando questo valore, gli assembly in modalità mista venga caricato in .NET Framework 4 o versioni successive, a meno che non sono state compilate con .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="250c5-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="250c5-122">Questo valore è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="250c5-122">This value is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="250c5-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="250c5-123">Child Elements</span></span>  
  
|<span data-ttu-id="250c5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="250c5-124">Element</span></span>|<span data-ttu-id="250c5-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250c5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="250c5-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="250c5-126">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="250c5-127">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="250c5-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="250c5-128">Le applicazioni compilate con la versione 1.1 o versioni successive devono utilizzare il  **\<supportedRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="250c5-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="250c5-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="250c5-129">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="250c5-130">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="250c5-130">Specifies which versions of the common language runtime the application supports.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="250c5-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="250c5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="250c5-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="250c5-132">Element</span></span>|<span data-ttu-id="250c5-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250c5-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="250c5-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="250c5-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="250c5-135">Note</span><span class="sxs-lookup"><span data-stu-id="250c5-135">Remarks</span></span>  
 <span data-ttu-id="250c5-136">Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o versione successiva del runtime.</span><span class="sxs-lookup"><span data-stu-id="250c5-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="250c5-137">Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il  **\<requiredRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="250c5-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>  
  
 <span data-ttu-id="250c5-138">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora le  **\<avvio >** elemento e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="250c5-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="250c5-139">L'attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="250c5-139">The useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
 <span data-ttu-id="250c5-140">Questo attributo è utile se l'applicazione usa i percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che questi percorsi per attivare la versione 4 di CLR anziché una versione precedente, o se l'applicazione compilato con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ma presenta una dipendenza da un assembly in modalità mista compilato con una versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="250c5-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="250c5-141">In questi scenari impostare l'attributo su `true`.</span><span class="sxs-lookup"><span data-stu-id="250c5-141">In those scenarios, set the attribute to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="250c5-142">Impostare l'attributo su `true` impedisce il caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process CLR versione 1.1 o CLR versione 2.0 (vedere [esecuzione Side-by-Side per l'interoperabilità COM](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span><span class="sxs-lookup"><span data-stu-id="250c5-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="250c5-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="250c5-143">Example</span></span>  
 <span data-ttu-id="250c5-144">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="250c5-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="250c5-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250c5-145">See Also</span></span>  
 [<span data-ttu-id="250c5-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="250c5-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="250c5-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="250c5-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="250c5-148">\<PaveOver> Specifica della versione di runtime da usare</span><span class="sxs-lookup"><span data-stu-id="250c5-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [<span data-ttu-id="250c5-149">Esecuzione side-by-Side per l'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="250c5-149">Side-by-Side Execution for COM Interop</span></span>](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 <span data-ttu-id="250c5-150">[In-Process Side-by-Side Execution](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)</span><span class="sxs-lookup"><span data-stu-id="250c5-150">[In-Process Side-by-Side Execution](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)</span></span>
