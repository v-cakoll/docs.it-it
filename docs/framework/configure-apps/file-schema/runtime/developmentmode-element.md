---
title: '&lt;developmentMode&gt; elemento'
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
ms.openlocfilehash: 71b4eb1dfb50774cea2f7a50d5e5350b0338f41e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltdevelopmentmodegt-element"></a><span data-ttu-id="32302-102">&lt;developmentMode&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="32302-102">&lt;developmentMode&gt; Element</span></span>
<span data-ttu-id="32302-103">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="32302-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="32302-104">\<configuration></span></span>  
<span data-ttu-id="32302-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="32302-105">\<runtime></span></span>  
<span data-ttu-id="32302-106">\<developmentMode ></span><span class="sxs-lookup"><span data-stu-id="32302-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32302-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32302-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32302-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="32302-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32302-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="32302-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32302-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="32302-110">Attributes</span></span>  
  
|<span data-ttu-id="32302-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="32302-111">Attribute</span></span>|<span data-ttu-id="32302-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32302-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32302-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="32302-113">**developerInstallation**</span></span>|<span data-ttu-id="32302-114">Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="32302-115">Attributo developerInstallation</span><span class="sxs-lookup"><span data-stu-id="32302-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="32302-116">Valore</span><span class="sxs-lookup"><span data-stu-id="32302-116">Value</span></span>|<span data-ttu-id="32302-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32302-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32302-118">**true**</span><span class="sxs-lookup"><span data-stu-id="32302-118">**true**</span></span>|<span data-ttu-id="32302-119">Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="32302-120">**false**</span><span class="sxs-lookup"><span data-stu-id="32302-120">**false**</span></span>|<span data-ttu-id="32302-121">Non esegue la ricerca per gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="32302-122">Questa è l'impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="32302-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32302-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="32302-123">Child Elements</span></span>  
 <span data-ttu-id="32302-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="32302-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32302-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="32302-125">Parent Elements</span></span>  
  
|<span data-ttu-id="32302-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="32302-126">Element</span></span>|<span data-ttu-id="32302-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32302-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="32302-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="32302-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="32302-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="32302-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32302-130">Note</span><span class="sxs-lookup"><span data-stu-id="32302-130">Remarks</span></span>  
 <span data-ttu-id="32302-131">Utilizzare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="32302-131">Use this setting only at development time.</span></span> <span data-ttu-id="32302-132">Il runtime non controllate le versioni degli assembly con nome sicuro, vedere il DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="32302-133">Usa semplicemente il primo assembly individuato.</span><span class="sxs-lookup"><span data-stu-id="32302-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32302-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="32302-134">Example</span></span>  
 <span data-ttu-id="32302-135">Nell'esempio seguente viene illustrato come impostare il runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="32302-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32302-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32302-136">See Also</span></span>  
 [<span data-ttu-id="32302-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="32302-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="32302-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="32302-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="32302-139">Procedura: individuare assembly mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="32302-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
