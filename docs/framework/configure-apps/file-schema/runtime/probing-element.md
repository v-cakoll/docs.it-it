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
ms.openlocfilehash: 05634cb319ac69bd76e16e592ba59490b30c9c9d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252394"
---
# <a name="probing-element"></a><span data-ttu-id="6bfd9-102">\<Elemento > Probe</span><span class="sxs-lookup"><span data-stu-id="6bfd9-102">\<probing> Element</span></span>
<span data-ttu-id="6bfd9-103">Specifica le sottodirectory di base dell'applicazione per la ricerca del Common Language Runtime durante il caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="6bfd9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bfd9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bfd9-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bfd9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6bfd9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di associazione**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="6bfd9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="6bfd9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<probing>**</span><span class="sxs-lookup"><span data-stu-id="6bfd9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bfd9-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bfd9-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bfd9-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6bfd9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6bfd9-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bfd9-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6bfd9-111">Attributes</span></span>  
  
|<span data-ttu-id="6bfd9-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="6bfd9-112">Attribute</span></span>|<span data-ttu-id="6bfd9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bfd9-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="6bfd9-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6bfd9-115">Specifica le sottodirectory della directory di base dell'applicazione che potrebbero contenere assembly.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="6bfd9-116">Delimita ogni sottodirectory con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bfd9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6bfd9-117">Child Elements</span></span>  

<span data-ttu-id="6bfd9-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bfd9-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6bfd9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6bfd9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bfd9-120">Element</span></span>|<span data-ttu-id="6bfd9-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6bfd9-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="6bfd9-122">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="6bfd9-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6bfd9-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6bfd9-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bfd9-125">Example</span></span>  
 <span data-ttu-id="6bfd9-126">Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione in cui il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="6bfd9-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bfd9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bfd9-127">See also</span></span>

- [<span data-ttu-id="6bfd9-128">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6bfd9-128">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6bfd9-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6bfd9-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6bfd9-130">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="6bfd9-130">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="6bfd9-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="6bfd9-131">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
