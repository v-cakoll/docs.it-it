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
ms.openlocfilehash: f5a9f99133c153401694372abaeea10a02e492e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634184"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="f6700-102">\<requiredRuntime > elemento</span><span class="sxs-lookup"><span data-stu-id="f6700-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="f6700-103">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6700-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="f6700-104">Questo elemento è deprecato e non deve più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f6700-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="f6700-105">Il [ `supportedRuntime` ](supportedruntime-element.md) elemento deve essere usato invece.</span><span class="sxs-lookup"><span data-stu-id="f6700-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="f6700-106">\<configuration> \<startup> \<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="f6700-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="f6700-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6700-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f6700-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f6700-108">Attributes and elements</span></span>

<span data-ttu-id="f6700-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f6700-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f6700-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f6700-110">Attributes</span></span>

|<span data-ttu-id="f6700-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f6700-111">Attribute</span></span>|<span data-ttu-id="f6700-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6700-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="f6700-113">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f6700-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f6700-114">Valore stringa che specifica la versione di .NET Framework supportata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6700-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="f6700-115">Il valore della stringa deve corrispondere al nome di directory trovato nella directory radice di installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6700-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="f6700-116">Il contenuto del valore della stringa non viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="f6700-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="f6700-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f6700-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f6700-118">Specifica se il codice di avvio di runtime cerca il Registro di sistema per determinare la versione di runtime.</span><span class="sxs-lookup"><span data-stu-id="f6700-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="f6700-119">attributo di modalità provvisoria</span><span class="sxs-lookup"><span data-stu-id="f6700-119">safemode attribute</span></span>

|<span data-ttu-id="f6700-120">Value</span><span class="sxs-lookup"><span data-stu-id="f6700-120">Value</span></span>|<span data-ttu-id="f6700-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6700-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f6700-122">Il codice di avvio di runtime cerca nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="f6700-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="f6700-123">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f6700-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="f6700-124">Il codice di avvio del runtime non cercare nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="f6700-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f6700-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f6700-125">Child elements</span></span>

<span data-ttu-id="f6700-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f6700-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f6700-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f6700-127">Parent elements</span></span>

|<span data-ttu-id="f6700-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6700-128">Element</span></span>|<span data-ttu-id="f6700-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6700-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f6700-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6700-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="f6700-131">Contiene il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f6700-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f6700-132">Note</span><span class="sxs-lookup"><span data-stu-id="f6700-132">Remarks</span></span>
 <span data-ttu-id="f6700-133">Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f6700-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="f6700-134">Le applicazioni compilate con la versione 1.1 o versione successiva del runtime devono usare il `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f6700-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="f6700-135">Se si usa la [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario usare il `<requiredRuntime>` (elemento) per tutte le versioni del runtime.</span><span class="sxs-lookup"><span data-stu-id="f6700-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="f6700-136">Il `<supportedRuntime>` elemento viene ignorato quando si usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="f6700-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="f6700-137">Il `version` stringa dell'attributo deve corrispondere al nome di cartella di installazione per la versione specificata di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6700-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="f6700-138">Questa stringa non viene interpretata.</span><span class="sxs-lookup"><span data-stu-id="f6700-138">This string is not interpreted.</span></span> <span data-ttu-id="f6700-139">Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato; il codice di avvio Mostra un messaggio di errore e viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="f6700-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="f6700-140">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f6700-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="f6700-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6700-141">Example</span></span>

<span data-ttu-id="f6700-142">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f6700-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f6700-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6700-143">See also</span></span>

- [<span data-ttu-id="f6700-144">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="f6700-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f6700-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f6700-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f6700-146">Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="f6700-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
