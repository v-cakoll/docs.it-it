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
ms.openlocfilehash: f9a70cf0812f84908630f109ef06aafa4b4f7525
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434422"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="8f94b-102">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="8f94b-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="8f94b-103">Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo, che restituisce un puntatore a un'interfaccia di runtime (CLR) di linguaggio comune in base a criteri di criteri, gestito al file di configurazione, versione e assembly.</span><span class="sxs-lookup"><span data-stu-id="8f94b-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f94b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8f94b-104">Methods</span></span>  
  
|<span data-ttu-id="8f94b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8f94b-105">Method</span></span>|<span data-ttu-id="8f94b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f94b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f94b-107">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="8f94b-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="8f94b-108">Fornisce un'interfaccia CLR preferita in base a criteri di criteri, i file di configurazione, versione e assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="8f94b-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f94b-109">Note</span><span class="sxs-lookup"><span data-stu-id="8f94b-109">Remarks</span></span>  
 <span data-ttu-id="8f94b-110">È possibile ottenere un riferimento a questa interfaccia chiamando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8f94b-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="8f94b-111">Questa interfaccia non è effettivamente caricare o attivare il CLR, ma restituisce semplicemente la versione CLR preferita in base alle versioni disponibili che sono installate o caricate.</span><span class="sxs-lookup"><span data-stu-id="8f94b-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="8f94b-112">Il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API di hosting consolida i criteri in modo che gli host con esigenze specifiche possono utilizzare le funzionalità di base senza incorrere in problemi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="8f94b-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="8f94b-113">Ad esempio, molte delle esportazioni MSCorEE.dll verrà associato a un CLR specifico, anche se un metodo potrebbe non richiederlo.</span><span class="sxs-lookup"><span data-stu-id="8f94b-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="8f94b-114">Il [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumerazione fornisce criteri di associazione che sono comuni alla maggior parte degli host.</span><span class="sxs-lookup"><span data-stu-id="8f94b-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f94b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f94b-115">Requirements</span></span>  
 <span data-ttu-id="8f94b-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f94b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f94b-117">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="8f94b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f94b-118">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8f94b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f94b-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f94b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f94b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f94b-120">See Also</span></span>  
 [<span data-ttu-id="8f94b-121">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="8f94b-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="8f94b-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8f94b-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8f94b-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="8f94b-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
