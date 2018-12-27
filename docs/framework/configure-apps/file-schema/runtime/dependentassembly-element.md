---
title: '&lt;dependentAssembly&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b0d3bfb7e4db2fec39f37c9fb794731cdf5bbc
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613297"
---
# <a name="ltdependentassemblygt-element"></a><span data-ttu-id="f7e86-102">&lt;dependentAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="f7e86-102">&lt;dependentAssembly&gt; Element</span></span>
<span data-ttu-id="f7e86-103">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="f7e86-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="f7e86-104">Usare uno `dependentAssembly` (elemento) per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="f7e86-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="f7e86-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f7e86-105">\<configuration></span></span>  
<span data-ttu-id="f7e86-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="f7e86-106">\<runtime></span></span>  
<span data-ttu-id="f7e86-107">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="f7e86-107">\<assemblyBinding></span></span>  
<span data-ttu-id="f7e86-108">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="f7e86-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e86-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7e86-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7e86-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7e86-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f7e86-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7e86-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7e86-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7e86-112">Attributes</span></span>  
 <span data-ttu-id="f7e86-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f7e86-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7e86-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7e86-114">Child Elements</span></span>  
  
|<span data-ttu-id="f7e86-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7e86-115">Element</span></span>|<span data-ttu-id="f7e86-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7e86-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="f7e86-117">Contiene le informazioni di identificazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f7e86-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="f7e86-118">Questo elemento deve essere incluso in ogni `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="f7e86-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="f7e86-119">Specifica in cui il runtime può trovare un assembly condiviso se non è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="f7e86-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="f7e86-120">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="f7e86-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="f7e86-121">Specifica se il runtime applica i criteri dell'editore per questo assembly.</span><span class="sxs-lookup"><span data-stu-id="f7e86-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7e86-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7e86-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f7e86-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7e86-123">Element</span></span>|<span data-ttu-id="f7e86-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7e86-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f7e86-125">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="f7e86-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f7e86-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7e86-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f7e86-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f7e86-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f7e86-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7e86-128">Example</span></span>  
 <span data-ttu-id="f7e86-129">Nell'esempio seguente viene illustrato come incapsulare le informazioni per i due assembly.</span><span class="sxs-lookup"><span data-stu-id="f7e86-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7e86-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7e86-130">See Also</span></span>  
- [<span data-ttu-id="f7e86-131">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f7e86-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="f7e86-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7e86-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="f7e86-133">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="f7e86-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
