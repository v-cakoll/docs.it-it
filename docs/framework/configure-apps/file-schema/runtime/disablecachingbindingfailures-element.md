---
title: '&lt;disableCachingBindingFailures&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd86bc2f58bc216f741c32a51925d3f4f8ef47df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a><span data-ttu-id="cd0d7-102">&lt;disableCachingBindingFailures&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="cd0d7-102">&lt;disableCachingBindingFailures&gt; Element</span></span>
<span data-ttu-id="cd0d7-103">Specifica se disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="cd0d7-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="cd0d7-104">\<configuration> Element</span></span>  
<span data-ttu-id="cd0d7-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="cd0d7-105">\<runtime> Element</span></span>  
<span data-ttu-id="cd0d7-106">\<disableCachingBindingFailures ></span><span class="sxs-lookup"><span data-stu-id="cd0d7-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0d7-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd0d7-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd0d7-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd0d7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd0d7-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd0d7-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd0d7-110">Attributes</span></span>  
  
|<span data-ttu-id="cd0d7-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="cd0d7-111">Attribute</span></span>|<span data-ttu-id="cd0d7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd0d7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd0d7-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cd0d7-113">enabled</span></span>|<span data-ttu-id="cd0d7-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cd0d7-115">Specifica se disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cd0d7-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="cd0d7-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cd0d7-117">Valore</span><span class="sxs-lookup"><span data-stu-id="cd0d7-117">Value</span></span>|<span data-ttu-id="cd0d7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd0d7-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cd0d7-119">0</span><span class="sxs-lookup"><span data-stu-id="cd0d7-119">0</span></span>|<span data-ttu-id="cd0d7-120">Non disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="cd0d7-121">Questo è il comportamento di associazione predefinito a partire da .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="cd0d7-122">1</span><span class="sxs-lookup"><span data-stu-id="cd0d7-122">1</span></span>|<span data-ttu-id="cd0d7-123">Disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="cd0d7-124">Questa impostazione consente di ripristinare il comportamento di associazione di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd0d7-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd0d7-125">Child Elements</span></span>  
 <span data-ttu-id="cd0d7-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd0d7-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd0d7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="cd0d7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd0d7-128">Element</span></span>|<span data-ttu-id="cd0d7-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd0d7-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cd0d7-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cd0d7-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd0d7-132">Note</span><span class="sxs-lookup"><span data-stu-id="cd0d7-132">Remarks</span></span>  
 <span data-ttu-id="cd0d7-133">A partire da .NET Framework versione 2.0, il comportamento predefinito per il caricamento degli assembly è per memorizzare nella cache tutti i binding e gli errori di caricamento.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="cd0d7-134">Ovvero, se un tentativo di caricare un assembly ha esito negativo, le successive richieste per caricare l'assembly stesso non riescono immediatamente, senza tentare di individuare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="cd0d7-135">Questo elemento disabilita il comportamento predefinito per errori di associazione che si verificano perché l'assembly non è stato trovato nel percorso di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="cd0d7-136">Questi errori generano <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="cd0d7-137">Alcuni associazione e il caricamento di errori non sono interessati da questo elemento e vengono sempre memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="cd0d7-138">Questi errori si verificano perché l'assembly è stato trovato ma non può essere caricato.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="cd0d7-139">Generano <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="cd0d7-140">Nell'elenco seguente è riportati alcuni esempi di tali errori.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="cd0d7-141">Se si tenta di caricare un file non è un assembly valido, i tentativi successivi di caricare l'assembly avrà esito negativo anche se il file non valido viene sostituito con l'assembly corretto.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="cd0d7-142">Se si tenta di caricare un assembly a cui è stato bloccato dal file system, i tentativi successivi di caricare l'assembly avrà esito negativo anche dopo che l'assembly viene rilasciata dal file system.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="cd0d7-143">Se uno o più versioni dell'assembly che si sta tentando di caricare è nel percorso di sondaggio, ma la versione che richiesta non è compreso tra loro, i tentativi successivi di caricare tale versione avrà esito negativo anche se la versione corretta viene spostata nel percorso di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd0d7-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd0d7-144">Example</span></span>  
 <span data-ttu-id="cd0d7-145">Nell'esempio seguente viene illustrato come disabilitare la memorizzazione nella cache di errori di associazione di assembly che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="cd0d7-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd0d7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd0d7-146">See Also</span></span>  
 [<span data-ttu-id="cd0d7-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="cd0d7-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="cd0d7-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="cd0d7-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="cd0d7-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="cd0d7-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
