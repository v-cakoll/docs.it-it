---
title: <bindingRedirect> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: d96585b397f75dcb9fac7e7fce93799cc95e7c6c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154296"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="a2f79-102">\<bindingRedirect> Elemento</span><span class="sxs-lookup"><span data-stu-id="a2f79-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="a2f79-103">Reindirizza una versione dell'assembly in un'altra.</span><span class="sxs-lookup"><span data-stu-id="a2f79-103">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="a2f79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2f79-104">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2f79-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a2f79-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a2f79-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a2f79-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2f79-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a2f79-107">Attributes</span></span>  
  
|<span data-ttu-id="a2f79-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="a2f79-108">Attribute</span></span>|<span data-ttu-id="a2f79-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2f79-109">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="a2f79-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2f79-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="a2f79-111">Specifica la versione dell'assembly richiesta in origine.</span><span class="sxs-lookup"><span data-stu-id="a2f79-111">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="a2f79-112">Il formato di un numero di versione dell'assembly è *Major. minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="a2f79-112">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="a2f79-113">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="a2f79-113">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="a2f79-114">È inoltre possibile specificare una gamma di versioni nel seguente formato:</span><span class="sxs-lookup"><span data-stu-id="a2f79-114">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="a2f79-115">*n. n. n. n-n. n. n. n*</span><span class="sxs-lookup"><span data-stu-id="a2f79-115">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="a2f79-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2f79-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a2f79-117">Specifica la versione dell'assembly da utilizzare al posto della versione richiesta originariamente nel formato: *n* . n. n. n</span><span class="sxs-lookup"><span data-stu-id="a2f79-117">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="a2f79-118">Questo valore può specificare una versione precedente di `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="a2f79-118">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2f79-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a2f79-119">Child Elements</span></span>  
  
|<span data-ttu-id="a2f79-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2f79-120">Element</span></span>|<span data-ttu-id="a2f79-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2f79-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2f79-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="a2f79-122">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="a2f79-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a2f79-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a2f79-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2f79-124">Element</span></span>|<span data-ttu-id="a2f79-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2f79-125">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="a2f79-126">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="a2f79-126">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="a2f79-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2f79-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="a2f79-128">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="a2f79-128">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="a2f79-129">Utilizzare un elemento dependentAssembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="a2f79-129">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="a2f79-130">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2f79-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f79-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="a2f79-131">Remarks</span></span>  
 <span data-ttu-id="a2f79-132">Quando si compila un'applicazione .NET Framework in base a un assembly con un nome sicuro, per impostazione predefinita tale versione dell'assembly viene utilizzata dall'applicazione in fase di esecuzione, anche se è disponibile una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="a2f79-132">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="a2f79-133">È possibile tuttavia configurare l'applicazione in modo che venga eseguita in base a una versione più recente dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a2f79-133">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="a2f79-134">Per informazioni dettagliate sul modo in cui il runtime usa questi file per determinare quale versione dell'assembly usare, vedere [come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a2f79-134">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="a2f79-135">È possibile reindirizzare più versioni di assembly includendo più elementi `bindingRedirect` in un elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a2f79-135">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="a2f79-136">È inoltre possibile reindirizzare una versione più recente a una versione precedente dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a2f79-136">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="a2f79-137">Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="a2f79-137">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="a2f79-138">che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori.</span><span class="sxs-lookup"><span data-stu-id="a2f79-138">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="a2f79-139">L'autorizzazione viene concessa impostando il <xref:System.Security.Permissions.SecurityPermissionFlag> flag su <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="a2f79-139">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="a2f79-140">Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="a2f79-140">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2f79-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2f79-141">Example</span></span>  
 <span data-ttu-id="a2f79-142">Nell'esempio seguente viene illustrato come reindirizzare una versione dell'assembly a un'altra.</span><span class="sxs-lookup"><span data-stu-id="a2f79-142">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2f79-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a2f79-143">See also</span></span>

- [<span data-ttu-id="a2f79-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a2f79-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a2f79-145">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a2f79-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a2f79-146">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="a2f79-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
