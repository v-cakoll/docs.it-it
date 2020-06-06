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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154309"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="b7abb-102">Elemento \<assemblyIdentity> per \<runtime></span><span class="sxs-lookup"><span data-stu-id="b7abb-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="b7abb-103">Contiene informazioni di identificazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-103">Contains identifying information about the assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a><span data-ttu-id="b7abb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7abb-104">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7abb-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b7abb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b7abb-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b7abb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7abb-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b7abb-107">Attributes</span></span>  
  
|<span data-ttu-id="b7abb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="b7abb-108">Attribute</span></span>|<span data-ttu-id="b7abb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7abb-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b7abb-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7abb-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7abb-111">Nome dell'assembly</span><span class="sxs-lookup"><span data-stu-id="b7abb-111">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="b7abb-112">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b7abb-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b7abb-113">Stringa che specifica la lingua e il paese/area geografica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-113">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="b7abb-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b7abb-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b7abb-115">Valore esadecimale che specifica il nome sicuro dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-115">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="b7abb-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b7abb-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b7abb-117">Uno dei valori "x86", "amd64", "MSIL" o "ia64", che specifica l'architettura del processore per un assembly che contiene codice specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="b7abb-117">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="b7abb-118">I valori non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b7abb-118">The values are not case-sensitive.</span></span> <span data-ttu-id="b7abb-119">Se all'attributo viene assegnato qualsiasi altro valore, l'intero `<assemblyIdentity>` elemento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="b7abb-119">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="b7abb-120">Vedere <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="b7abb-120">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="b7abb-121">Attributo processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="b7abb-121">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="b7abb-122">Valore</span><span class="sxs-lookup"><span data-stu-id="b7abb-122">Value</span></span>|<span data-ttu-id="b7abb-123">Description</span><span class="sxs-lookup"><span data-stu-id="b7abb-123">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="b7abb-124">Solo architettura AMD x86-64.</span><span class="sxs-lookup"><span data-stu-id="b7abb-124">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="b7abb-125">Solo architettura Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="b7abb-125">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="b7abb-126">Neutro rispetto al processore e i bit per parola.</span><span class="sxs-lookup"><span data-stu-id="b7abb-126">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="b7abb-127">Un processore x86 a 32 bit, nativo o nell'ambiente Windows in Windows (WOW) su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b7abb-127">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7abb-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b7abb-128">Child Elements</span></span>  
 <span data-ttu-id="b7abb-129">No.</span><span class="sxs-lookup"><span data-stu-id="b7abb-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7abb-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b7abb-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b7abb-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7abb-131">Element</span></span>|<span data-ttu-id="b7abb-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7abb-132">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="b7abb-133">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="b7abb-133">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="b7abb-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7abb-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="b7abb-135">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-135">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="b7abb-136">Usare un `<dependentAssembly>` elemento per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-136">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="b7abb-137">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b7abb-137">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7abb-138">Commenti</span><span class="sxs-lookup"><span data-stu-id="b7abb-138">Remarks</span></span>  
 <span data-ttu-id="b7abb-139">Ogni **\<dependentAssembly>** elemento deve avere un **\<assemblyIdentity>** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="b7abb-139">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="b7abb-140">Se l' `processorArchitecture` attributo è presente, l' `<assemblyIdentity>` elemento si applica solo all'assembly con l'architettura del processore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b7abb-140">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="b7abb-141">Se l' `processorArchitecture` attributo non è presente, l' `<assemblyIdentity>` elemento può essere applicato a un assembly con qualsiasi architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="b7abb-141">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="b7abb-142">Nell'esempio seguente viene illustrato un file di configurazione per due assembly con lo stesso nome che hanno come destinazione due diverse architetture del processore e le cui versioni non sono state mantenute in sincronizzazione. Quando l'applicazione viene eseguita sulla piattaforma x86 `<assemblyIdentity>` , viene applicato il primo elemento e l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="b7abb-142">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="b7abb-143">Se l'applicazione viene eseguita su una piattaforma diversa da x86 o ia64, entrambi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="b7abb-143">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="b7abb-144">Se un file di configurazione contiene un `<assemblyIdentity>` elemento senza `processorArchitecture` attributo e non contiene un elemento che corrisponde alla piattaforma, viene utilizzato l'elemento senza l' `processorArchitecture` attributo.</span><span class="sxs-lookup"><span data-stu-id="b7abb-144">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7abb-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7abb-145">Example</span></span>  
 <span data-ttu-id="b7abb-146">Nell'esempio seguente viene illustrato come fornire informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="b7abb-146">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7abb-147">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b7abb-147">See also</span></span>

- [<span data-ttu-id="b7abb-148">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b7abb-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b7abb-149">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b7abb-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b7abb-150">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="b7abb-150">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
