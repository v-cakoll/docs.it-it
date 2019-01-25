---
title: '&lt;bindingRedirect&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7fb610357772b3c74129074096c53bf3f149501a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714750"
---
# <a name="ltbindingredirectgt-element"></a><span data-ttu-id="7f437-102">&lt;bindingRedirect&gt; Element</span><span class="sxs-lookup"><span data-stu-id="7f437-102">&lt;bindingRedirect&gt; Element</span></span>
<span data-ttu-id="7f437-103">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="7f437-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="7f437-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7f437-104">\<configuration></span></span>  
<span data-ttu-id="7f437-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7f437-105">\<runtime></span></span>  
<span data-ttu-id="7f437-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="7f437-106">\<assemblyBinding></span></span>  
<span data-ttu-id="7f437-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="7f437-107">\<dependentAssembly></span></span>  
<span data-ttu-id="7f437-108">\<bindingRedirect></span><span class="sxs-lookup"><span data-stu-id="7f437-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f437-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f437-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f437-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f437-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f437-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f437-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f437-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f437-112">Attributes</span></span>  
  
|<span data-ttu-id="7f437-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f437-113">Attribute</span></span>|<span data-ttu-id="7f437-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f437-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="7f437-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f437-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f437-116">Specifica la versione dell'assembly richiesta in origine.</span><span class="sxs-lookup"><span data-stu-id="7f437-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="7f437-117">Il formato di un numero di versione assembly *revisione*.</span><span class="sxs-lookup"><span data-stu-id="7f437-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="7f437-118">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="7f437-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="7f437-119">È inoltre possibile specificare una gamma di versioni nel seguente formato:</span><span class="sxs-lookup"><span data-stu-id="7f437-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="7f437-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="7f437-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="7f437-121">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f437-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f437-122">Specifica la versione dell'assembly da utilizzare al posto della versione richiesta originariamente nel formato: *n.n.n. n*</span><span class="sxs-lookup"><span data-stu-id="7f437-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="7f437-123">Questo valore può specificare una versione precedente di `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="7f437-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f437-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f437-124">Child Elements</span></span>  
  
|<span data-ttu-id="7f437-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f437-125">Element</span></span>|<span data-ttu-id="7f437-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f437-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f437-127">nessuno</span><span class="sxs-lookup"><span data-stu-id="7f437-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="7f437-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f437-128">Parent Elements</span></span>  
  
|<span data-ttu-id="7f437-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f437-129">Element</span></span>|<span data-ttu-id="7f437-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f437-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="7f437-131">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="7f437-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="7f437-132">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f437-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="7f437-133">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="7f437-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="7f437-134">Utilizzare un elemento dependentAssembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="7f437-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="7f437-135">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f437-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f437-136">Note</span><span class="sxs-lookup"><span data-stu-id="7f437-136">Remarks</span></span>  
 <span data-ttu-id="7f437-137">Quando si compila un'applicazione .NET Framework in base a un assembly con un nome sicuro, per impostazione predefinita tale versione dell'assembly viene utilizzata dall'applicazione in fase di esecuzione, anche se è disponibile una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7f437-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="7f437-138">È possibile tuttavia configurare l'applicazione in modo che venga eseguita in base a una versione più recente dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7f437-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="7f437-139">Per informazioni dettagliate su come il runtime usa questi file per determinare la versione di assembly da usare, vedere [modo in cui il Runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="7f437-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="7f437-140">È possibile reindirizzare più versioni di assembly includendo più elementi `bindingRedirect` in un elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="7f437-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="7f437-141">È inoltre possibile reindirizzare una versione più recente a una versione precedente dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7f437-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="7f437-142">Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="7f437-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="7f437-143">che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori.</span><span class="sxs-lookup"><span data-stu-id="7f437-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="7f437-144">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag nella <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="7f437-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="7f437-145">Per altre informazioni, vedere [autorizzazione di sicurezza per il reindirizzamento di associazione Assembly](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="7f437-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f437-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f437-146">Example</span></span>  
 <span data-ttu-id="7f437-147">Nell'esempio seguente viene illustrato come reindirizzare una versione dell'assembly a un'altra.</span><span class="sxs-lookup"><span data-stu-id="7f437-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f437-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f437-148">See also</span></span>
- [<span data-ttu-id="7f437-149">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7f437-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7f437-150">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7f437-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7f437-151">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="7f437-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
