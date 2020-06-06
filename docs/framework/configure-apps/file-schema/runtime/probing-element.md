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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115856"
---
# <a name="probing-element"></a><span data-ttu-id="0e8e0-102">\<probing> Elemento</span><span class="sxs-lookup"><span data-stu-id="0e8e0-102">\<probing> Element</span></span>
<span data-ttu-id="0e8e0-103">Specifica le sottodirectory di base dell'applicazione per la ricerca del Common Language Runtime durante il caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="0e8e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e8e0-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e8e0-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e8e0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0e8e0-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e8e0-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e8e0-107">Attributes</span></span>  
  
|<span data-ttu-id="0e8e0-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e8e0-108">Attribute</span></span>|<span data-ttu-id="0e8e0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e8e0-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="0e8e0-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0e8e0-111">Specifica le sottodirectory della directory di base dell'applicazione che potrebbero contenere assembly.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="0e8e0-112">Delimita ogni sottodirectory con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e8e0-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e8e0-113">Child Elements</span></span>  

<span data-ttu-id="0e8e0-114">No.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e8e0-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e8e0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0e8e0-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e8e0-116">Element</span></span>|<span data-ttu-id="0e8e0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e8e0-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="0e8e0-118">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="0e8e0-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0e8e0-120">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0e8e0-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e8e0-121">Example</span></span>  
 <span data-ttu-id="0e8e0-122">Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione in cui il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="0e8e0-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e8e0-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0e8e0-123">See also</span></span>

- [<span data-ttu-id="0e8e0-124">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0e8e0-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="0e8e0-125">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0e8e0-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="0e8e0-126">Specificare la posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="0e8e0-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="0e8e0-127">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="0e8e0-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
