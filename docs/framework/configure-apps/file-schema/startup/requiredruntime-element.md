---
title: '&lt;requiredRuntime&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ac1e1f7bc36d8d2b12b99de2794bb0ba31ddbd7a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518647"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="bfdf3-102">&lt;requiredRuntime&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="bfdf3-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="bfdf3-103">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="bfdf3-104">Questo elemento è deprecato e non deve più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="bfdf3-105">Il [ `supportedRuntime` ](supportedruntime-element.md) elemento deve essere usato invece.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="bfdf3-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bfdf3-106">\<configuration></span></span>  
<span data-ttu-id="bfdf3-107">\<startup></span><span class="sxs-lookup"><span data-stu-id="bfdf3-107">\<startup></span></span>  
<span data-ttu-id="bfdf3-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="bfdf3-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdf3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfdf3-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfdf3-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bfdf3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bfdf3-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfdf3-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="bfdf3-112">Attributes</span></span>  
  
|<span data-ttu-id="bfdf3-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="bfdf3-113">Attribute</span></span>|<span data-ttu-id="bfdf3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfdf3-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="bfdf3-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bfdf3-116">Valore stringa che specifica la versione di .NET Framework supportata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="bfdf3-117">Il valore della stringa deve corrispondere al nome di directory trovato nella directory radice di installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="bfdf3-118">Il contenuto del valore della stringa non viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="bfdf3-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bfdf3-120">Specifica se il codice di avvio di runtime cerca il Registro di sistema per determinare la versione di runtime.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="bfdf3-121">modalità provvisoria attributo</span><span class="sxs-lookup"><span data-stu-id="bfdf3-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="bfdf3-122">Valore</span><span class="sxs-lookup"><span data-stu-id="bfdf3-122">Value</span></span>|<span data-ttu-id="bfdf3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfdf3-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bfdf3-124">Il codice di avvio di runtime cerca nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="bfdf3-125">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="bfdf3-126">Il codice di avvio del runtime non cercare nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfdf3-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bfdf3-127">Child Elements</span></span>  
 <span data-ttu-id="bfdf3-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfdf3-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bfdf3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="bfdf3-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfdf3-130">Element</span></span>|<span data-ttu-id="bfdf3-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfdf3-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bfdf3-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="bfdf3-133">Contiene il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfdf3-134">Note</span><span class="sxs-lookup"><span data-stu-id="bfdf3-134">Remarks</span></span>  
 <span data-ttu-id="bfdf3-135">Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="bfdf3-136">Le applicazioni compilate con la versione 1.1 o versione successiva del runtime devono usare il `<supportedRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfdf3-137">Se si usa la [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario usare il `<requiredRuntime>` (elemento) per tutte le versioni del runtime.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="bfdf3-138">Il `<supportedRuntime>` elemento viene ignorato quando si usa [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="bfdf3-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="bfdf3-139">Il `version` stringa dell'attributo deve corrispondere al nome di cartella di installazione per la versione specificata di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="bfdf3-140">Questa stringa non viene interpretata.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-140">This string is not interpreted.</span></span> <span data-ttu-id="bfdf3-141">Se il codice di avvio del runtime non trova una cartella corrispondente, il runtime non viene caricato; il codice di avvio Mostra un messaggio di errore e viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfdf3-142">Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il `<requiredRuntime>` elemento.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfdf3-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfdf3-143">Example</span></span>  
 <span data-ttu-id="bfdf3-144">Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bfdf3-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfdf3-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfdf3-145">See Also</span></span>  
 [<span data-ttu-id="bfdf3-146">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="bfdf3-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="bfdf3-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bfdf3-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bfdf3-148">\<PaveOver> Specifica della versione di runtime da usare</span><span class="sxs-lookup"><span data-stu-id="bfdf3-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
