---
title: <appDomainManagerType> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154426"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="9f36b-102">\<appDomainManagerType> Elemento</span><span class="sxs-lookup"><span data-stu-id="9f36b-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="9f36b-103">Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="9f36b-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="9f36b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f36b-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f36b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9f36b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9f36b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9f36b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f36b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="9f36b-107">Attributes</span></span>  
  
|<span data-ttu-id="9f36b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="9f36b-108">Attribute</span></span>|<span data-ttu-id="9f36b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f36b-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="9f36b-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9f36b-110">Required attribute.</span></span> <span data-ttu-id="9f36b-111">Specifica il nome del tipo, incluso lo spazio dei nomi, che funge da gestore del dominio dell'applicazione per il dominio applicazione predefinito nel processo.</span><span class="sxs-lookup"><span data-stu-id="9f36b-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f36b-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9f36b-112">Child Elements</span></span>  
 <span data-ttu-id="9f36b-113">No.</span><span class="sxs-lookup"><span data-stu-id="9f36b-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f36b-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9f36b-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9f36b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f36b-115">Element</span></span>|<span data-ttu-id="9f36b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f36b-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9f36b-117">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f36b-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9f36b-118">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9f36b-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f36b-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="9f36b-119">Remarks</span></span>  
 <span data-ttu-id="9f36b-120">Per specificare il tipo del gestore di dominio dell'applicazione, è necessario specificare sia questo elemento sia l' [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9f36b-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="9f36b-121">Se uno di questi elementi non è specificato, l'altro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="9f36b-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="9f36b-122">Quando viene caricato il dominio applicazione predefinito, <xref:System.TypeLoadException> viene generata un'eccezione se il tipo specificato non esiste nell'assembly specificato dall' [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) elemento e il processo non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="9f36b-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="9f36b-123">Quando si specifica il tipo di gestore di dominio dell'applicazione per il dominio applicazione predefinito, altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestore di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f36b-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="9f36b-124">Usare le <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> proprietà e per specificare un tipo di gestore di dominio dell'applicazione diverso per un nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f36b-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="9f36b-125">Per specificare il tipo di gestore di dominio applicazione è necessario che l'applicazione disponga di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="9f36b-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="9f36b-126">Ad esempio, un'applicazione in esecuzione sul desktop ha attendibilità totale. Se l'applicazione non dispone di attendibilità totale, <xref:System.TypeLoadException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9f36b-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="9f36b-127">Il formato del tipo e dello spazio dei nomi è identico a quello usato per la <xref:System.Type.FullName%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f36b-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="9f36b-128">Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="9f36b-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f36b-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f36b-129">Example</span></span>  
 <span data-ttu-id="9f36b-130">Nell'esempio seguente viene illustrato come specificare che il gestore di dominio dell'applicazione per il dominio applicazione predefinito di un processo è il `MyMgr` tipo nell' `AdMgrExample` assembly.</span><span class="sxs-lookup"><span data-stu-id="9f36b-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f36b-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9f36b-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9f36b-132">\<appDomainManagerAssembly>Elemento</span><span class="sxs-lookup"><span data-stu-id="9f36b-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="9f36b-133">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="9f36b-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9f36b-134">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="9f36b-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9f36b-135">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="9f36b-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
