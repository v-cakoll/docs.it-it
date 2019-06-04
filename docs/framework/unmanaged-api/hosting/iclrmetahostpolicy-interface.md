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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426d77114d3deeff94c39e2f5fc1f2e56e753641
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490283"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="5dd57-102">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="5dd57-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="5dd57-103">Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo, che restituisce un puntatore a un'interfaccia di runtime (CLR) di linguaggio comune basata su criteri, gestito al file di configurazione, versione e assembly.</span><span class="sxs-lookup"><span data-stu-id="5dd57-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5dd57-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5dd57-104">Methods</span></span>  
  
|<span data-ttu-id="5dd57-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5dd57-105">Method</span></span>|<span data-ttu-id="5dd57-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dd57-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5dd57-107">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="5dd57-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="5dd57-108">Fornisce un'interfaccia CLR preferita basata su criteri, gestito al file di configurazione, versione e assembly.</span><span class="sxs-lookup"><span data-stu-id="5dd57-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dd57-109">Note</span><span class="sxs-lookup"><span data-stu-id="5dd57-109">Remarks</span></span>  
 <span data-ttu-id="5dd57-110">È possibile ottenere un riferimento a questa interfaccia mediante la chiamata di [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzionano come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5dd57-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="5dd57-111">Questa interfaccia non effettivamente caricare o attivare il CLR, ma semplicemente restituisce la versione CLR preferita in base alle versioni disponibili che sono installate o caricate.</span><span class="sxs-lookup"><span data-stu-id="5dd57-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="5dd57-112">L'API di hosting di .NET Framework 4 consente di consolidare i criteri in modo che gli host grazie a esigenze specifiche possono usare la funzionalità di base senza incorrere in problemi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="5dd57-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="5dd57-113">Ad esempio, molte delle esportazioni Mscoree. dll verrà associato a un oggetto CLR specifico, anche se un metodo potrà non richiederlo.</span><span class="sxs-lookup"><span data-stu-id="5dd57-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="5dd57-114">Il [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumerazione fornisce i criteri di associazione che sono comuni alla maggior parte degli host.</span><span class="sxs-lookup"><span data-stu-id="5dd57-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd57-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dd57-115">Requirements</span></span>  
 <span data-ttu-id="5dd57-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dd57-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd57-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5dd57-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5dd57-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5dd57-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dd57-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd57-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd57-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dd57-120">See also</span></span>

- [<span data-ttu-id="5dd57-121">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="5dd57-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="5dd57-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5dd57-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5dd57-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="5dd57-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
