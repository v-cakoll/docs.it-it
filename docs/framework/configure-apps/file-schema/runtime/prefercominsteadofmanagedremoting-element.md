---
title: <PreferComInsteadOfManagedRemoting> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d793c8d84a15f554ada78f3c0dd1f0e936893fd4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252404"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="b159d-102">\<Elemento > PreferComInsteadOfManagedRemoting</span><span class="sxs-lookup"><span data-stu-id="b159d-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="b159d-103">Specifica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b159d-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="b159d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b159d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b159d-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b159d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b159d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting>**</span><span class="sxs-lookup"><span data-stu-id="b159d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b159d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b159d-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b159d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b159d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b159d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b159d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b159d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b159d-110">Attributes</span></span>  
  
|<span data-ttu-id="b159d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b159d-111">Attribute</span></span>|<span data-ttu-id="b159d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b159d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b159d-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b159d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b159d-114">Indica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b159d-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b159d-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b159d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b159d-116">Valore</span><span class="sxs-lookup"><span data-stu-id="b159d-116">Value</span></span>|<span data-ttu-id="b159d-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b159d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b159d-118">Il runtime userà la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b159d-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="b159d-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b159d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b159d-120">Il runtime utilizzerà l'interoperabilità COM tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b159d-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b159d-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b159d-121">Child Elements</span></span>  
 <span data-ttu-id="b159d-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b159d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b159d-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b159d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b159d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b159d-124">Element</span></span>|<span data-ttu-id="b159d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b159d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b159d-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b159d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b159d-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b159d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b159d-128">Note</span><span class="sxs-lookup"><span data-stu-id="b159d-128">Remarks</span></span>  
 <span data-ttu-id="b159d-129">Quando si imposta l' `enabled` attributo su `true`, il runtime si comporta come segue:</span><span class="sxs-lookup"><span data-stu-id="b159d-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="b159d-130">Il runtime non chiama [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) quando un'interfaccia [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) immette il dominio tramite un'interfaccia com.</span><span class="sxs-lookup"><span data-stu-id="b159d-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="b159d-131">Costruisce invece un [runtime callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) intorno all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b159d-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="b159d-132">Il runtime restituisce E_NOINTERFACE quando riceve una `QueryInterface` chiamata per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) per qualsiasi [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) creato in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="b159d-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="b159d-133">Questi due comportamenti assicurano che tutte le chiamate su interfacce COM tra oggetti gestiti tra i limiti del dominio dell'applicazione usino l'interoperabilità COM e COM anziché la comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="b159d-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b159d-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="b159d-134">Example</span></span>  
 <span data-ttu-id="b159d-135">Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare l'interoperabilità COM tra i limiti di isolamento:</span><span class="sxs-lookup"><span data-stu-id="b159d-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b159d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b159d-136">See also</span></span>

- [<span data-ttu-id="b159d-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b159d-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b159d-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b159d-138">Configuration File Schema</span></span>](../index.md)
