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
ms.openlocfilehash: fdf840035150f08c894c984213af9a0abe6e95af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704765"
---
# <a name="developmentmode-element"></a><span data-ttu-id="02967-102">\<developmentMode > elemento</span><span class="sxs-lookup"><span data-stu-id="02967-102">\<developmentMode> Element</span></span>
<span data-ttu-id="02967-103">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="02967-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="02967-104">\<configuration></span></span>  
<span data-ttu-id="02967-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="02967-105">\<runtime></span></span>  
<span data-ttu-id="02967-106">\<developmentMode ></span><span class="sxs-lookup"><span data-stu-id="02967-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02967-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02967-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02967-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02967-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02967-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02967-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02967-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="02967-110">Attributes</span></span>  
  
|<span data-ttu-id="02967-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="02967-111">Attribute</span></span>|<span data-ttu-id="02967-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02967-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02967-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="02967-113">**developerInstallation**</span></span>|<span data-ttu-id="02967-114">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="02967-115">Attributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="02967-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="02967-116">Value</span><span class="sxs-lookup"><span data-stu-id="02967-116">Value</span></span>|<span data-ttu-id="02967-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02967-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02967-118">**true**</span><span class="sxs-lookup"><span data-stu-id="02967-118">**true**</span></span>|<span data-ttu-id="02967-119">Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="02967-120">**false**</span><span class="sxs-lookup"><span data-stu-id="02967-120">**false**</span></span>|<span data-ttu-id="02967-121">Non esegue la ricerca per gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="02967-122">Questo è il valore predefinito</span><span class="sxs-lookup"><span data-stu-id="02967-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02967-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02967-123">Child Elements</span></span>  
 <span data-ttu-id="02967-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="02967-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02967-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02967-125">Parent Elements</span></span>  
  
|<span data-ttu-id="02967-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="02967-126">Element</span></span>|<span data-ttu-id="02967-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02967-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02967-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02967-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02967-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="02967-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02967-130">Note</span><span class="sxs-lookup"><span data-stu-id="02967-130">Remarks</span></span>  
 <span data-ttu-id="02967-131">Usare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="02967-131">Use this setting only at development time.</span></span> <span data-ttu-id="02967-132">Il runtime non verifica se le versioni di assembly con nome sicuro trovato nel DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="02967-133">Utilizza semplicemente il primo assembly individuato.</span><span class="sxs-lookup"><span data-stu-id="02967-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02967-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="02967-134">Example</span></span>  
 <span data-ttu-id="02967-135">Nell'esempio seguente viene illustrato come parte del runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="02967-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02967-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02967-136">See also</span></span>

- [<span data-ttu-id="02967-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="02967-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="02967-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="02967-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="02967-139">Procedura: Individuare assembly mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="02967-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
