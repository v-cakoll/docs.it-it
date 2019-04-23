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
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076289"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="5ae62-102">\<publisherPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="5ae62-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="5ae62-103">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="5ae62-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="5ae62-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5ae62-104">\<configuration></span></span>  
<span data-ttu-id="5ae62-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="5ae62-105">\<runtime></span></span>  
<span data-ttu-id="5ae62-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="5ae62-106">\<assemblyBinding></span></span>  
<span data-ttu-id="5ae62-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="5ae62-107">\<dependentAssembly></span></span>  
<span data-ttu-id="5ae62-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="5ae62-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae62-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ae62-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ae62-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5ae62-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5ae62-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5ae62-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ae62-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5ae62-112">Attributes</span></span>  
  
|<span data-ttu-id="5ae62-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5ae62-113">Attribute</span></span>|<span data-ttu-id="5ae62-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae62-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="5ae62-115">Specifica se applicare i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="5ae62-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="5ae62-116">applicare l'attributo</span><span class="sxs-lookup"><span data-stu-id="5ae62-116">apply Attribute</span></span>  
  
|<span data-ttu-id="5ae62-117">Value</span><span class="sxs-lookup"><span data-stu-id="5ae62-117">Value</span></span>|<span data-ttu-id="5ae62-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae62-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="5ae62-119">Applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="5ae62-119">Applies publisher policy.</span></span> <span data-ttu-id="5ae62-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5ae62-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="5ae62-121">Non si applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="5ae62-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ae62-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5ae62-122">Child Elements</span></span>  
 <span data-ttu-id="5ae62-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5ae62-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ae62-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5ae62-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5ae62-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ae62-125">Element</span></span>|<span data-ttu-id="5ae62-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ae62-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5ae62-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ae62-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5ae62-128">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5ae62-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ae62-129">Note</span><span class="sxs-lookup"><span data-stu-id="5ae62-129">Remarks</span></span>  
 <span data-ttu-id="5ae62-130">Quando un fornitore del componente rilascia una nuova versione di un assembly, il fornitore può includere un criterio server di pubblicazione in modo che le applicazioni che usano la versione precedente a questo punto usano la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="5ae62-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="5ae62-131">Per specificare se applicare i criteri dell'editore per un determinato assembly, inserire il  **\<publisherPolicy >** elemento il  **\<dependentAssembly >** elemento.</span><span class="sxs-lookup"><span data-stu-id="5ae62-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="5ae62-132">L'impostazione predefinita per il **si applicano** attributo **yes**.</span><span class="sxs-lookup"><span data-stu-id="5ae62-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="5ae62-133">Impostando il **si applicano** dell'attributo **alcun** sostituzioni quelli precedenti **Sì** le impostazioni per un assembly.</span><span class="sxs-lookup"><span data-stu-id="5ae62-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="5ae62-134">L'autorizzazione è necessaria per un'applicazione ignorare in modo esplicito server di pubblicazione dei criteri tramite il [ \<publisherPolicy applicare = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ae62-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="5ae62-135">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag nella <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="5ae62-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="5ae62-136">Per altre informazioni, vedere [autorizzazione di sicurezza per il reindirizzamento di associazione Assembly](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="5ae62-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ae62-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ae62-137">Example</span></span>  
 <span data-ttu-id="5ae62-138">Nell'esempio seguente consente di disattivare i criteri dell'editore per l'assembly, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="5ae62-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ae62-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae62-139">See also</span></span>

- [<span data-ttu-id="5ae62-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="5ae62-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="5ae62-141">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="5ae62-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5ae62-142">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="5ae62-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="5ae62-143">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="5ae62-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
