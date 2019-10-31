---
title: Interfaccia ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140851"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="13053-102">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="13053-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="13053-103">Fornisce il metodo [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , che restituisce un puntatore a un'interfaccia Common Language Runtime (CLR) in base a criteri di criteri, assembly gestito, versione e file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13053-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13053-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="13053-104">Methods</span></span>  
  
|<span data-ttu-id="13053-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="13053-105">Method</span></span>|<span data-ttu-id="13053-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13053-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13053-107">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="13053-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="13053-108">Fornisce un'interfaccia CLR preferita in base ai criteri, all'assembly gestito, alla versione e al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13053-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13053-109">Note</span><span class="sxs-lookup"><span data-stu-id="13053-109">Remarks</span></span>  
 <span data-ttu-id="13053-110">È possibile ottenere un riferimento a questa interfaccia chiamando la funzione [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) , come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="13053-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="13053-111">Questa interfaccia non carica o attiva il CLR, ma restituisce semplicemente la versione CLR preferita in base alle versioni disponibili installate o caricate.</span><span class="sxs-lookup"><span data-stu-id="13053-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="13053-112">L'API di hosting di .NET Framework 4 consolida i criteri in modo che gli host con esigenze specifiche possano usare le funzionalità di base senza incorrere in sanzioni impreviste.</span><span class="sxs-lookup"><span data-stu-id="13053-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="13053-113">Molte delle esportazioni MSCorEE. dll, ad esempio, vengono associate a uno specifico CLR, anche se è possibile che un metodo non lo richieda logicamente.</span><span class="sxs-lookup"><span data-stu-id="13053-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="13053-114">L'enumerazione [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) fornisce criteri di associazione comuni alla maggior parte degli host.</span><span class="sxs-lookup"><span data-stu-id="13053-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13053-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13053-115">Requirements</span></span>  
 <span data-ttu-id="13053-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13053-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13053-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="13053-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="13053-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13053-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13053-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13053-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13053-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13053-120">See also</span></span>

- [<span data-ttu-id="13053-121">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="13053-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="13053-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="13053-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="13053-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="13053-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
