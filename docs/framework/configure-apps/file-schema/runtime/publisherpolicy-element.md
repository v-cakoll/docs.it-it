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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115851"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="8f36b-102">\<publisherPolicy> Elemento</span><span class="sxs-lookup"><span data-stu-id="8f36b-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="8f36b-103">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="8f36b-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="8f36b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f36b-104">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f36b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8f36b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8f36b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8f36b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f36b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="8f36b-107">Attributes</span></span>  
  
|<span data-ttu-id="8f36b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="8f36b-108">Attribute</span></span>|<span data-ttu-id="8f36b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f36b-109">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="8f36b-110">Specifica se applicare i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="8f36b-110">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="8f36b-111">applica attributo</span><span class="sxs-lookup"><span data-stu-id="8f36b-111">apply Attribute</span></span>  
  
|<span data-ttu-id="8f36b-112">Valore</span><span class="sxs-lookup"><span data-stu-id="8f36b-112">Value</span></span>|<span data-ttu-id="8f36b-113">Description</span><span class="sxs-lookup"><span data-stu-id="8f36b-113">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="8f36b-114">Applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="8f36b-114">Applies publisher policy.</span></span> <span data-ttu-id="8f36b-115">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f36b-115">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="8f36b-116">Non applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="8f36b-116">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f36b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8f36b-117">Child Elements</span></span>  

<span data-ttu-id="8f36b-118">No.</span><span class="sxs-lookup"><span data-stu-id="8f36b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f36b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8f36b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8f36b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f36b-120">Element</span></span>|<span data-ttu-id="8f36b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f36b-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8f36b-122">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="8f36b-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8f36b-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f36b-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="8f36b-124">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="8f36b-124">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="8f36b-125">Usare un `<dependentAssembly>` elemento per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="8f36b-125">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="8f36b-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8f36b-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f36b-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="8f36b-127">Remarks</span></span>  
 <span data-ttu-id="8f36b-128">Quando un fornitore di componenti rilascia una nuova versione di un assembly, il fornitore può includere un criterio editore, in modo che le applicazioni che usano la versione precedente usino ora la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="8f36b-128">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="8f36b-129">Per specificare se applicare i criteri dell'editore per un particolare assembly, inserire l' **\<publisherPolicy>** elemento nell' **\<dependentAssembly>** elemento.</span><span class="sxs-lookup"><span data-stu-id="8f36b-129">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="8f36b-130">L'impostazione predefinita per l'attributo **Apply** è **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8f36b-130">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="8f36b-131">L'impostazione dell'attributo **Apply** su **No** sostituisce le impostazioni **Yes** precedenti di un assembly.</span><span class="sxs-lookup"><span data-stu-id="8f36b-131">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="8f36b-132">L'autorizzazione è necessaria affinché un'applicazione ignori esplicitamente i criteri del server di pubblicazione usando l' [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f36b-132">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="8f36b-133">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag su <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="8f36b-133">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="8f36b-134">Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="8f36b-134">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f36b-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f36b-135">Example</span></span>  
 <span data-ttu-id="8f36b-136">Nell'esempio seguente vengono disattivati i criteri dell'editore per l'assembly `myAssembly` .</span><span class="sxs-lookup"><span data-stu-id="8f36b-136">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f36b-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8f36b-137">See also</span></span>

- [<span data-ttu-id="8f36b-138">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="8f36b-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8f36b-139">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8f36b-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8f36b-140">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="8f36b-140">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8f36b-141">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="8f36b-141">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
