---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="78ee6-102">&lt;PreferComInsteadOfManagedRemoting&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="78ee6-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="78ee6-103">Specifica se il runtime utilizzerà l'interoperabilità COM anziché remoti per tutte le chiamate tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="78ee6-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="78ee6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="78ee6-104">\<configuration></span></span>  
<span data-ttu-id="78ee6-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="78ee6-105">\<runtime></span></span>  
<span data-ttu-id="78ee6-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="78ee6-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78ee6-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78ee6-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78ee6-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78ee6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="78ee6-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78ee6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78ee6-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="78ee6-110">Attributes</span></span>  
  
|<span data-ttu-id="78ee6-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="78ee6-111">Attribute</span></span>|<span data-ttu-id="78ee6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78ee6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="78ee6-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="78ee6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="78ee6-114">Indica se il runtime utilizzerà l'interoperabilità COM anziché remoting limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="78ee6-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="78ee6-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="78ee6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="78ee6-116">Valore</span><span class="sxs-lookup"><span data-stu-id="78ee6-116">Value</span></span>|<span data-ttu-id="78ee6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78ee6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="78ee6-118">Il runtime utilizza comunicazione remota di limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="78ee6-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="78ee6-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="78ee6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="78ee6-120">Il runtime utilizzerà l'interoperabilità COM limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="78ee6-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78ee6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78ee6-121">Child Elements</span></span>  
 <span data-ttu-id="78ee6-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="78ee6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78ee6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78ee6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78ee6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="78ee6-124">Element</span></span>|<span data-ttu-id="78ee6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78ee6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="78ee6-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78ee6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="78ee6-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="78ee6-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78ee6-128">Note</span><span class="sxs-lookup"><span data-stu-id="78ee6-128">Remarks</span></span>  
 <span data-ttu-id="78ee6-129">Quando si imposta la `enabled` attributo `true`, il runtime si comporta come segue:</span><span class="sxs-lookup"><span data-stu-id="78ee6-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="78ee6-130">Il runtime non chiami [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia quando un [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interfaccia accede al dominio tramite un'interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="78ee6-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="78ee6-131">Invece, costruisce una [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) attorno all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="78ee6-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="78ee6-132">Il runtime restituisce E_NOINTERFACE quando riceve un `QueryInterface` chiamare per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia per qualsiasi [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) che è stato creato in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="78ee6-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="78ee6-133">Questi due comportamenti assicurarsi che tutte le chiamate tramite COM interfacce tra gli oggetti gestiti attraverso l'utilizzo di limiti di dominio dell'applicazione COM e l'interoperabilità COM anziché servizi remoti.</span><span class="sxs-lookup"><span data-stu-id="78ee6-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78ee6-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="78ee6-134">Example</span></span>  
 <span data-ttu-id="78ee6-135">Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare COM interoperabilità attraverso i limiti di isolamento:</span><span class="sxs-lookup"><span data-stu-id="78ee6-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78ee6-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78ee6-136">See Also</span></span>  
 [<span data-ttu-id="78ee6-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="78ee6-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="78ee6-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="78ee6-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
