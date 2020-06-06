---
title: Elemento <assemblyBinding> per <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154322"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="afe0f-102">Elemento \<assemblyBinding> per \<runtime></span><span class="sxs-lookup"><span data-stu-id="afe0f-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="afe0f-103">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="afe0f-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="afe0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afe0f-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afe0f-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="afe0f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="afe0f-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="afe0f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afe0f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="afe0f-107">Attributes</span></span>  
  
|<span data-ttu-id="afe0f-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="afe0f-108">Attribute</span></span>|<span data-ttu-id="afe0f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afe0f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afe0f-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="afe0f-110">**xmlns**</span></span>|<span data-ttu-id="afe0f-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="afe0f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="afe0f-112">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="afe0f-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="afe0f-113">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="afe0f-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="afe0f-114">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="afe0f-114">**appliesTo**</span></span>|<span data-ttu-id="afe0f-115">Specifica la versione di runtime a cui si applica il reindirizzamento di assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afe0f-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="afe0f-116">Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="afe0f-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="afe0f-117">Se non è specificato alcun attributo **appliesTo** , l' **\<assemblyBinding>** elemento si applica a tutte le versioni del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afe0f-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="afe0f-118">L'attributo **appliesTo** è stato introdotto nella versione .NET Framework 1,1; viene ignorato dalla versione di .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="afe0f-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="afe0f-119">Ciò significa che tutti **\<assemblyBinding>** gli elementi vengono applicati quando si usa la versione di .NET Framework 1,0, anche se viene specificato un attributo **appliesTo** .</span><span class="sxs-lookup"><span data-stu-id="afe0f-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afe0f-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="afe0f-120">Child Elements</span></span>  
  
|<span data-ttu-id="afe0f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="afe0f-121">Element</span></span>|<span data-ttu-id="afe0f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afe0f-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="afe0f-123">Incapsula i criteri di binding e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="afe0f-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="afe0f-124">Usare un **\<dependentAssembly>** tag per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="afe0f-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="afe0f-125">Specifica le sottodirectory in cui in Common Language Runtime viene effettuata la ricerca al momento del caricamento degli assembly. </span><span class="sxs-lookup"><span data-stu-id="afe0f-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="afe0f-126">Specifica se il runtime applica i criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="afe0f-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="afe0f-127">Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.</span><span class="sxs-lookup"><span data-stu-id="afe0f-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afe0f-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="afe0f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="afe0f-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="afe0f-129">Element</span></span>|<span data-ttu-id="afe0f-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afe0f-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="afe0f-131">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afe0f-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="afe0f-132">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="afe0f-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="afe0f-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="afe0f-133">Example</span></span>  
 <span data-ttu-id="afe0f-134">L'esempio seguente illustra come reindirizzare una versione dell'assembly a un'altra versione e fornire un elemento codeBase.</span><span class="sxs-lookup"><span data-stu-id="afe0f-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="afe0f-135">Nell'esempio seguente viene illustrato come utilizzare l'attributo **appliesTo** per reindirizzare l'associazione di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afe0f-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afe0f-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="afe0f-136">See also</span></span>

- [<span data-ttu-id="afe0f-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="afe0f-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="afe0f-138">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="afe0f-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="afe0f-139">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="afe0f-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
