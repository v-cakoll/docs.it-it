---
title: '&lt;codeBase&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 272a4262295b5dd67414dd0ef6523f90b2125836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="202b0-102">&lt;codeBase&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="202b0-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="202b0-103">Specifica se common language runtime può individuare un assembly.</span><span class="sxs-lookup"><span data-stu-id="202b0-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="202b0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="202b0-104">\<configuration></span></span>  
<span data-ttu-id="202b0-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="202b0-105">\<runtime></span></span>  
<span data-ttu-id="202b0-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="202b0-106">\<assemblyBinding></span></span>  
<span data-ttu-id="202b0-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="202b0-107">\<dependentAssembly></span></span>  
<span data-ttu-id="202b0-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="202b0-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="202b0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="202b0-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="202b0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="202b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="202b0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="202b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="202b0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="202b0-112">Attributes</span></span>  
  
|<span data-ttu-id="202b0-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="202b0-113">Attribute</span></span>|<span data-ttu-id="202b0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="202b0-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="202b0-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="202b0-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="202b0-116">Specifica l'URL in cui il runtime può individuare la versione specificata dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="202b0-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="202b0-117">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="202b0-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="202b0-118">Specifica la versione dell'assembly che viene applicata la codebase.</span><span class="sxs-lookup"><span data-stu-id="202b0-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="202b0-119">Il formato di un numero di versione di assembly è *revisione*.</span><span class="sxs-lookup"><span data-stu-id="202b0-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="202b0-120">Attributo di versione</span><span class="sxs-lookup"><span data-stu-id="202b0-120">version Attribute</span></span>  
  
|<span data-ttu-id="202b0-121">Valore</span><span class="sxs-lookup"><span data-stu-id="202b0-121">Value</span></span>|<span data-ttu-id="202b0-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="202b0-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="202b0-123">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="202b0-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="202b0-124">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="202b0-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="202b0-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="202b0-125">Child Elements</span></span>  
 <span data-ttu-id="202b0-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="202b0-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="202b0-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="202b0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="202b0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="202b0-128">Element</span></span>|<span data-ttu-id="202b0-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="202b0-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="202b0-130">Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati.</span><span class="sxs-lookup"><span data-stu-id="202b0-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="202b0-131">Possono essere presenti più provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="202b0-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="202b0-132">Consente di configurare tutte le impostazioni di compilazione che utilizza ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="202b0-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="202b0-133">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="202b0-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="202b0-134">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="202b0-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="202b0-135">Note</span><span class="sxs-lookup"><span data-stu-id="202b0-135">Remarks</span></span>  
 <span data-ttu-id="202b0-136">Per il runtime di utilizzare il  **\<codeBase >** impostato in un file di configurazione di computer o un file dei criteri editore, il file deve reindirizzare la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="202b0-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="202b0-137">File di configurazione dell'applicazione possono avere un'impostazione di codebase senza eseguire il reindirizzamento alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="202b0-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="202b0-138">Dopo aver determinato la versione di assembly da utilizzare, il runtime applica l'impostazione della codebase dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="202b0-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="202b0-139">Se non è indicato alcun codebase, il runtime verifica per l'assembly nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="202b0-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="202b0-140">Se l'assembly dispone di un nome sicuro, l'impostazione della codebase può essere in un punto qualsiasi nella rete intranet locale o Internet.</span><span class="sxs-lookup"><span data-stu-id="202b0-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="202b0-141">Se l'assembly è un assembly privato, l'impostazione di codebase deve essere un percorso relativo alla directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="202b0-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="202b0-142">Per gli assembly senza nome sicuro, la versione viene ignorata e il caricatore Usa la prima occorrenza di \<codebase > all'interno di \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="202b0-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="202b0-143">Se c'è una voce nel file di configurazione dell'applicazione che reindirizza l'associazione a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="202b0-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="202b0-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="202b0-144">Example</span></span>  
 <span data-ttu-id="202b0-145">Nell'esempio seguente viene illustrato come specificare in cui il runtime può individuare un assembly.</span><span class="sxs-lookup"><span data-stu-id="202b0-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="202b0-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="202b0-146">See Also</span></span>  
 [<span data-ttu-id="202b0-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="202b0-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="202b0-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="202b0-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="202b0-149">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="202b0-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="202b0-150">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="202b0-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
