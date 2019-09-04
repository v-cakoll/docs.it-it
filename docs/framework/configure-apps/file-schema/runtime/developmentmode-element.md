---
title: <developmentMode> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0253c3ced52b575097fe5d18abb8ce188c0164fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252689"
---
# <a name="developmentmode-element"></a><span data-ttu-id="1e902-102">\<Elemento > developmentMode</span><span class="sxs-lookup"><span data-stu-id="1e902-102">\<developmentMode> Element</span></span>
<span data-ttu-id="1e902-103">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="1e902-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e902-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e902-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e902-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="1e902-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode>**</span><span class="sxs-lookup"><span data-stu-id="1e902-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e902-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e902-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e902-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e902-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1e902-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e902-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e902-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1e902-110">Attributes</span></span>  
  
|<span data-ttu-id="1e902-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1e902-111">Attribute</span></span>|<span data-ttu-id="1e902-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e902-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e902-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="1e902-113">**developerInstallation**</span></span>|<span data-ttu-id="1e902-114">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="1e902-115">Attributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="1e902-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="1e902-116">Valore</span><span class="sxs-lookup"><span data-stu-id="1e902-116">Value</span></span>|<span data-ttu-id="1e902-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e902-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1e902-118">**true**</span><span class="sxs-lookup"><span data-stu-id="1e902-118">**true**</span></span>|<span data-ttu-id="1e902-119">Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="1e902-120">**false**</span><span class="sxs-lookup"><span data-stu-id="1e902-120">**false**</span></span>|<span data-ttu-id="1e902-121">Non cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="1e902-122">Questa è l'impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1e902-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e902-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e902-123">Child Elements</span></span>  
 <span data-ttu-id="1e902-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1e902-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e902-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e902-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1e902-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e902-126">Element</span></span>|<span data-ttu-id="1e902-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e902-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1e902-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e902-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1e902-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1e902-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e902-130">Note</span><span class="sxs-lookup"><span data-stu-id="1e902-130">Remarks</span></span>  
 <span data-ttu-id="1e902-131">Usare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="1e902-131">Use this setting only at development time.</span></span> <span data-ttu-id="1e902-132">Il runtime non controlla le versioni in assembly con nome sicuro presenti in DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="1e902-133">Usa semplicemente il primo assembly trovato.</span><span class="sxs-lookup"><span data-stu-id="1e902-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e902-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e902-134">Example</span></span>  
 <span data-ttu-id="1e902-135">Nell'esempio seguente viene illustrato come fare in modo che il runtime cerchi gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1e902-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e902-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e902-136">See also</span></span>

- [<span data-ttu-id="1e902-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1e902-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1e902-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1e902-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1e902-139">Procedura: Individuare gli assembly usando DEVPATH</span><span class="sxs-lookup"><span data-stu-id="1e902-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
