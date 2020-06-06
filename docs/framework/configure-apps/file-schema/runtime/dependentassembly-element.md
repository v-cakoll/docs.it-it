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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154205"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="7970b-102">\<dependentAssembly> Elemento</span><span class="sxs-lookup"><span data-stu-id="7970b-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="7970b-103">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="7970b-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="7970b-104">Usare un `dependentAssembly` elemento per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="7970b-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="7970b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7970b-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7970b-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7970b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="7970b-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7970b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7970b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="7970b-108">Attributes</span></span>  
 <span data-ttu-id="7970b-109">No.</span><span class="sxs-lookup"><span data-stu-id="7970b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7970b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7970b-110">Child Elements</span></span>  
  
|<span data-ttu-id="7970b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="7970b-111">Element</span></span>|<span data-ttu-id="7970b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7970b-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="7970b-113">Contiene informazioni di identificazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="7970b-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="7970b-114">Questo elemento deve essere incluso in ogni `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="7970b-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="7970b-115">Specifica la posizione in cui il runtime può trovare un assembly condiviso se non è installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="7970b-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="7970b-116">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="7970b-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="7970b-117">Specifica se il runtime applica i criteri dell'editore per questo assembly.</span><span class="sxs-lookup"><span data-stu-id="7970b-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7970b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7970b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7970b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="7970b-119">Element</span></span>|<span data-ttu-id="7970b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7970b-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="7970b-121">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="7970b-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="7970b-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7970b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7970b-123">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7970b-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7970b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7970b-124">Example</span></span>  
 <span data-ttu-id="7970b-125">Nell'esempio seguente viene illustrato come incapsulare le informazioni sull'assembly per due assembly.</span><span class="sxs-lookup"><span data-stu-id="7970b-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7970b-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7970b-126">See also</span></span>

- [<span data-ttu-id="7970b-127">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7970b-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7970b-128">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7970b-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7970b-129">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="7970b-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
