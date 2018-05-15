---
title: '&lt;assemblyBinding&gt; elemento per &lt;runtime&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d84c134b8e2b048f39836bbc10af06039e96719e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltassemblybindinggt-element-for-ltruntimegt"></a><span data-ttu-id="7c6a2-102">&lt;assemblyBinding&gt; elemento per &lt;runtime&gt;</span><span class="sxs-lookup"><span data-stu-id="7c6a2-102">&lt;assemblyBinding&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="7c6a2-103">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="7c6a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c6a2-104">\<configuration></span></span>  
<span data-ttu-id="7c6a2-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7c6a2-105">\<runtime></span></span>  
<span data-ttu-id="7c6a2-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="7c6a2-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6a2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c6a2-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c6a2-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7c6a2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7c6a2-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c6a2-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="7c6a2-110">Attributes</span></span>  
  
|<span data-ttu-id="7c6a2-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7c6a2-111">Attribute</span></span>|<span data-ttu-id="7c6a2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c6a2-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c6a2-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="7c6a2-113">**xmlns**</span></span>|<span data-ttu-id="7c6a2-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7c6a2-115">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="7c6a2-116">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="7c6a2-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="7c6a2-117">**appliesTo**</span></span>|<span data-ttu-id="7c6a2-118">Specifica la versione di runtime a cui si applica il reindirizzamento di assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="7c6a2-119">Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="7c6a2-120">Se non si specifica l'attributo **appliesTo** l'elemento **\<assemblyBinding>** viene applicato a tutte le versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="7c6a2-121">Il **appliesTo** attributo è stato introdotto in .NET Framework versione 1.1, viene ignorata da .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="7c6a2-122">Quando si usa .NET Framework versione 1.0 vengono quindi applicati tutti gli elementi **\<assemblyBinding>** anche se viene specificato un attributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c6a2-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7c6a2-123">Child Elements</span></span>  
  
|<span data-ttu-id="7c6a2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c6a2-124">Element</span></span>|<span data-ttu-id="7c6a2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c6a2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c6a2-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="7c6a2-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="7c6a2-127">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="7c6a2-128">Utilizzare uno  **\<dependentAssembly >** tag per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="7c6a2-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="7c6a2-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="7c6a2-130">Specifica le sottodirectory in cui in Common Language Runtime viene effettuata la ricerca al momento del caricamento degli assembly. </span><span class="sxs-lookup"><span data-stu-id="7c6a2-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="7c6a2-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="7c6a2-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="7c6a2-132">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="7c6a2-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="7c6a2-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="7c6a2-134">Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c6a2-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7c6a2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7c6a2-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c6a2-136">Element</span></span>|<span data-ttu-id="7c6a2-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c6a2-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7c6a2-138">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7c6a2-139">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c6a2-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c6a2-140">Example</span></span>  
 <span data-ttu-id="7c6a2-141">L'esempio seguente illustra come reindirizzare una versione dell'assembly a un'altra versione e fornire un elemento codeBase.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="7c6a2-142">Nell'esempio seguente viene illustrato come utilizzare il **appliesTo** attributo per reindirizzare l'associazione di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6a2-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c6a2-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c6a2-143">See Also</span></span>  
 [<span data-ttu-id="7c6a2-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7c6a2-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7c6a2-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7c6a2-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7c6a2-146">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="7c6a2-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
