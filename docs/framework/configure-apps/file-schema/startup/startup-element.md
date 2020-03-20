---
title: elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153731"
---
# <a name="startup-element"></a><span data-ttu-id="30853-102">\<elemento> all'avvio</span><span class="sxs-lookup"><span data-stu-id="30853-102">\<startup> element</span></span>

<span data-ttu-id="30853-103">Specifica le informazioni di avvio di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="30853-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="30853-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="30853-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="30853-105">&nbsp;&nbsp;**\<>di avvio**</span><span class="sxs-lookup"><span data-stu-id="30853-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="30853-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30853-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30853-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30853-107">Attributes and elements</span></span>

 <span data-ttu-id="30853-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30853-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="30853-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="30853-109">Attributes</span></span>

|<span data-ttu-id="30853-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="30853-110">Attribute</span></span>|<span data-ttu-id="30853-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30853-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="30853-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="30853-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="30853-113">Specifica se abilitare i criteri di attivazione runtime di .NET Framework 2.0 o utilizzare i criteri di attivazione di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="30853-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="30853-114">useLegacyV2RuntimeActivationPolicy (attributo)</span><span class="sxs-lookup"><span data-stu-id="30853-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="30853-115">valore</span><span class="sxs-lookup"><span data-stu-id="30853-115">Value</span></span>|<span data-ttu-id="30853-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30853-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="30853-117">Abilitare i criteri di attivazione runtime di .NET Framework 2.0 per il runtime scelto, ovvero associare le tecniche di attivazione runtime legacy (ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione anziché il limite in CLR versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="30853-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="30853-118">Pertanto, se CLR versione 4 o successiva viene scelto dal file di configurazione, gli assembly in modalità mista creati con versioni precedenti di .NET Framework vengono caricati con la versione CLR scelta.</span><span class="sxs-lookup"><span data-stu-id="30853-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="30853-119">L'impostazione di questo valore impedisce il caricamento di CLR versione 1.1 o 2.0 in uno stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="30853-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="30853-120">Utilizzare i criteri di attivazione predefiniti per .NET Framework 4 e versioni successive, che consente alle tecniche di attivazione runtime legacy di caricare CLR versione 1.1 o 2.0 nel processo.</span><span class="sxs-lookup"><span data-stu-id="30853-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="30853-121">L'impostazione di questo valore impedisce il caricamento di assembly in modalità mista in .NET Framework 4 o versioni successive, a meno che non siano compilati con .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="30853-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="30853-122">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="30853-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="30853-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30853-123">Child elements</span></span>

|<span data-ttu-id="30853-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="30853-124">Element</span></span>|<span data-ttu-id="30853-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30853-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30853-126">\<>runtime obbligatorio</span><span class="sxs-lookup"><span data-stu-id="30853-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="30853-127">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="30853-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="30853-128">Le applicazioni compilate con la versione di runtime 1.1 o successiva devono usare l'elemento \*\* \<>supportedRuntime.Applications\*\* built with runtime version 1.1 or later should use the supportedRuntime>element.</span><span class="sxs-lookup"><span data-stu-id="30853-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="30853-129">\<>supportedRuntime</span><span class="sxs-lookup"><span data-stu-id="30853-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="30853-130">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="30853-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="30853-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30853-131">Parent elements</span></span>

|<span data-ttu-id="30853-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="30853-132">Element</span></span>|<span data-ttu-id="30853-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30853-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="30853-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30853-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="30853-135">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="30853-135">Remarks</span></span>

 <span data-ttu-id="30853-136">L'elemento \*\* \<>supportedRuntime\*\* deve essere utilizzato da tutte le applicazioni compilate utilizzando la versione 1.1 o successiva del runtime.</span><span class="sxs-lookup"><span data-stu-id="30853-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="30853-137">Le applicazioni compilate per supportare solo la versione 1.0 del runtime devono utilizzare l'elemento \*\* \<>requiredRuntime.\*\*</span><span class="sxs-lookup"><span data-stu-id="30853-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="30853-138">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l'elemento \*\* \<>di avvio\*\* e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="30853-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="30853-139">Attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="30853-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="30853-140">Questo attributo è utile se l'applicazione utilizza percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che tali percorsi attivino la versione 4 di CLR anziché una versione precedente oppure se l'applicazione viene compilata con .NET Framework 4 ma ha una dipendenza da un assembly in modalità mista compilato con una versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30853-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="30853-141">In questi scenari, impostare l'attributo su `true`.</span><span class="sxs-lookup"><span data-stu-id="30853-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="30853-142">L'impostazione `true` dell'attributo su impedisce il caricamento di CLR versione 1.1 o 2.0 in uno stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process (vedere [Esecuzione side-by-side per interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="30853-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="30853-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="30853-143">Example</span></span>

 <span data-ttu-id="30853-144">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="30853-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="30853-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30853-145">See also</span></span>

- [<span data-ttu-id="30853-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="30853-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="30853-147">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="30853-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="30853-148">Procedura: configurare un'app per il supporto di .NET Framework 4 o versioni successiveHow to: Configure an app to support .NET Framework 4 or versioni successive</span><span class="sxs-lookup"><span data-stu-id="30853-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="30853-149">[Esecuzione side-by-side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30853-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- <span data-ttu-id="30853-150">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)</span><span class="sxs-lookup"><span data-stu-id="30853-150">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md)</span></span>
