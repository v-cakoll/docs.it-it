---
title: <appDomainManagerAssembly> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154427"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="ba0f4-102">\<appDomainManagerAssembly> Elemento</span><span class="sxs-lookup"><span data-stu-id="ba0f4-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="ba0f4-103">Specifica l'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="ba0f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba0f4-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba0f4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ba0f4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ba0f4-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba0f4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ba0f4-107">Attributes</span></span>  
  
|<span data-ttu-id="ba0f4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ba0f4-108">Attribute</span></span>|<span data-ttu-id="ba0f4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba0f4-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="ba0f4-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-110">Required attribute.</span></span> <span data-ttu-id="ba0f4-111">Specifica il nome visualizzato dell'assembly che fornisce il gestore di dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-111">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba0f4-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ba0f4-112">Child Elements</span></span>  
 <span data-ttu-id="ba0f4-113">No.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba0f4-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ba0f4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ba0f4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba0f4-115">Element</span></span>|<span data-ttu-id="ba0f4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba0f4-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba0f4-117">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ba0f4-118">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba0f4-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="ba0f4-119">Remarks</span></span>  
 <span data-ttu-id="ba0f4-120">Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l' [\<appDomainManagerType>](appdomainmanagertype-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="ba0f4-121">Se uno di questi elementi non è specificato, l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="ba0f4-122">Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata un'eccezione se l'assembly specificato non esiste o se l'assembly non contiene il tipo specificato dall' [\<appDomainManagerType>](appdomainmanagertype-element.md) elemento e il processo non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="ba0f4-123">Se l'assembly viene trovato ma le informazioni sulla versione non corrispondono, <xref:System.IO.FileLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-123">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ba0f4-124">Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="ba0f4-125">Usare le <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> proprietà e per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="ba0f4-126">Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="ba0f4-127">Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, <xref:System.TypeLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ba0f4-128">Per il formato del nome visualizzato dell'assembly, vedere la <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-128">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ba0f4-129">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba0f4-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba0f4-130">Example</span></span>  
 <span data-ttu-id="ba0f4-131">Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo è il `MyMgr` tipo nell' `AdMgrExample` assembly.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba0f4-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ba0f4-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ba0f4-133">\<appDomainManagerType>Elemento</span><span class="sxs-lookup"><span data-stu-id="ba0f4-133">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="ba0f4-134">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ba0f4-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ba0f4-135">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ba0f4-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ba0f4-136">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="ba0f4-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
