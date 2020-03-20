---
title: Elemento <assemblyIdentity> per <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154309"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="28324-102">\<Elemento> assemblyIdentity per \<la> di runtime</span><span class="sxs-lookup"><span data-stu-id="28324-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="28324-103">Contiene informazioni di identificazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="28324-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="28324-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28324-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28324-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="28324-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="28324-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="28324-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="28324-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="28324-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="28324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span><span class="sxs-lookup"><span data-stu-id="28324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28324-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28324-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28324-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="28324-110">Attributes and Elements</span></span>  
 <span data-ttu-id="28324-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="28324-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28324-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="28324-112">Attributes</span></span>  
  
|<span data-ttu-id="28324-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="28324-113">Attribute</span></span>|<span data-ttu-id="28324-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28324-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="28324-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="28324-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="28324-116">Il nome dell'assembly</span><span class="sxs-lookup"><span data-stu-id="28324-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="28324-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="28324-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28324-118">Stringa che specifica la lingua e il paese dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="28324-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="28324-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="28324-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28324-120">Valore esadecimale che specifica il nome sicuro dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="28324-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="28324-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="28324-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="28324-122">Uno dei valori "x86", "amd64", "msil" o "ia64", specificando l'architettura del processore per un assembly che contiene codice specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="28324-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="28324-123">Per i valori non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="28324-123">The values are not case-sensitive.</span></span> <span data-ttu-id="28324-124">Se all'attributo viene assegnato `<assemblyIdentity>` qualsiasi altro valore, l'intero elemento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="28324-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="28324-125">Vedere <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="28324-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="28324-126">Attributo processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="28324-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="28324-127">valore</span><span class="sxs-lookup"><span data-stu-id="28324-127">Value</span></span>|<span data-ttu-id="28324-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28324-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="28324-129">Solo architettura AMD x86-64.</span><span class="sxs-lookup"><span data-stu-id="28324-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="28324-130">Solo architettura Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="28324-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="28324-131">Neutro rispetto al processore e i bit per parola.</span><span class="sxs-lookup"><span data-stu-id="28324-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="28324-132">Un processore x86 a 32 bit, nativo o nell'ambiente Windows on Windows (WOW) su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="28324-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28324-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="28324-133">Child Elements</span></span>  
 <span data-ttu-id="28324-134">No.</span><span class="sxs-lookup"><span data-stu-id="28324-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28324-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="28324-135">Parent Elements</span></span>  
  
|<span data-ttu-id="28324-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="28324-136">Element</span></span>|<span data-ttu-id="28324-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28324-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="28324-138">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="28324-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="28324-139">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28324-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="28324-140">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="28324-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="28324-141">Utilizzare `<dependentAssembly>` un elemento per ogni assieme.</span><span class="sxs-lookup"><span data-stu-id="28324-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="28324-142">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="28324-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28324-143">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="28324-143">Remarks</span></span>  
 <span data-ttu-id="28324-144">Ogni \*\* \<\*\* elemento dependentAssembly>deve avere un \*\* \<\*\* elemento figlio assemblyIdentity>.</span><span class="sxs-lookup"><span data-stu-id="28324-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="28324-145">Se `processorArchitecture` l'attributo `<assemblyIdentity>` è presente, l'elemento si applica solo all'assembly con l'architettura del processore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="28324-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="28324-146">Se `processorArchitecture` l'attributo non `<assemblyIdentity>` è presente, l'elemento può essere applicato a un assembly con qualsiasi architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="28324-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="28324-147">Nell'esempio seguente viene illustrato un file di configurazione per due assembly con lo stesso nome destinato a due diverse architetture a due processori e le cui versioni non sono state mantenute sincronizzate. Quando l'applicazione viene eseguita sulla `<assemblyIdentity>` piattaforma x86 si applica il primo elemento e l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="28324-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="28324-148">Se l'applicazione viene eseguita su una piattaforma diversa da x86 o ia64, entrambi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="28324-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="28324-149">Se un file `<assemblyIdentity>` di configurazione `processorArchitecture` contiene un elemento senza attributo e non contiene `processorArchitecture` un elemento che corrisponde alla piattaforma, viene utilizzato l'elemento senza l'attributo .</span><span class="sxs-lookup"><span data-stu-id="28324-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28324-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="28324-150">Example</span></span>  
 <span data-ttu-id="28324-151">Nell'esempio seguente viene illustrato come fornire informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="28324-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28324-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28324-152">See also</span></span>

- [<span data-ttu-id="28324-153">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="28324-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="28324-154">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="28324-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="28324-155">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="28324-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
