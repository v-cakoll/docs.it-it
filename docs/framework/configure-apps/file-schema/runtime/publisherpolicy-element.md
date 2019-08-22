---
title: <publisherPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c8f8744d3ef1ca30eb05a4c8c3290d8a514714b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663519"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="18dc7-102">\<Elemento > publisherPolicy apply</span><span class="sxs-lookup"><span data-stu-id="18dc7-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="18dc7-103">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="18dc7-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="18dc7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="18dc7-104">\<configuration></span></span>  
<span data-ttu-id="18dc7-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="18dc7-105">\<runtime></span></span>  
<span data-ttu-id="18dc7-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="18dc7-106">\<assemblyBinding></span></span>  
<span data-ttu-id="18dc7-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="18dc7-107">\<dependentAssembly></span></span>  
<span data-ttu-id="18dc7-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="18dc7-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18dc7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18dc7-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18dc7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18dc7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18dc7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18dc7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18dc7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="18dc7-112">Attributes</span></span>  
  
|<span data-ttu-id="18dc7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="18dc7-113">Attribute</span></span>|<span data-ttu-id="18dc7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18dc7-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="18dc7-115">Specifica se applicare i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="18dc7-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="18dc7-116">applica attributo</span><span class="sxs-lookup"><span data-stu-id="18dc7-116">apply Attribute</span></span>  
  
|<span data-ttu-id="18dc7-117">Value</span><span class="sxs-lookup"><span data-stu-id="18dc7-117">Value</span></span>|<span data-ttu-id="18dc7-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="18dc7-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="18dc7-119">Applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="18dc7-119">Applies publisher policy.</span></span> <span data-ttu-id="18dc7-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="18dc7-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="18dc7-121">Non applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="18dc7-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18dc7-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18dc7-122">Child Elements</span></span>  
 <span data-ttu-id="18dc7-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="18dc7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18dc7-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18dc7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="18dc7-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="18dc7-125">Element</span></span>|<span data-ttu-id="18dc7-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18dc7-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="18dc7-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18dc7-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="18dc7-128">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="18dc7-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18dc7-129">Note</span><span class="sxs-lookup"><span data-stu-id="18dc7-129">Remarks</span></span>  
 <span data-ttu-id="18dc7-130">Quando un fornitore di componenti rilascia una nuova versione di un assembly, il fornitore può includere un criterio editore, in modo che le applicazioni che usano la versione precedente usino ora la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="18dc7-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="18dc7-131">Per specificare se applicare i criteri dell'editore per un particolare assembly, inserire l'  **\<elemento > publisherPolicy apply** nell'elemento  **\<> di dependentAssembly** .</span><span class="sxs-lookup"><span data-stu-id="18dc7-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="18dc7-132">L'impostazione predefinita per l'attributo **Apply** è **Sì**.</span><span class="sxs-lookup"><span data-stu-id="18dc7-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="18dc7-133">L'impostazione dell'attributo **Apply** su **No** sostituisce le impostazioni **Yes** precedenti di un assembly.</span><span class="sxs-lookup"><span data-stu-id="18dc7-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="18dc7-134">L'autorizzazione è necessaria affinché un'applicazione ignori esplicitamente i criteri del server di pubblicazione usando l' [ \<elemento publisherPolicy apply Apply = "No"/>](publisherpolicy-element.md) nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18dc7-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="18dc7-135">L'autorizzazione viene concessa impostando <xref:System.Security.Permissions.SecurityPermissionFlag> il flag <xref:System.Security.Permissions.SecurityPermission>su.</span><span class="sxs-lookup"><span data-stu-id="18dc7-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="18dc7-136">Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="18dc7-136">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18dc7-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="18dc7-137">Example</span></span>  
 <span data-ttu-id="18dc7-138">Nell'esempio seguente vengono disattivati i criteri dell'editore `myAssembly`per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="18dc7-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18dc7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18dc7-139">See also</span></span>

- [<span data-ttu-id="18dc7-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="18dc7-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="18dc7-141">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="18dc7-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="18dc7-142">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="18dc7-142">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="18dc7-143">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="18dc7-143">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
