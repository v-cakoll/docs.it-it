---
title: '&lt;dependentAssembly&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a968d2d1abf6e77cddd9d0a0367822ee4f9723ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdependentassemblygt-element"></a><span data-ttu-id="75f33-102">&lt;dependentAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="75f33-102">&lt;dependentAssembly&gt; Element</span></span>
<span data-ttu-id="75f33-103">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="75f33-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="75f33-104">Utilizzare uno `dependentAssembly` elemento per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="75f33-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="75f33-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75f33-105">\<configuration></span></span>  
<span data-ttu-id="75f33-106">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="75f33-106">\<runtime></span></span>  
<span data-ttu-id="75f33-107">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="75f33-107">\<assemblyBinding></span></span>  
<span data-ttu-id="75f33-108">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="75f33-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f33-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75f33-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75f33-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75f33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75f33-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75f33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75f33-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="75f33-112">Attributes</span></span>  
 <span data-ttu-id="75f33-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="75f33-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75f33-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75f33-114">Child Elements</span></span>  
  
|<span data-ttu-id="75f33-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="75f33-115">Element</span></span>|<span data-ttu-id="75f33-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f33-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="75f33-117">Contiene le informazioni di identificazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="75f33-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="75f33-118">Questo elemento deve essere incluso in ogni `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="75f33-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="75f33-119">Specifica in cui il runtime trova un assembly condiviso se non è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="75f33-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="75f33-120">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="75f33-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="75f33-121">Specifica se il runtime applica i criteri dell'editore per questo assembly.</span><span class="sxs-lookup"><span data-stu-id="75f33-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75f33-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75f33-122">Parent Elements</span></span>  
  
|<span data-ttu-id="75f33-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="75f33-123">Element</span></span>|<span data-ttu-id="75f33-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f33-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="75f33-125">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="75f33-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="75f33-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75f33-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="75f33-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="75f33-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75f33-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="75f33-128">Example</span></span>  
 <span data-ttu-id="75f33-129">Nell'esempio seguente viene illustrato come incapsulare le informazioni per due assembly.</span><span class="sxs-lookup"><span data-stu-id="75f33-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75f33-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f33-130">See Also</span></span>  
 [<span data-ttu-id="75f33-131">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="75f33-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="75f33-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="75f33-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="75f33-133">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="75f33-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
