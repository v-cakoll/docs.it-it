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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697491"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="0b2e0-102">Elemento \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="0b2e0-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="0b2e0-103">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="0b2e0-104">Questo elemento è deprecato e non deve più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="0b2e0-105">In [`supportedRuntime`](supportedruntime-element.md) alternativa, è necessario usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="0b2e0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b2e0-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b2e0-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0b2e0-107">Attributes and elements</span></span>

<span data-ttu-id="0b2e0-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b2e0-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="0b2e0-109">Attributes</span></span>

|<span data-ttu-id="0b2e0-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="0b2e0-110">Attribute</span></span>|<span data-ttu-id="0b2e0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b2e0-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="0b2e0-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0b2e0-113">Valore stringa che specifica la versione del .NET Framework supportata da questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="0b2e0-114">Il valore stringa deve corrispondere al nome di directory trovato nella radice di installazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="0b2e0-115">Il contenuto del valore stringa non viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="0b2e0-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0b2e0-117">Specifica se il codice di avvio del runtime cerca il registro di sistema per determinare la versione di Runtime.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="0b2e0-118">attributo modalità provvisoria</span><span class="sxs-lookup"><span data-stu-id="0b2e0-118">safemode attribute</span></span>

|<span data-ttu-id="0b2e0-119">Valore</span><span class="sxs-lookup"><span data-stu-id="0b2e0-119">Value</span></span>|<span data-ttu-id="0b2e0-120">Description</span><span class="sxs-lookup"><span data-stu-id="0b2e0-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0b2e0-121">Il codice di avvio runtime cerca nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="0b2e0-122">Si tratta del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="0b2e0-123">Il codice di avvio del runtime non cerca nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0b2e0-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0b2e0-124">Child elements</span></span>

<span data-ttu-id="0b2e0-125">No.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b2e0-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0b2e0-126">Parent elements</span></span>

|<span data-ttu-id="0b2e0-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b2e0-127">Element</span></span>|<span data-ttu-id="0b2e0-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b2e0-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0b2e0-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="0b2e0-130">Contiene l' `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0b2e0-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="0b2e0-131">Remarks</span></span>
 <span data-ttu-id="0b2e0-132">Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l' `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="0b2e0-133">Le applicazioni compilate con la versione 1,1 o successive del runtime devono usare l' `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="0b2e0-134">Se si usa la funzione [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) per specificare il file di configurazione, è necessario usare l' `<requiredRuntime>` elemento per tutte le versioni del runtime.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="0b2e0-135">L' `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="0b2e0-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="0b2e0-136">La `version` stringa dell'attributo deve corrispondere al nome della cartella di installazione per la versione specificata del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="0b2e0-137">Questa stringa non viene interpretata.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-137">This string is not interpreted.</span></span> <span data-ttu-id="0b2e0-138">Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato. il codice di avvio Mostra un messaggio di errore e viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="0b2e0-139">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l' `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="0b2e0-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b2e0-140">Example</span></span>

<span data-ttu-id="0b2e0-141">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0b2e0-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0b2e0-142">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0b2e0-142">See also</span></span>

- [<span data-ttu-id="0b2e0-143">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="0b2e0-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0b2e0-144">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0b2e0-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0b2e0-145">Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="0b2e0-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
