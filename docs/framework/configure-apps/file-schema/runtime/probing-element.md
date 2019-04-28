---
title: <probing> Elemento
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
ms.openlocfilehash: 9402c9f28c123affb7b90fc189484bb1fd43db46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704609"
---
# <a name="probing-element"></a><span data-ttu-id="57cea-102">\<probing > elemento</span><span class="sxs-lookup"><span data-stu-id="57cea-102">\<probing> Element</span></span>
<span data-ttu-id="57cea-103">Specifica le sottodirectory di base dell'applicazione per common language runtime per la ricerca quando il caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="57cea-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="57cea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="57cea-104">\<configuration></span></span>  
<span data-ttu-id="57cea-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="57cea-105">\<runtime></span></span>  
<span data-ttu-id="57cea-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="57cea-106">\<assemblyBinding></span></span>  
<span data-ttu-id="57cea-107">\<probing></span><span class="sxs-lookup"><span data-stu-id="57cea-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57cea-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57cea-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57cea-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57cea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57cea-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57cea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57cea-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="57cea-111">Attributes</span></span>  
  
|<span data-ttu-id="57cea-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="57cea-112">Attribute</span></span>|<span data-ttu-id="57cea-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57cea-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="57cea-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="57cea-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="57cea-115">Specifica le sottodirectory della directory base dell'applicazione che possono contenere assembly.</span><span class="sxs-lookup"><span data-stu-id="57cea-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="57cea-116">Consente di delimitare ogni sottodirectory con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="57cea-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57cea-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57cea-117">Child Elements</span></span>  
 <span data-ttu-id="57cea-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="57cea-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57cea-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57cea-119">Parent Elements</span></span>  
  
|<span data-ttu-id="57cea-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="57cea-120">Element</span></span>|<span data-ttu-id="57cea-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57cea-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="57cea-122">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="57cea-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="57cea-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57cea-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="57cea-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="57cea-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57cea-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="57cea-125">Example</span></span>  
 <span data-ttu-id="57cea-126">Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione che il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="57cea-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57cea-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57cea-127">See also</span></span>

- [<span data-ttu-id="57cea-128">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="57cea-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="57cea-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="57cea-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="57cea-130">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="57cea-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="57cea-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="57cea-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
