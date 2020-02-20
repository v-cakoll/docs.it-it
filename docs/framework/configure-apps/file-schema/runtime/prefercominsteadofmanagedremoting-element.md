---
title: <PreferComInsteadOfManagedRemoting> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452253"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="eeb37-102">\<elemento > PreferComInsteadOfManagedRemoting</span><span class="sxs-lookup"><span data-stu-id="eeb37-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="eeb37-103">Specifica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="eeb37-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="eeb37-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eeb37-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eeb37-105">&nbsp;&nbsp;[ **\<runtime >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="eeb37-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="eeb37-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**</span><span class="sxs-lookup"><span data-stu-id="eeb37-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb37-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eeb37-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eeb37-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eeb37-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eeb37-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eeb37-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eeb37-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="eeb37-110">Attributes</span></span>  
  
|<span data-ttu-id="eeb37-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="eeb37-111">Attribute</span></span>|<span data-ttu-id="eeb37-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eeb37-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="eeb37-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eeb37-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="eeb37-114">Indica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="eeb37-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="eeb37-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="eeb37-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="eeb37-116">Valore</span><span class="sxs-lookup"><span data-stu-id="eeb37-116">Value</span></span>|<span data-ttu-id="eeb37-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eeb37-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="eeb37-118">Il runtime userà la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="eeb37-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="eeb37-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eeb37-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="eeb37-120">Il runtime utilizzerà l'interoperabilità COM tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="eeb37-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eeb37-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eeb37-121">Child Elements</span></span>  
 <span data-ttu-id="eeb37-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="eeb37-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eeb37-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eeb37-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eeb37-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="eeb37-124">Element</span></span>|<span data-ttu-id="eeb37-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eeb37-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eeb37-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eeb37-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eeb37-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="eeb37-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb37-128">Note</span><span class="sxs-lookup"><span data-stu-id="eeb37-128">Remarks</span></span>  
 <span data-ttu-id="eeb37-129">Quando si imposta l'attributo `enabled` su `true`, il runtime si comporta come segue:</span><span class="sxs-lookup"><span data-stu-id="eeb37-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="eeb37-130">Il runtime non chiama [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) quando un'interfaccia [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) immette il dominio tramite un'interfaccia com.</span><span class="sxs-lookup"><span data-stu-id="eeb37-130">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="eeb37-131">Costruisce invece un [runtime callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) intorno all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="eeb37-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="eeb37-132">Il runtime restituisce E_NOINTERFACE quando riceve una chiamata `QueryInterface` per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) per qualsiasi CCW ( [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) creato in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="eeb37-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="eeb37-133">Questi due comportamenti assicurano che tutte le chiamate su interfacce COM tra oggetti gestiti tra i limiti del dominio dell'applicazione usino l'interoperabilità COM e COM anziché la comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="eeb37-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb37-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeb37-134">Example</span></span>  
 <span data-ttu-id="eeb37-135">Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare l'interoperabilità COM tra i limiti di isolamento:</span><span class="sxs-lookup"><span data-stu-id="eeb37-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eeb37-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eeb37-136">See also</span></span>

- [<span data-ttu-id="eeb37-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="eeb37-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eeb37-138">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="eeb37-138">Configuration File Schema</span></span>](../index.md)
