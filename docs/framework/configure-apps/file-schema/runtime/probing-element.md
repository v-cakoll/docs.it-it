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
ms.openlocfilehash: e9e48ea97e1b70fef7fcc78a113e18c5fec23b7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115856"
---
# <a name="probing-element"></a><span data-ttu-id="f7db4-102">\<elemento > Probe</span><span class="sxs-lookup"><span data-stu-id="f7db4-102">\<probing> Element</span></span>
<span data-ttu-id="f7db4-103">Specifica le sottodirectory di base dell'applicazione per la ricerca del Common Language Runtime durante il caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="f7db4-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="f7db4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7db4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7db4-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="f7db4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f7db4-106">&nbsp; &nbsp;[ \**&nbsp; &nbsp; \<assemblyBinding > \** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="f7db4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\</span></span>
<span data-ttu-id="f7db4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Probe** ></span><span class="sxs-lookup"><span data-stu-id="f7db4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7db4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7db4-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7db4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7db4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7db4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7db4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7db4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7db4-111">Attributes</span></span>  
  
|<span data-ttu-id="f7db4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f7db4-112">Attribute</span></span>|<span data-ttu-id="f7db4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7db4-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="f7db4-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7db4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7db4-115">Specifica le sottodirectory della directory di base dell'applicazione che potrebbero contenere assembly.</span><span class="sxs-lookup"><span data-stu-id="f7db4-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="f7db4-116">Delimita ogni sottodirectory con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="f7db4-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7db4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7db4-117">Child Elements</span></span>  

<span data-ttu-id="f7db4-118">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="f7db4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7db4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7db4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f7db4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7db4-120">Element</span></span>|<span data-ttu-id="f7db4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7db4-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f7db4-122">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="f7db4-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f7db4-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7db4-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f7db4-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f7db4-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f7db4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7db4-125">Example</span></span>  
 <span data-ttu-id="f7db4-126">Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione in cui il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="f7db4-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7db4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7db4-127">See also</span></span>

- [<span data-ttu-id="f7db4-128">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f7db4-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="f7db4-129">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7db4-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="f7db4-130">Specificare la posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="f7db4-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="f7db4-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="f7db4-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
