---
title: '&lt;appDomainManagerAssembly&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23c0edd99d09417c8e657045407a02a07338d7b2
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610190"
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="ad81d-102">&lt;appDomainManagerAssembly&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="ad81d-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="ad81d-103">Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="ad81d-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="ad81d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ad81d-104">\<configuration></span></span>  
<span data-ttu-id="ad81d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ad81d-105">\<runtime></span></span>  
<span data-ttu-id="ad81d-106">\<appDomainManagerAssembly ></span><span class="sxs-lookup"><span data-stu-id="ad81d-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad81d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad81d-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad81d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad81d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ad81d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad81d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad81d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad81d-110">Attributes</span></span>  
  
|<span data-ttu-id="ad81d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ad81d-111">Attribute</span></span>|<span data-ttu-id="ad81d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad81d-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="ad81d-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad81d-113">Required attribute.</span></span> <span data-ttu-id="ad81d-114">Specifica il nome visualizzato dell'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="ad81d-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad81d-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad81d-115">Child Elements</span></span>  
 <span data-ttu-id="ad81d-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ad81d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad81d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad81d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ad81d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad81d-118">Element</span></span>|<span data-ttu-id="ad81d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad81d-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad81d-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad81d-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ad81d-121">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ad81d-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad81d-122">Note</span><span class="sxs-lookup"><span data-stu-id="ad81d-122">Remarks</span></span>  
 <span data-ttu-id="ad81d-123">Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento e il [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ad81d-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="ad81d-124">Se uno di questi elementi non è specificato, l'altra viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="ad81d-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="ad81d-125">Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata se l'assembly specificato non esiste o se l'assembly non contiene il tipo specificato per il [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento; e il processo non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="ad81d-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="ad81d-126">Se l'assembly viene trovato, ma le informazioni sulla versione non corrisponde, un <xref:System.IO.FileLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ad81d-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ad81d-127">Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, gli altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestione del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad81d-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="ad81d-128">Usare la <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> e <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> le proprietà per specificare un tipo di gestione dominio applicazione diverso per un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad81d-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="ad81d-129">Specifica il tipo di gestione del dominio dell'applicazione richiede che l'applicazione disponga di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="ad81d-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="ad81d-130">(Ad esempio, un'applicazione in esecuzione sul desktop sia totalmente attendibile.) Se l'applicazione non ha attendibilità totale, una <xref:System.TypeLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ad81d-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ad81d-131">Per il formato del nome visualizzato dell'assembly, vedere il <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad81d-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ad81d-132">Questo elemento di configurazione è disponibile solo nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ad81d-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad81d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad81d-133">Example</span></span>  
 <span data-ttu-id="ad81d-134">Nell'esempio seguente viene illustrato come specificare che il gestore del dominio dell'applicazione per il dominio applicazione predefinito di un processo è il `MyMgr` digitare il `AdMgrExample` assembly.</span><span class="sxs-lookup"><span data-stu-id="ad81d-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad81d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad81d-135">See Also</span></span>  
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="ad81d-136">\<appDomainManagerType > elemento</span><span class="sxs-lookup"><span data-stu-id="ad81d-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
- [<span data-ttu-id="ad81d-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ad81d-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="ad81d-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ad81d-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="ad81d-139">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="ad81d-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
