---
title: <qualifyAssembly> Elemento
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
ms.openlocfilehash: 4aa90a378630c9aff74923d8e8600aed15a77a5e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663495"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="adfa4-102">\<Elemento > qualifyAssembly</span><span class="sxs-lookup"><span data-stu-id="adfa4-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="adfa4-103">Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.</span><span class="sxs-lookup"><span data-stu-id="adfa4-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="adfa4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="adfa4-104">\<configuration></span></span>  
<span data-ttu-id="adfa4-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="adfa4-105">\<runtime></span></span>  
<span data-ttu-id="adfa4-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="adfa4-106">\<assemblyBinding></span></span>  
<span data-ttu-id="adfa4-107">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="adfa4-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfa4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adfa4-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adfa4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="adfa4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="adfa4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="adfa4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adfa4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="adfa4-111">Attributes</span></span>  
  
|<span data-ttu-id="adfa4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="adfa4-112">Attribute</span></span>|<span data-ttu-id="adfa4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="adfa4-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="adfa4-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="adfa4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="adfa4-115">Specifica il nome parziale dell'assembly come appare nel codice.</span><span class="sxs-lookup"><span data-stu-id="adfa4-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="adfa4-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="adfa4-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="adfa4-117">Specifica il nome completo dell'assembly visualizzato nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="adfa4-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adfa4-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="adfa4-118">Child Elements</span></span>  
 <span data-ttu-id="adfa4-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="adfa4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adfa4-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="adfa4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="adfa4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="adfa4-121">Element</span></span>|<span data-ttu-id="adfa4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="adfa4-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="adfa4-123">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="adfa4-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="adfa4-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="adfa4-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="adfa4-125">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="adfa4-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adfa4-126">Note</span><span class="sxs-lookup"><span data-stu-id="adfa4-126">Remarks</span></span>  
 <span data-ttu-id="adfa4-127">Quando si <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> chiama il metodo utilizzando nomi di assembly parziali, il Common Language Runtime cerca l'assembly solo nella directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="adfa4-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="adfa4-128">Usare l'  **\<elemento > qualifyAssembly** nel file di configurazione dell'applicazione per fornire le informazioni complete sull'assembly (nome, versione, token di chiave pubblica e impostazioni cultura) e fare in modo che il Common Language Runtime cerchi l'assembly nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="adfa4-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="adfa4-129">L'attributo **FullName** deve includere i quattro campi dell'identità dell'assembly: nome, versione, token di chiave pubblica e impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="adfa4-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="adfa4-130">L' attributo parzialname deve fare riferimento parzialmente a un assembly.</span><span class="sxs-lookup"><span data-stu-id="adfa4-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="adfa4-131">È necessario specificare almeno il nome di testo dell'assembly (caso più comune), ma è anche possibile includere la versione, il token di chiave pubblica o le impostazioni cultura (o qualsiasi combinazione dei quattro, ma non tutti e quattro).</span><span class="sxs-lookup"><span data-stu-id="adfa4-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="adfa4-132">Il parametro partial deve corrispondere al nome specificato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="adfa4-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="adfa4-133">Ad esempio, non è possibile `"math"` specificare come attributo parzialname nel file di configurazione e chiamare `Assembly.Load("math, Version=3.3.3.3")` nel codice.</span><span class="sxs-lookup"><span data-stu-id="adfa4-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfa4-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="adfa4-134">Example</span></span>  
 <span data-ttu-id="adfa4-135">Nell'esempio seguente viene logicamente svolta la chiamata `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="adfa4-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="adfa4-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adfa4-136">See also</span></span>

- [<span data-ttu-id="adfa4-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="adfa4-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="adfa4-138">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="adfa4-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="adfa4-139">[Riferimenti a assembly parziali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="adfa4-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
