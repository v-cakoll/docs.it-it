---
title: '&lt;individuazione tramite probe&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b9be3050da21c0a99931ca70cf990b0b8bf1fe
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612303"
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="5a74e-102">&lt;individuazione tramite probe&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="5a74e-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="5a74e-103">Specifica le sottodirectory di base dell'applicazione per common language runtime per la ricerca quando il caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="5a74e-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="5a74e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5a74e-104">\<configuration></span></span>  
<span data-ttu-id="5a74e-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="5a74e-105">\<runtime></span></span>  
<span data-ttu-id="5a74e-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="5a74e-106">\<assemblyBinding></span></span>  
<span data-ttu-id="5a74e-107">\<probing ></span><span class="sxs-lookup"><span data-stu-id="5a74e-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a74e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a74e-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a74e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5a74e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5a74e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5a74e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a74e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="5a74e-111">Attributes</span></span>  
  
|<span data-ttu-id="5a74e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="5a74e-112">Attribute</span></span>|<span data-ttu-id="5a74e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a74e-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="5a74e-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5a74e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5a74e-115">Specifica le sottodirectory della directory base dell'applicazione che possono contenere assembly.</span><span class="sxs-lookup"><span data-stu-id="5a74e-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="5a74e-116">Consente di delimitare ogni sottodirectory con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="5a74e-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a74e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5a74e-117">Child Elements</span></span>  
 <span data-ttu-id="5a74e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5a74e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a74e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5a74e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5a74e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a74e-120">Element</span></span>|<span data-ttu-id="5a74e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a74e-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="5a74e-122">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="5a74e-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="5a74e-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5a74e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5a74e-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5a74e-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a74e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a74e-125">Example</span></span>  
 <span data-ttu-id="5a74e-126">Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione che il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="5a74e-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a74e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a74e-127">See Also</span></span>  
- [<span data-ttu-id="5a74e-128">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="5a74e-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="5a74e-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="5a74e-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="5a74e-130">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="5a74e-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
- [<span data-ttu-id="5a74e-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="5a74e-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
