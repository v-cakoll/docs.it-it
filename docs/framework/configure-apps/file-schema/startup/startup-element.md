---
title: Elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699420"
---
# <a name="startup-element"></a><span data-ttu-id="c3fb2-102">elemento > \<startup</span><span class="sxs-lookup"><span data-stu-id="c3fb2-102">\<startup> element</span></span>

<span data-ttu-id="c3fb2-103">Specifica Common Language Runtime informazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="c3fb2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c3fb2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c3fb2-105">&nbsp;&nbsp; **\<startup>**</span><span class="sxs-lookup"><span data-stu-id="c3fb2-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c3fb2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3fb2-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c3fb2-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3fb2-107">Attributes and elements</span></span>

 <span data-ttu-id="c3fb2-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c3fb2-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3fb2-109">Attributes</span></span>

|<span data-ttu-id="c3fb2-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="c3fb2-110">Attribute</span></span>|<span data-ttu-id="c3fb2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fb2-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="c3fb2-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c3fb2-113">Specifica se abilitare i criteri di attivazione di runtime di .NET Framework 2,0 o di usare i criteri di attivazione .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="c3fb2-114">attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="c3fb2-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="c3fb2-115">Value</span><span class="sxs-lookup"><span data-stu-id="c3fb2-115">Value</span></span>|<span data-ttu-id="c3fb2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fb2-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="c3fb2-117">Abilitare i criteri di attivazione di runtime di .NET Framework 2,0 per il runtime scelto, ovvero associare le tecniche di attivazione di runtime legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), al runtime scelto dal file di configurazione anziché limitarle a CLR versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="c3fb2-118">Pertanto, se si sceglie CLR versione 4 o successiva dal file di configurazione, gli assembly in modalità mista creati con le versioni precedenti del .NET Framework vengono caricati con la versione CLR scelta.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="c3fb2-119">L'impostazione di questo valore impedisce il caricamento di CLR versione 1,1 o CLR versione 2,0 nello stesso processo, disabilitando efficacemente la funzionalità side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="c3fb2-120">Usare i criteri di attivazione predefiniti per il .NET Framework 4 e versioni successive, ovvero consentire le tecniche legacy di attivazione del runtime per caricare la versione CLR 1,1 o 2,0 nel processo.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="c3fb2-121">L'impostazione di questo valore impedisce il caricamento degli assembly in modalità mista in .NET Framework 4 o versioni successive, a meno che non siano stati compilati con .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="c3fb2-122">Questo valore è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c3fb2-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3fb2-123">Child elements</span></span>

|<span data-ttu-id="c3fb2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3fb2-124">Element</span></span>|<span data-ttu-id="c3fb2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fb2-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c3fb2-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="c3fb2-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="c3fb2-127">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="c3fb2-128">Le applicazioni compilate con il runtime versione 1,1 o successive devono usare l'elemento **> \<supportedRuntime** .</span><span class="sxs-lookup"><span data-stu-id="c3fb2-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="c3fb2-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="c3fb2-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="c3fb2-130">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c3fb2-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3fb2-131">Parent elements</span></span>

|<span data-ttu-id="c3fb2-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3fb2-132">Element</span></span>|<span data-ttu-id="c3fb2-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fb2-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c3fb2-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c3fb2-135">Note</span><span class="sxs-lookup"><span data-stu-id="c3fb2-135">Remarks</span></span>

 <span data-ttu-id="c3fb2-136">L'elemento **> \<supportedRuntime** deve essere usato da tutte le applicazioni compilate con la versione 1,1 o successive del runtime.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="c3fb2-137">Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l'elemento **> \<requiredRuntime** .</span><span class="sxs-lookup"><span data-stu-id="c3fb2-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="c3fb2-138">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l'elemento **> \<startup** e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="c3fb2-139">Attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="c3fb2-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="c3fb2-140">Questo attributo è utile se l'applicazione utilizza percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che tali percorsi attivino la versione 4 di CLR anziché una versione precedente o se l'applicazione viene compilata con .NET Framework 4 ma ha una dipendenza da un assembly in modalità mista compilato con una versione precedente del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="c3fb2-141">In questi scenari, impostare l'attributo su `true`.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="c3fb2-142">L'impostazione dell'attributo su `true` impedisce il caricamento di CLR versione 1,1 o CLR versione 2,0 nello stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process (vedere [esecuzione side-by-side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="c3fb2-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="c3fb2-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3fb2-143">Example</span></span>

 <span data-ttu-id="c3fb2-144">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3fb2-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c3fb2-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3fb2-145">See also</span></span>

- [<span data-ttu-id="c3fb2-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="c3fb2-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c3fb2-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c3fb2-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c3fb2-148">Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="c3fb2-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="c3fb2-149">[Esecuzione side-by-side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c3fb2-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- <span data-ttu-id="c3fb2-150">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)</span><span class="sxs-lookup"><span data-stu-id="c3fb2-150">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md)</span></span>
