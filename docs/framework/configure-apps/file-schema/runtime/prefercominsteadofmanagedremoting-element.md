---
title: <PreferComInsteadOfManagedRemoting> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77452253"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="48949-102">\<PreferComInsteadOfManagedRemoting> Elemento</span><span class="sxs-lookup"><span data-stu-id="48949-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="48949-103">Specifica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="48949-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="48949-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48949-104">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48949-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="48949-105">Attributes and Elements</span></span>  
 <span data-ttu-id="48949-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="48949-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48949-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="48949-107">Attributes</span></span>  
  
|<span data-ttu-id="48949-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="48949-108">Attribute</span></span>|<span data-ttu-id="48949-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48949-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="48949-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="48949-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="48949-111">Indica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="48949-111">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="48949-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="48949-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="48949-113">Valore</span><span class="sxs-lookup"><span data-stu-id="48949-113">Value</span></span>|<span data-ttu-id="48949-114">Description</span><span class="sxs-lookup"><span data-stu-id="48949-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="48949-115">Il runtime userà la comunicazione remota tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="48949-115">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="48949-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="48949-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="48949-117">Il runtime utilizzerà l'interoperabilità COM tra i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="48949-117">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48949-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="48949-118">Child Elements</span></span>  
 <span data-ttu-id="48949-119">No.</span><span class="sxs-lookup"><span data-stu-id="48949-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48949-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="48949-120">Parent Elements</span></span>  
  
|<span data-ttu-id="48949-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="48949-121">Element</span></span>|<span data-ttu-id="48949-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48949-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48949-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48949-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="48949-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="48949-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48949-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="48949-125">Remarks</span></span>  
 <span data-ttu-id="48949-126">Quando si imposta l' `enabled` attributo su `true` , il runtime si comporta come segue:</span><span class="sxs-lookup"><span data-stu-id="48949-126">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="48949-127">Il runtime non chiama [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) quando un'interfaccia [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) immette il dominio tramite un'interfaccia com.</span><span class="sxs-lookup"><span data-stu-id="48949-127">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="48949-128">Costruisce invece un [runtime callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) intorno all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48949-128">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="48949-129">Il runtime restituisce E_NOINTERFACE quando riceve una `QueryInterface` chiamata per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) per qualsiasi [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) creato in questo dominio.</span><span class="sxs-lookup"><span data-stu-id="48949-129">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="48949-130">Questi due comportamenti assicurano che tutte le chiamate su interfacce COM tra oggetti gestiti tra i limiti del dominio dell'applicazione usino l'interoperabilità COM e COM anziché la comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="48949-130">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48949-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="48949-131">Example</span></span>  
 <span data-ttu-id="48949-132">Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare l'interoperabilità COM tra i limiti di isolamento:</span><span class="sxs-lookup"><span data-stu-id="48949-132">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48949-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="48949-133">See also</span></span>

- [<span data-ttu-id="48949-134">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="48949-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="48949-135">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="48949-135">Configuration File Schema</span></span>](../index.md)
