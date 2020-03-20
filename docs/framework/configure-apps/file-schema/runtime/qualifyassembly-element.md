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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153919"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="842ff-102">\<elemento> qualifyAssembly</span><span class="sxs-lookup"><span data-stu-id="842ff-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="842ff-103">Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.</span><span class="sxs-lookup"><span data-stu-id="842ff-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="842ff-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="842ff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="842ff-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="842ff-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="842ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="842ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="842ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualificareAssembly>**</span><span class="sxs-lookup"><span data-stu-id="842ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842ff-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="842ff-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="842ff-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="842ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="842ff-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="842ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="842ff-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="842ff-111">Attributes</span></span>  
  
|<span data-ttu-id="842ff-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="842ff-112">Attribute</span></span>|<span data-ttu-id="842ff-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="842ff-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="842ff-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="842ff-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="842ff-115">Specifica il nome parziale dell'assembly così come viene visualizzato nel codice.</span><span class="sxs-lookup"><span data-stu-id="842ff-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="842ff-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="842ff-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="842ff-117">Specifica il nome completo dell'assembly così come viene visualizzato nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="842ff-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="842ff-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="842ff-118">Child Elements</span></span>  
 <span data-ttu-id="842ff-119">No.</span><span class="sxs-lookup"><span data-stu-id="842ff-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="842ff-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="842ff-120">Parent Elements</span></span>  
  
|<span data-ttu-id="842ff-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="842ff-121">Element</span></span>|<span data-ttu-id="842ff-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="842ff-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="842ff-123">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="842ff-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="842ff-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="842ff-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="842ff-125">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="842ff-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="842ff-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="842ff-126">Remarks</span></span>  
 <span data-ttu-id="842ff-127">La <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> chiamata al metodo utilizzando nomi di assembly parziali fa sì che Common Language Runtime cerchi l'assembly solo nella directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="842ff-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="842ff-128">Utilizzare l'elemento \*\* \<>qualifyAssembly\*\* nel file di configurazione dell'applicazione per fornire le informazioni complete sull'assembly (nome, versione, token di chiave pubblica e impostazioni cultura) e fare in modo che Common Language Runtime cerchi l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="842ff-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="842ff-129">L'attributo **fullName** deve includere i quattro campi dell'identità dell'assembly: name, version, public key token e culture.</span><span class="sxs-lookup"><span data-stu-id="842ff-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="842ff-130">L'attributo **partialName** deve fare riferimento parzialmente a un assembly.</span><span class="sxs-lookup"><span data-stu-id="842ff-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="842ff-131">È necessario specificare almeno il nome di testo dell'assembly (il caso più comune), ma è anche possibile includere la versione, il token di chiave pubblica o le impostazioni cultura (o qualsiasi combinazione dei quattro, ma non tutti e quattro).</span><span class="sxs-lookup"><span data-stu-id="842ff-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="842ff-132">Il **partialName** deve corrispondere al nome specificato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="842ff-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="842ff-133">Ad esempio, non `"math"` è possibile specificare come attributo **partialName** nel file di configurazione e chiamare `Assembly.Load("math, Version=3.3.3.3")` nel codice.</span><span class="sxs-lookup"><span data-stu-id="842ff-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842ff-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="842ff-134">Example</span></span>  
 <span data-ttu-id="842ff-135">Nell'esempio riportato di `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`seguito la chiamata viene trasformata in modo logico in .</span><span class="sxs-lookup"><span data-stu-id="842ff-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="842ff-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="842ff-136">See also</span></span>

- [<span data-ttu-id="842ff-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="842ff-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="842ff-138">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="842ff-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="842ff-139">[Riferimenti di assembly parziali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="842ff-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
