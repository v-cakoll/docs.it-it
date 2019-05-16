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
ms.openlocfilehash: d98f8d672ed1de1a5065a0390dba29992bcc1b39
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634467"
---
# <a name="startup-element"></a><span data-ttu-id="3a567-102">\<avvio > elemento</span><span class="sxs-lookup"><span data-stu-id="3a567-102">\<startup> element</span></span>

<span data-ttu-id="3a567-103">Specifica informazioni di avvio di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3a567-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="3a567-104">\<configuration> \<startup></span><span class="sxs-lookup"><span data-stu-id="3a567-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="3a567-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a567-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a567-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a567-106">Attributes and elements</span></span>

 <span data-ttu-id="3a567-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a567-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3a567-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a567-108">Attributes</span></span>

|<span data-ttu-id="3a567-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a567-109">Attribute</span></span>|<span data-ttu-id="3a567-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a567-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="3a567-111">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a567-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3a567-112">Specifica se abilitare la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime o usare il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] criteri di attivazione.</span><span class="sxs-lookup"><span data-stu-id="3a567-112">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="3a567-113">useLegacyV2RuntimeActivationPolicy attribute</span><span class="sxs-lookup"><span data-stu-id="3a567-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="3a567-114">Value</span><span class="sxs-lookup"><span data-stu-id="3a567-114">Value</span></span>|<span data-ttu-id="3a567-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a567-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="3a567-116">Abilitare [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime per il runtime scelto, ovvero per associare le tecniche di attivazione di runtime legacy (ad esempio il [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione invece di limitazione di essi in CLR versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="3a567-116">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="3a567-117">Di conseguenza, se CLR 4 o versione successiva viene scelto dal file di configurazione, gli assembly in modalità mista creati con le versioni precedenti di .NET Framework vengono caricati con la versione di Common Language Runtime scelta.</span><span class="sxs-lookup"><span data-stu-id="3a567-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="3a567-118">Impostazione di questo valore impedisce CLR versione 1.1 o CLR versione 2.0 di caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="3a567-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="3a567-119">Usare i criteri di attivazione predefinite per il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive, ovvero per consentire le tecniche di attivazione per caricare la versione 1.1 o 2.0 di CLR nel processo di runtime legacy.</span><span class="sxs-lookup"><span data-stu-id="3a567-119">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="3a567-120">Impostando questo valore, gli assembly in modalità mista venga caricato in .NET Framework 4 o versioni successive, a meno che non sono state compilate con .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3a567-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="3a567-121">Questo valore è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a567-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3a567-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a567-122">Child elements</span></span>

|<span data-ttu-id="3a567-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a567-123">Element</span></span>|<span data-ttu-id="3a567-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a567-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a567-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="3a567-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="3a567-126">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3a567-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="3a567-127">Le applicazioni compilate con la versione 1.1 o versioni successive devono utilizzare il  **\<supportedRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="3a567-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="3a567-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="3a567-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="3a567-129">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a567-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3a567-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a567-130">Parent elements</span></span>

|<span data-ttu-id="3a567-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a567-131">Element</span></span>|<span data-ttu-id="3a567-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a567-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3a567-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a567-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3a567-134">Note</span><span class="sxs-lookup"><span data-stu-id="3a567-134">Remarks</span></span>

 <span data-ttu-id="3a567-135">Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o versione successiva del runtime.</span><span class="sxs-lookup"><span data-stu-id="3a567-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="3a567-136">Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il  **\<requiredRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="3a567-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="3a567-137">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora le  **\<avvio >** elemento e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="3a567-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="3a567-138">L'attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="3a567-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="3a567-139">Questo attributo è utile se l'applicazione usa i percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che questi percorsi per attivare la versione 4 di CLR anziché una versione precedente, o se l'applicazione compilato con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ma presenta una dipendenza da un assembly in modalità mista compilato con una versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a567-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="3a567-140">In questi scenari impostare l'attributo su `true`.</span><span class="sxs-lookup"><span data-stu-id="3a567-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="3a567-141">Impostare l'attributo su `true` impedisce il caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process CLR versione 1.1 o CLR versione 2.0 (vedere [esecuzione Side-by-Side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="3a567-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="3a567-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a567-142">Example</span></span>

 <span data-ttu-id="3a567-143">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3a567-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3a567-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a567-144">See also</span></span>

- [<span data-ttu-id="3a567-145">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="3a567-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3a567-146">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3a567-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3a567-147">Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="3a567-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="3a567-148">[Esecuzione side-by-Side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3a567-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- <span data-ttu-id="3a567-149">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)</span><span class="sxs-lookup"><span data-stu-id="3a567-149">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md)</span></span>
