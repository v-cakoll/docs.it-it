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
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115851"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="1a676-102">\<elemento > publisherPolicy apply</span><span class="sxs-lookup"><span data-stu-id="1a676-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="1a676-103">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="1a676-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="1a676-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a676-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a676-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="1a676-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="1a676-106">&nbsp; &nbsp;[ \**&nbsp; &nbsp; \<assemblyBinding > \** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="1a676-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\</span></span>
<span data-ttu-id="1a676-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**dependentAssembly**](dependentassembly-element.md) ></span><span class="sxs-lookup"><span data-stu-id="1a676-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="1a676-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherPolicy apply** ></span><span class="sxs-lookup"><span data-stu-id="1a676-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a676-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a676-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a676-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1a676-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1a676-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1a676-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a676-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1a676-112">Attributes</span></span>  
  
|<span data-ttu-id="1a676-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1a676-113">Attribute</span></span>|<span data-ttu-id="1a676-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a676-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="1a676-115">Specifica se applicare i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="1a676-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="1a676-116">applica attributo</span><span class="sxs-lookup"><span data-stu-id="1a676-116">apply Attribute</span></span>  
  
|<span data-ttu-id="1a676-117">Value</span><span class="sxs-lookup"><span data-stu-id="1a676-117">Value</span></span>|<span data-ttu-id="1a676-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a676-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="1a676-119">Applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="1a676-119">Applies publisher policy.</span></span> <span data-ttu-id="1a676-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1a676-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="1a676-121">Non applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="1a676-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a676-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1a676-122">Child Elements</span></span>  

<span data-ttu-id="1a676-123">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="1a676-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a676-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1a676-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1a676-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a676-125">Element</span></span>|<span data-ttu-id="1a676-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a676-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="1a676-127">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="1a676-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="1a676-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a676-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="1a676-129">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="1a676-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="1a676-130">Usare un elemento `<dependentAssembly>` per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="1a676-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="1a676-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a676-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a676-132">Note</span><span class="sxs-lookup"><span data-stu-id="1a676-132">Remarks</span></span>  
 <span data-ttu-id="1a676-133">Quando un fornitore di componenti rilascia una nuova versione di un assembly, il fornitore può includere un criterio editore, in modo che le applicazioni che usano la versione precedente usino ora la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="1a676-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="1a676-134">Per specificare se applicare i criteri dell'editore per un particolare assembly, inserire l'elemento **\<publisherpolicy apply >** nell'elemento **\<dependentAssembly >** .</span><span class="sxs-lookup"><span data-stu-id="1a676-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="1a676-135">L'impostazione predefinita per l'attributo **Apply** è **Sì**.</span><span class="sxs-lookup"><span data-stu-id="1a676-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="1a676-136">L'impostazione dell'attributo **Apply** su **No** sostituisce le impostazioni **Yes** precedenti di un assembly.</span><span class="sxs-lookup"><span data-stu-id="1a676-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="1a676-137">L'autorizzazione è necessaria affinché un'applicazione ignori esplicitamente i criteri del server di pubblicazione utilizzando l'elemento [\<publisherPolicy apply Apply = "No"/>](publisherpolicy-element.md) nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a676-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="1a676-138">L'autorizzazione viene concessa impostando il flag di <xref:System.Security.Permissions.SecurityPermissionFlag> nel <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="1a676-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="1a676-139">Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="1a676-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a676-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a676-140">Example</span></span>  
 <span data-ttu-id="1a676-141">Nell'esempio seguente vengono disattivati i criteri dell'editore per l'assembly, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1a676-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a676-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a676-142">See also</span></span>

- [<span data-ttu-id="1a676-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1a676-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1a676-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1a676-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1a676-145">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="1a676-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1a676-146">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="1a676-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
