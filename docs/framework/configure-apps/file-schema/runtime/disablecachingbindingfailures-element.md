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
ms.openlocfilehash: 23633cb282b8e59b4df4bcc2cd38717d805a207e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117503"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="06606-102">\<elemento > disableCachingBindingFailures</span><span class="sxs-lookup"><span data-stu-id="06606-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="06606-103">Specifica se disabilitare la memorizzazione nella cache degli errori di associazione che si verificano perché l'assembly non è stato trovato da Probe.</span><span class="sxs-lookup"><span data-stu-id="06606-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
<span data-ttu-id="06606-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="06606-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="06606-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="06606-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="06606-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disableCachingBindingFailures >**</span><span class="sxs-lookup"><span data-stu-id="06606-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06606-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06606-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06606-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="06606-108">Attributes and Elements</span></span>  
 <span data-ttu-id="06606-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="06606-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06606-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="06606-110">Attributes</span></span>  
  
|<span data-ttu-id="06606-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="06606-111">Attribute</span></span>|<span data-ttu-id="06606-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06606-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06606-113">enabled</span><span class="sxs-lookup"><span data-stu-id="06606-113">enabled</span></span>|<span data-ttu-id="06606-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="06606-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="06606-115">Specifica se disabilitare la memorizzazione nella cache degli errori di associazione che si verificano perché l'assembly non è stato trovato da Probe.</span><span class="sxs-lookup"><span data-stu-id="06606-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="06606-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="06606-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="06606-117">Value</span><span class="sxs-lookup"><span data-stu-id="06606-117">Value</span></span>|<span data-ttu-id="06606-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06606-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="06606-119">0</span><span class="sxs-lookup"><span data-stu-id="06606-119">0</span></span>|<span data-ttu-id="06606-120">Non disabilitare la memorizzazione nella cache degli errori di associazione che si verificano perché l'assembly non è stato trovato da Probe.</span><span class="sxs-lookup"><span data-stu-id="06606-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="06606-121">Questo è il comportamento di binding predefinito a partire dalla versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="06606-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="06606-122">1</span><span class="sxs-lookup"><span data-stu-id="06606-122">1</span></span>|<span data-ttu-id="06606-123">Disabilitare la memorizzazione nella cache degli errori di associazione che si verificano perché l'assembly non è stato trovato da Probe.</span><span class="sxs-lookup"><span data-stu-id="06606-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="06606-124">Questa impostazione ripristina il comportamento di associazione della .NET Framework versione 1,1.</span><span class="sxs-lookup"><span data-stu-id="06606-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06606-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="06606-125">Child Elements</span></span>  
 <span data-ttu-id="06606-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="06606-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06606-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="06606-127">Parent Elements</span></span>  
  
|<span data-ttu-id="06606-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="06606-128">Element</span></span>|<span data-ttu-id="06606-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="06606-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06606-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="06606-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="06606-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="06606-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06606-132">Note</span><span class="sxs-lookup"><span data-stu-id="06606-132">Remarks</span></span>  
 <span data-ttu-id="06606-133">A partire dalla versione di .NET Framework 2,0, il comportamento predefinito per il caricamento degli assembly consiste nel memorizzare nella cache tutti gli errori di binding e caricamento.</span><span class="sxs-lookup"><span data-stu-id="06606-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="06606-134">Ovvero, se il tentativo di caricamento di un assembly ha esito negativo, le successive richieste di caricamento dello stesso assembly hanno esito negativo, senza alcun tentativo di individuazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="06606-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="06606-135">Questo elemento Disabilita il comportamento predefinito per gli errori di associazione che si verificano perché l'assembly non è stato trovato nel percorso di probe.</span><span class="sxs-lookup"><span data-stu-id="06606-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="06606-136">Questi errori generano <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="06606-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="06606-137">Alcuni errori di binding e caricamento non sono interessati da questo elemento e vengono sempre memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="06606-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="06606-138">Questi errori si verificano perché l'assembly è stato trovato ma non è stato possibile caricarlo.</span><span class="sxs-lookup"><span data-stu-id="06606-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="06606-139">Generano <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="06606-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="06606-140">Nell'elenco seguente sono inclusi alcuni esempi di tali errori.</span><span class="sxs-lookup"><span data-stu-id="06606-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="06606-141">Se si tenta di caricare un file non è un assembly valido, i tentativi successivi di caricamento dell'assembly avranno esito negativo anche se il file danneggiato viene sostituito con l'assembly corretto.</span><span class="sxs-lookup"><span data-stu-id="06606-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="06606-142">Se si tenta di caricare un assembly bloccato dal file system, i tentativi successivi di caricamento dell'assembly avranno esito negativo anche dopo che l'assembly verrà rilasciato dal file system.</span><span class="sxs-lookup"><span data-stu-id="06606-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="06606-143">Se una o più versioni dell'assembly che si sta tentando di caricare si trovano nel percorso di sondaggio, ma la versione specifica richiesta non è tra di esse, i successivi tentativi di caricamento della versione avranno esito negativo anche se la versione corretta viene spostata nel percorso di sondaggio.</span><span class="sxs-lookup"><span data-stu-id="06606-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06606-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="06606-144">Example</span></span>  
 <span data-ttu-id="06606-145">Nell'esempio seguente viene illustrato come disabilitare la memorizzazione nella cache degli errori di associazione degli assembly che si verificano perché l'assembly non è stato trovato da Probe.</span><span class="sxs-lookup"><span data-stu-id="06606-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06606-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06606-146">See also</span></span>

- [<span data-ttu-id="06606-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="06606-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="06606-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="06606-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="06606-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="06606-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
