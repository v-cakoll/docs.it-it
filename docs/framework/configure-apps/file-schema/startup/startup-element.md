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
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153731"
---
# <a name="startup-element"></a><span data-ttu-id="359a4-102">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="359a4-102">\<startup> element</span></span>

<span data-ttu-id="359a4-103">Specifica Common Language Runtime informazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="359a4-103">Specifies common language runtime startup information.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<startup>**  

## <a name="syntax"></a><span data-ttu-id="359a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="359a4-104">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="359a4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="359a4-105">Attributes and elements</span></span>

 <span data-ttu-id="359a4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="359a4-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="359a4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="359a4-107">Attributes</span></span>

|<span data-ttu-id="359a4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="359a4-108">Attribute</span></span>|<span data-ttu-id="359a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="359a4-109">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="359a4-110">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="359a4-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="359a4-111">Specifica se abilitare i criteri di attivazione di runtime di .NET Framework 2,0 o di usare i criteri di attivazione .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="359a4-111">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="359a4-112">attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="359a4-112">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="359a4-113">Valore</span><span class="sxs-lookup"><span data-stu-id="359a4-113">Value</span></span>|<span data-ttu-id="359a4-114">Description</span><span class="sxs-lookup"><span data-stu-id="359a4-114">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="359a4-115">Abilitare .NET Framework criteri di attivazione di runtime 2,0 per il runtime scelto, ovvero associare le tecniche di attivazione di runtime legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), al runtime scelto dal file di configurazione invece di limitarle a CLR versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="359a4-115">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="359a4-116">Pertanto, se si sceglie CLR versione 4 o successiva dal file di configurazione, gli assembly in modalità mista creati con le versioni precedenti del .NET Framework vengono caricati con la versione CLR scelta.</span><span class="sxs-lookup"><span data-stu-id="359a4-116">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="359a4-117">L'impostazione di questo valore impedisce il caricamento di CLR versione 1,1 o CLR versione 2,0 nello stesso processo, disabilitando efficacemente la funzionalità side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="359a4-117">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="359a4-118">Usare i criteri di attivazione predefiniti per il .NET Framework 4 e versioni successive, ovvero consentire le tecniche legacy di attivazione del runtime per caricare la versione CLR 1,1 o 2,0 nel processo.</span><span class="sxs-lookup"><span data-stu-id="359a4-118">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="359a4-119">L'impostazione di questo valore impedisce il caricamento degli assembly in modalità mista in .NET Framework 4 o versioni successive, a meno che non siano stati compilati con .NET Framework 4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="359a4-119">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="359a4-120">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="359a4-120">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="359a4-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="359a4-121">Child elements</span></span>

|<span data-ttu-id="359a4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="359a4-122">Element</span></span>|<span data-ttu-id="359a4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="359a4-123">Description</span></span>|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="359a4-124">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="359a4-124">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="359a4-125">Le applicazioni compilate con la versione 1,1 o successiva del runtime devono usare l' **\<supportedRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="359a4-125">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="359a4-126">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="359a4-126">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="359a4-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="359a4-127">Parent elements</span></span>

|<span data-ttu-id="359a4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="359a4-128">Element</span></span>|<span data-ttu-id="359a4-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="359a4-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="359a4-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="359a4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="359a4-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="359a4-131">Remarks</span></span>

 <span data-ttu-id="359a4-132">L' **\<supportedRuntime>** elemento deve essere usato da tutte le applicazioni compilate con la versione 1,1 o successive del runtime.</span><span class="sxs-lookup"><span data-stu-id="359a4-132">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="359a4-133">Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l' **\<requiredRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="359a4-133">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="359a4-134">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l' **\<startup>** elemento e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="359a4-134">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="359a4-135">Attributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="359a4-135">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="359a4-136">Questo attributo è utile se l'applicazione utilizza percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che tali percorsi attivino la versione 4 di CLR anziché una versione precedente o se l'applicazione viene compilata con il .NET Framework 4 ma ha una dipendenza da un assembly in modalità mista compilato con una versione precedente del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="359a4-136">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="359a4-137">In questi scenari, impostare l'attributo su `true` .</span><span class="sxs-lookup"><span data-stu-id="359a4-137">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="359a4-138">Impostando l'attributo su si `true` impedisce il caricamento di CLR versione 1,1 o CLR versione 2,0 nello stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process (vedere [esecuzione side-by-side per l'interoperabilità com](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="359a4-138">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="359a4-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="359a4-139">Example</span></span>

 <span data-ttu-id="359a4-140">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="359a4-140">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="359a4-141">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="359a4-141">See also</span></span>

- [<span data-ttu-id="359a4-142">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="359a4-142">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="359a4-143">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="359a4-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="359a4-144">Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="359a4-144">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="359a4-145">[Esecuzione side-by-side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="359a4-145">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- <span data-ttu-id="359a4-146">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)</span><span class="sxs-lookup"><span data-stu-id="359a4-146">[In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md)</span></span>
