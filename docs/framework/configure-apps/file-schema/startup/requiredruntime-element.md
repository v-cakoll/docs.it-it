---
title: '&lt;requiredRuntime&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2e864eec2ddf51d5cc88110654f6c23f146938d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="2c8bc-102">&lt;requiredRuntime&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="2c8bc-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="2c8bc-103">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2c8bc-104">Questo elemento è deprecato e non deve più essere usato.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="2c8bc-105">Il [ `supportedRuntime` ](supportedruntime-element.md) elemento da utilizzare in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="2c8bc-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c8bc-106">\<configuration></span></span>  
<span data-ttu-id="2c8bc-107">\<startup></span><span class="sxs-lookup"><span data-stu-id="2c8bc-107">\<startup></span></span>  
<span data-ttu-id="2c8bc-108">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="2c8bc-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c8bc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c8bc-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c8bc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2c8bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c8bc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c8bc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2c8bc-112">Attributes</span></span>  
  
|<span data-ttu-id="2c8bc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2c8bc-113">Attribute</span></span>|<span data-ttu-id="2c8bc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c8bc-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="2c8bc-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2c8bc-116">Valore stringa che specifica la versione di .NET Framework supportata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="2c8bc-117">Il valore di stringa deve corrispondere al nome di directory presente nella directory principale di installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="2c8bc-118">Il contenuto del valore di stringa non viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="2c8bc-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2c8bc-120">Specifica se il codice di avvio di runtime cerca il Registro di sistema per determinare la versione di runtime.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="2c8bc-121">modalità provvisoria attributo</span><span class="sxs-lookup"><span data-stu-id="2c8bc-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="2c8bc-122">Valore</span><span class="sxs-lookup"><span data-stu-id="2c8bc-122">Value</span></span>|<span data-ttu-id="2c8bc-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c8bc-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2c8bc-124">Il codice di avvio di runtime cerca nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="2c8bc-125">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="2c8bc-126">Il codice di avvio del runtime non cerca nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c8bc-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2c8bc-127">Child Elements</span></span>  
 <span data-ttu-id="2c8bc-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c8bc-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2c8bc-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2c8bc-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c8bc-130">Element</span></span>|<span data-ttu-id="2c8bc-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c8bc-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c8bc-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="2c8bc-133">Contiene il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c8bc-134">Note</span><span class="sxs-lookup"><span data-stu-id="2c8bc-134">Remarks</span></span>  
 <span data-ttu-id="2c8bc-135">Nelle applicazioni compilate per supportare esclusivamente la versione 1.0 del runtime è necessario utilizzare il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="2c8bc-136">Le applicazioni compilate con la versione 1.1 o successiva del runtime devono utilizzare il `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c8bc-137">Se si utilizza il [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario utilizzare il `<requiredRuntime>` elemento per tutte le versioni del runtime.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="2c8bc-138">Il `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="2c8bc-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="2c8bc-139">Il `version` stringa dell'attributo deve corrispondere al nome di cartella di installazione per la versione di .NET Framework specificata.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="2c8bc-140">Questa stringa non viene interpretata.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-140">This string is not interpreted.</span></span> <span data-ttu-id="2c8bc-141">Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato; il codice di avvio di un messaggio di errore e viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c8bc-142">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c8bc-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c8bc-143">Example</span></span>  
 <span data-ttu-id="2c8bc-144">Nell'esempio seguente viene illustrato come specificare la versione di runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c8bc-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c8bc-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c8bc-145">See Also</span></span>  
 [<span data-ttu-id="2c8bc-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="2c8bc-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="2c8bc-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c8bc-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="2c8bc-148">\<PaveOver> Specifica della versione di runtime da usare</span><span class="sxs-lookup"><span data-stu-id="2c8bc-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
