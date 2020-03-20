---
title: <dependentAssembly> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
ms.openlocfilehash: 2de8c752867d00708173d11d1851f415a2e8518d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154205"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="8f5f0-102">\<DependentAssembly> elemento</span><span class="sxs-lookup"><span data-stu-id="8f5f0-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="8f5f0-103">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="8f5f0-104">Utilizzare `dependentAssembly` un elemento per ogni assieme.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="8f5f0-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f5f0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f5f0-106">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f5f0-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8f5f0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="8f5f0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="8f5f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span><span class="sxs-lookup"><span data-stu-id="8f5f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f5f0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f5f0-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f5f0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8f5f0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f5f0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f5f0-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="8f5f0-112">Attributes</span></span>  
 <span data-ttu-id="8f5f0-113">No.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f5f0-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8f5f0-114">Child Elements</span></span>  
  
|<span data-ttu-id="8f5f0-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f5f0-115">Element</span></span>|<span data-ttu-id="8f5f0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f5f0-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="8f5f0-117">Contiene informazioni di identificazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="8f5f0-118">Questo elemento deve essere `dependentAssembly` incluso in ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="8f5f0-119">Specifica dove il runtime può trovare un assembly condiviso se non è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="8f5f0-120">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="8f5f0-121">Specifica se il runtime applica i criteri editore per questo assembly.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f5f0-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8f5f0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8f5f0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f5f0-123">Element</span></span>|<span data-ttu-id="8f5f0-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f5f0-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8f5f0-125">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8f5f0-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8f5f0-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8f5f0-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f5f0-128">Example</span></span>  
 <span data-ttu-id="8f5f0-129">Nell'esempio seguente viene illustrato come incapsulare le informazioni sull'assembly per due assembly.</span><span class="sxs-lookup"><span data-stu-id="8f5f0-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f5f0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f5f0-130">See also</span></span>

- [<span data-ttu-id="8f5f0-131">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="8f5f0-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8f5f0-132">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8f5f0-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8f5f0-133">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="8f5f0-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
