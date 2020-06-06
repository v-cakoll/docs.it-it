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
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117623"
---
# <a name="developmentmode-element"></a><span data-ttu-id="f648c-102">\<developmentMode> Elemento</span><span class="sxs-lookup"><span data-stu-id="f648c-102">\<developmentMode> Element</span></span>
<span data-ttu-id="f648c-103">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="f648c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f648c-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f648c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f648c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f648c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f648c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f648c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f648c-107">Attributes</span></span>  
  
|<span data-ttu-id="f648c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f648c-108">Attribute</span></span>|<span data-ttu-id="f648c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f648c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f648c-110">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="f648c-110">**developerInstallation**</span></span>|<span data-ttu-id="f648c-111">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="f648c-112">Attributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="f648c-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="f648c-113">Valore</span><span class="sxs-lookup"><span data-stu-id="f648c-113">Value</span></span>|<span data-ttu-id="f648c-114">Description</span><span class="sxs-lookup"><span data-stu-id="f648c-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f648c-115">**true**</span><span class="sxs-lookup"><span data-stu-id="f648c-115">**true**</span></span>|<span data-ttu-id="f648c-116">Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="f648c-117">**false**</span><span class="sxs-lookup"><span data-stu-id="f648c-117">**false**</span></span>|<span data-ttu-id="f648c-118">Non cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="f648c-119">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f648c-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f648c-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f648c-120">Child Elements</span></span>  
 <span data-ttu-id="f648c-121">No.</span><span class="sxs-lookup"><span data-stu-id="f648c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f648c-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f648c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f648c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f648c-123">Element</span></span>|<span data-ttu-id="f648c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f648c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f648c-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f648c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f648c-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f648c-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f648c-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="f648c-127">Remarks</span></span>  
 <span data-ttu-id="f648c-128">Usare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="f648c-128">Use this setting only at development time.</span></span> <span data-ttu-id="f648c-129">Il runtime non controlla le versioni in assembly con nome sicuro presenti in DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="f648c-130">Usa semplicemente il primo assembly trovato.</span><span class="sxs-lookup"><span data-stu-id="f648c-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f648c-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="f648c-131">Example</span></span>  
 <span data-ttu-id="f648c-132">Nell'esempio seguente viene illustrato come fare in modo che il runtime cerchi gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="f648c-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f648c-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f648c-133">See also</span></span>

- [<span data-ttu-id="f648c-134">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f648c-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f648c-135">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f648c-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f648c-136">Procedura: Individuare assembly usando DEVPATH</span><span class="sxs-lookup"><span data-stu-id="f648c-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
