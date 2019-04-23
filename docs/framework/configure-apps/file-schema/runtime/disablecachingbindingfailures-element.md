---
title: <disableCachingBindingFailures> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4893adaf528f1a9ef8fc8eab8027406fd8520cc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159276"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="d3458-102">\<disableCachingBindingFailures > elemento</span><span class="sxs-lookup"><span data-stu-id="d3458-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="d3458-103">Specifica se disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.</span><span class="sxs-lookup"><span data-stu-id="d3458-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="d3458-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="d3458-104">\<configuration> Element</span></span>  
<span data-ttu-id="d3458-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="d3458-105">\<runtime> Element</span></span>  
<span data-ttu-id="d3458-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="d3458-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3458-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3458-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3458-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d3458-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d3458-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d3458-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3458-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d3458-110">Attributes</span></span>  
  
|<span data-ttu-id="d3458-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d3458-111">Attribute</span></span>|<span data-ttu-id="d3458-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3458-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3458-113">enabled</span><span class="sxs-lookup"><span data-stu-id="d3458-113">enabled</span></span>|<span data-ttu-id="d3458-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3458-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d3458-115">Specifica se disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.</span><span class="sxs-lookup"><span data-stu-id="d3458-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d3458-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="d3458-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="d3458-117">Valore</span><span class="sxs-lookup"><span data-stu-id="d3458-117">Value</span></span>|<span data-ttu-id="d3458-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3458-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3458-119">0</span><span class="sxs-lookup"><span data-stu-id="d3458-119">0</span></span>|<span data-ttu-id="d3458-120">Non disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.</span><span class="sxs-lookup"><span data-stu-id="d3458-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="d3458-121">Questo è il comportamento predefinito dell'associazione a partire da .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="d3458-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="d3458-122">1</span><span class="sxs-lookup"><span data-stu-id="d3458-122">1</span></span>|<span data-ttu-id="d3458-123">Disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.</span><span class="sxs-lookup"><span data-stu-id="d3458-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="d3458-124">Questa impostazione consente di ripristinare il comportamento di associazione di .NET Framework versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="d3458-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3458-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d3458-125">Child Elements</span></span>  
 <span data-ttu-id="d3458-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d3458-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3458-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d3458-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d3458-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3458-128">Element</span></span>|<span data-ttu-id="d3458-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3458-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d3458-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3458-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d3458-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d3458-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3458-132">Note</span><span class="sxs-lookup"><span data-stu-id="d3458-132">Remarks</span></span>  
 <span data-ttu-id="d3458-133">A partire da .NET Framework versione 2.0, il comportamento predefinito per il caricamento degli assembly è per memorizzare nella cache tutti i binding e gli errori di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d3458-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="d3458-134">Vale a dire, se non riesce un tentativo di caricare un assembly, le successive richieste per caricare l'assembly stesso immediatamente esito negativo, senza tentare di individuare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d3458-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="d3458-135">Questo elemento consente di disattivare il comportamento predefinito per gli errori che si verificano perché l'assembly non è stato trovato nel percorso di sondaggio di associazione.</span><span class="sxs-lookup"><span data-stu-id="d3458-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="d3458-136">Questi errori generano <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="d3458-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="d3458-137">Associazione di alcuni errori di caricamento non sono interessati da questo elemento e vengono sempre memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="d3458-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="d3458-138">Questi errori si verificano perché l'assembly è stato trovato ma non può essere caricato.</span><span class="sxs-lookup"><span data-stu-id="d3458-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="d3458-139">Generano <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="d3458-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="d3458-140">Nell'elenco seguente sono riportati alcuni esempi di tali errori.</span><span class="sxs-lookup"><span data-stu-id="d3458-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="d3458-141">Se si tenta di caricare un file non è un assembly valido, i tentativi successivi per caricare l'assembly avrà esito negativo anche se il file non valido viene sostituito con l'assembly corretto.</span><span class="sxs-lookup"><span data-stu-id="d3458-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="d3458-142">Se si tenta di caricare un assembly che è stato bloccato dal file system, i tentativi successivi per caricare l'assembly avrà esito negativo anche dopo che l'assembly viene rilasciata dal file system.</span><span class="sxs-lookup"><span data-stu-id="d3458-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="d3458-143">Se uno o più versioni dell'assembly che si sta tentando di caricare è nel percorso di sondaggio, ma la versione specifica di che richiesta non è tra di essi, i tentativi successivi di caricare tale versione avrà esito negativo anche se la versione corretta verrà spostata nel percorso di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d3458-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3458-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3458-144">Example</span></span>  
 <span data-ttu-id="d3458-145">Nell'esempio seguente viene illustrato come disabilitare la memorizzazione nella cache di errori di associazione di assembly che si verificano perché l'assembly non è stato trovato il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d3458-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3458-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3458-146">See also</span></span>

- [<span data-ttu-id="d3458-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="d3458-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d3458-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d3458-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d3458-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="d3458-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
