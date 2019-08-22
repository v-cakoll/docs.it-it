---
title: <appDomainManagerType> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b535ba67ab05dabd7e0a23e79692bbf69e25b55
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663917"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="3e8d0-102">\<Elemento > appDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="3e8d0-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="3e8d0-103">Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="3e8d0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e8d0-104">\<configuration></span></span>  
<span data-ttu-id="3e8d0-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="3e8d0-105">\<runtime></span></span>  
<span data-ttu-id="3e8d0-106">\<appDomainManagerType></span><span class="sxs-lookup"><span data-stu-id="3e8d0-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8d0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e8d0-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e8d0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3e8d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3e8d0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e8d0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3e8d0-110">Attributes</span></span>  
  
|<span data-ttu-id="3e8d0-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3e8d0-111">Attribute</span></span>|<span data-ttu-id="3e8d0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e8d0-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="3e8d0-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-113">Required attribute.</span></span> <span data-ttu-id="3e8d0-114">Specifica il nome del tipo, incluso lo spazio dei nomi, che funge da gestore del dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e8d0-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3e8d0-115">Child Elements</span></span>  
 <span data-ttu-id="3e8d0-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e8d0-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3e8d0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3e8d0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e8d0-118">Element</span></span>|<span data-ttu-id="3e8d0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e8d0-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3e8d0-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3e8d0-121">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e8d0-122">Note</span><span class="sxs-lookup"><span data-stu-id="3e8d0-122">Remarks</span></span>  
 <span data-ttu-id="3e8d0-123">Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l' [ \<elemento > AppDomainManagerAssembly](appdomainmanagerassembly-element.md) .</span><span class="sxs-lookup"><span data-stu-id="3e8d0-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="3e8d0-124">Se uno di questi elementi non è specificato, l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="3e8d0-125">Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata un'eccezione se il tipo specificato non esiste nell'assembly specificato [ \<dall'elemento > AppDomainManagerAssembly](appdomainmanagerassembly-element.md) e il processo non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="3e8d0-126">Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="3e8d0-127">Usare le <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> proprietà <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> e per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="3e8d0-128">Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="3e8d0-129">Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, <xref:System.TypeLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="3e8d0-130">Il formato del tipo e dello spazio dei nomi è identico a quello usato per <xref:System.Type.FullName%2A?displayProperty=nameWithType> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="3e8d0-131">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e8d0-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e8d0-132">Example</span></span>  
 <span data-ttu-id="3e8d0-133">Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo `MyMgr` è il tipo `AdMgrExample` nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3e8d0-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e8d0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e8d0-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3e8d0-135">\<Elemento > appDomainManagerAssembly</span><span class="sxs-lookup"><span data-stu-id="3e8d0-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="3e8d0-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="3e8d0-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3e8d0-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3e8d0-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3e8d0-138">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="3e8d0-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
