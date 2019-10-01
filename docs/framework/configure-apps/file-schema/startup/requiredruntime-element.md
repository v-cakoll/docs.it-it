---
title: Elemento <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697491"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="64d3e-102">elemento > \<requiredRuntime</span><span class="sxs-lookup"><span data-stu-id="64d3e-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="64d3e-103">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="64d3e-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="64d3e-104">Questo elemento è deprecato e non deve più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="64d3e-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="64d3e-105">In alternativa, è necessario usare l'elemento [`supportedRuntime`](supportedruntime-element.md) .</span><span class="sxs-lookup"><span data-stu-id="64d3e-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="64d3e-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="64d3e-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="64d3e-107">&nbsp; @ no__t-1[ **\<startup >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="64d3e-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="64d3e-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="64d3e-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="64d3e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64d3e-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64d3e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64d3e-110">Attributes and elements</span></span>

<span data-ttu-id="64d3e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64d3e-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="64d3e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="64d3e-112">Attributes</span></span>

|<span data-ttu-id="64d3e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="64d3e-113">Attribute</span></span>|<span data-ttu-id="64d3e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64d3e-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="64d3e-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64d3e-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64d3e-116">Valore stringa che specifica la versione del .NET Framework supportata da questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="64d3e-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="64d3e-117">Il valore stringa deve corrispondere al nome di directory trovato nella radice di installazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64d3e-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="64d3e-118">Il contenuto del valore stringa non viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="64d3e-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="64d3e-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="64d3e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64d3e-120">Specifica se il codice di avvio del runtime cerca il registro di sistema per determinare la versione di Runtime.</span><span class="sxs-lookup"><span data-stu-id="64d3e-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="64d3e-121">attributo modalità provvisoria</span><span class="sxs-lookup"><span data-stu-id="64d3e-121">safemode attribute</span></span>

|<span data-ttu-id="64d3e-122">Value</span><span class="sxs-lookup"><span data-stu-id="64d3e-122">Value</span></span>|<span data-ttu-id="64d3e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64d3e-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="64d3e-124">Il codice di avvio runtime cerca nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="64d3e-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="64d3e-125">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64d3e-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="64d3e-126">Il codice di avvio del runtime non cerca nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="64d3e-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="64d3e-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64d3e-127">Child elements</span></span>

<span data-ttu-id="64d3e-128">No.</span><span class="sxs-lookup"><span data-stu-id="64d3e-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="64d3e-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64d3e-129">Parent elements</span></span>

|<span data-ttu-id="64d3e-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="64d3e-130">Element</span></span>|<span data-ttu-id="64d3e-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64d3e-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="64d3e-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64d3e-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="64d3e-133">Contiene l' `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="64d3e-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64d3e-134">Note</span><span class="sxs-lookup"><span data-stu-id="64d3e-134">Remarks</span></span>
 <span data-ttu-id="64d3e-135">Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l'elemento `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="64d3e-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="64d3e-136">Le applicazioni compilate con la versione 1,1 o successive del runtime devono usare l'elemento `<supportedRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="64d3e-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="64d3e-137">Se si usa la funzione [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) per specificare il file di configurazione, è necessario usare l'elemento `<requiredRuntime>` per tutte le versioni del runtime.</span><span class="sxs-lookup"><span data-stu-id="64d3e-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="64d3e-138">L'elemento `<supportedRuntime>` viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="64d3e-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="64d3e-139">La stringa dell'attributo `version` deve corrispondere al nome della cartella di installazione per la versione specificata del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64d3e-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="64d3e-140">Questa stringa non viene interpretata.</span><span class="sxs-lookup"><span data-stu-id="64d3e-140">This string is not interpreted.</span></span> <span data-ttu-id="64d3e-141">Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato. il codice di avvio Mostra un messaggio di errore e viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="64d3e-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="64d3e-142">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l'elemento `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="64d3e-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="64d3e-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="64d3e-143">Example</span></span>

<span data-ttu-id="64d3e-144">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="64d3e-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="64d3e-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d3e-145">See also</span></span>

- [<span data-ttu-id="64d3e-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="64d3e-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="64d3e-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="64d3e-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="64d3e-148">Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="64d3e-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
