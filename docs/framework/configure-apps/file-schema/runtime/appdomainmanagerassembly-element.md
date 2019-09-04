---
title: <appDomainManagerAssembly> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 083e3ba21dcd196eacfe3d9fd649c211da9dc125
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252843"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="e1ca9-102">\<Elemento > appDomainManagerAssembly</span><span class="sxs-lookup"><span data-stu-id="e1ca9-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="e1ca9-103">Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="e1ca9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1ca9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1ca9-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1ca9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e1ca9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerAssembly>**</span><span class="sxs-lookup"><span data-stu-id="e1ca9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ca9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1ca9-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1ca9-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e1ca9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1ca9-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1ca9-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e1ca9-110">Attributes</span></span>  
  
|<span data-ttu-id="e1ca9-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e1ca9-111">Attribute</span></span>|<span data-ttu-id="e1ca9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1ca9-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="e1ca9-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-113">Required attribute.</span></span> <span data-ttu-id="e1ca9-114">Specifica il nome visualizzato dell'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1ca9-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e1ca9-115">Child Elements</span></span>  
 <span data-ttu-id="e1ca9-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1ca9-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e1ca9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e1ca9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1ca9-118">Element</span></span>|<span data-ttu-id="e1ca9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1ca9-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1ca9-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e1ca9-121">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1ca9-122">Note</span><span class="sxs-lookup"><span data-stu-id="e1ca9-122">Remarks</span></span>  
 <span data-ttu-id="e1ca9-123">Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l' [ \<elemento > AppDomainManagerType](appdomainmanagertype-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e1ca9-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="e1ca9-124">Se uno di questi elementi non è specificato, l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="e1ca9-125">Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata un'eccezione se l'assembly specificato non esiste o se l'assembly non contiene il tipo specificato [ \<dall'elemento > AppDomainManagerType](appdomainmanagertype-element.md) e il processo non riesce iniziare.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="e1ca9-126">Se l'assembly viene trovato ma le informazioni sulla versione non corrispondono, viene <xref:System.IO.FileLoadException> generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e1ca9-127">Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="e1ca9-128">Usare le <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> proprietà <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> e per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="e1ca9-129">Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="e1ca9-130">Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, <xref:System.TypeLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e1ca9-131">Per il formato del nome visualizzato dell'assembly, vedere la <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e1ca9-132">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1ca9-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1ca9-133">Example</span></span>  
 <span data-ttu-id="e1ca9-134">Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo `MyMgr` è il tipo `AdMgrExample` nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e1ca9-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1ca9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1ca9-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e1ca9-136">\<Elemento > appDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="e1ca9-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="e1ca9-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="e1ca9-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1ca9-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e1ca9-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1ca9-139">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="e1ca9-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
