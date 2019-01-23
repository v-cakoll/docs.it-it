---
title: '&lt;qualifyAssembly&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84ebe43c55e2a32e24206d875c65984b8c946b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501552"
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="8496c-102">&lt;qualifyAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="8496c-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="8496c-103">Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.</span><span class="sxs-lookup"><span data-stu-id="8496c-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="8496c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8496c-104">\<configuration></span></span>  
<span data-ttu-id="8496c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="8496c-105">\<runtime></span></span>  
<span data-ttu-id="8496c-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="8496c-106">\<assemblyBinding></span></span>  
<span data-ttu-id="8496c-107">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="8496c-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8496c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8496c-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8496c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8496c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8496c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8496c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8496c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8496c-111">Attributes</span></span>  
  
|<span data-ttu-id="8496c-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8496c-112">Attribute</span></span>|<span data-ttu-id="8496c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8496c-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="8496c-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8496c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="8496c-115">Specifica il nome parziale dell'assembly come appare nel codice.</span><span class="sxs-lookup"><span data-stu-id="8496c-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="8496c-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8496c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8496c-117">Specifica il nome completo dell'assembly come appare nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="8496c-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8496c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8496c-118">Child Elements</span></span>  
 <span data-ttu-id="8496c-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8496c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8496c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8496c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8496c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8496c-121">Element</span></span>|<span data-ttu-id="8496c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8496c-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8496c-123">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="8496c-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8496c-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8496c-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8496c-125">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8496c-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8496c-126">Note</span><span class="sxs-lookup"><span data-stu-id="8496c-126">Remarks</span></span>  
 <span data-ttu-id="8496c-127">La chiamata di <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metodo usando nomi di assembly parziali fa in modo che common language runtime cercare l'assembly solo nella directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8496c-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="8496c-128">Usare la  **\<qualifyAssembly >** elemento nel file di configurazione dell'applicazione per fornire le informazioni sull'assembly (nome, versione, token di chiave pubblica e le impostazioni cultura) e causare common language runtime per la ricerca per l'assembly nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="8496c-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="8496c-129">Il **fullName** attributo deve includere quattro campi di identità dell'assembly: nome, versione, token di chiave pubblica e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="8496c-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="8496c-130">Il **partialName** attributo parzialmente deve fare riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="8496c-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="8496c-131">È necessario specificare almeno il nome dell'assembly testo (il caso più comune), ma è anche possibile includere una versione, token di chiave pubblica o le impostazioni cultura (o qualsiasi combinazione di quattro, ma non tutte e quattro).</span><span class="sxs-lookup"><span data-stu-id="8496c-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="8496c-132">Il **partialName** deve corrispondere al nome specificato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="8496c-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="8496c-133">Ad esempio, non è possibile specificare `"math"` come il **partialName** attributo nel file di configurazione e chiamare `Assembly.Load("math, Version=3.3.3.3")` nel codice.</span><span class="sxs-lookup"><span data-stu-id="8496c-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8496c-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="8496c-134">Example</span></span>  
 <span data-ttu-id="8496c-135">L'esempio seguente consente in modo logico la chiamata `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="8496c-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8496c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8496c-136">See also</span></span>
- [<span data-ttu-id="8496c-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="8496c-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="8496c-138">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="8496c-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8496c-139">NIB: Riferimenti ad Assembly parziali</span><span class="sxs-lookup"><span data-stu-id="8496c-139">NIB: Partial Assembly References</span></span>](https://msdn.microsoft.com/library/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
