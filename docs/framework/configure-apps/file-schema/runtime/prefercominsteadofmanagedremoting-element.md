---
title: <PreferComInsteadOfManagedRemoting> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32e4b490f0824cf97a1ae5910d7c74801c7b439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592685"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="dc938-102">\<PreferComInsteadOfManagedRemoting > elemento</span><span class="sxs-lookup"><span data-stu-id="dc938-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="dc938-103">Specifica se il runtime userà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc938-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="dc938-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc938-104">\<configuration></span></span>  
<span data-ttu-id="dc938-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="dc938-105">\<runtime></span></span>  
<span data-ttu-id="dc938-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="dc938-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc938-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc938-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc938-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dc938-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc938-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dc938-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc938-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="dc938-110">Attributes</span></span>  
  
|<span data-ttu-id="dc938-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="dc938-111">Attribute</span></span>|<span data-ttu-id="dc938-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc938-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="dc938-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc938-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="dc938-114">Indica se il runtime userà l'interoperabilità COM anziché la comunicazione remota attraverso i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc938-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dc938-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="dc938-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="dc938-116">Valore</span><span class="sxs-lookup"><span data-stu-id="dc938-116">Value</span></span>|<span data-ttu-id="dc938-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc938-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="dc938-118">Il runtime Usa .NET remoting superando i limiti di dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc938-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="dc938-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dc938-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="dc938-120">Il runtime userà l'interoperabilità COM superando i limiti di dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc938-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc938-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dc938-121">Child Elements</span></span>  
 <span data-ttu-id="dc938-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dc938-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc938-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dc938-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dc938-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc938-124">Element</span></span>|<span data-ttu-id="dc938-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc938-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc938-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc938-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dc938-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dc938-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc938-128">Note</span><span class="sxs-lookup"><span data-stu-id="dc938-128">Remarks</span></span>  
 <span data-ttu-id="dc938-129">Quando si impostano i `enabled` dell'attributo `true`, il runtime si comporta come segue:</span><span class="sxs-lookup"><span data-stu-id="dc938-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="dc938-130">Il runtime non chiami [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) per un' [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia quando un' [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interfaccia accede al dominio tramite un'interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="dc938-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="dc938-131">In alternativa, crea una [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) attorno all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc938-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="dc938-132">E_NOINTERFACE viene restituito dal runtime quando riceve un `QueryInterface` chiamare per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia per qualsiasi [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) che è stato creato in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="dc938-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="dc938-133">Questi due comportamenti assicurarsi che tutte le chiamate su COM interfacce tra gli oggetti gestiti attraverso l'utilizzo dei limiti di dominio dell'applicazione COM e l'interoperabilità COM anziché la comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="dc938-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc938-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc938-134">Example</span></span>  
 <span data-ttu-id="dc938-135">Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare COM interoperabilità tra i limiti di isolamento:</span><span class="sxs-lookup"><span data-stu-id="dc938-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc938-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc938-136">See also</span></span>

- [<span data-ttu-id="dc938-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="dc938-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="dc938-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="dc938-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
