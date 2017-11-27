---
title: Interfaccia ICLRMetaHostPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8cbe1d397e1214cfa4d3f4cbc3d6cdf2d3ccd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="a3f54-102">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="a3f54-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="a3f54-103">Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo, che restituisce un puntatore a un'interfaccia di runtime (CLR) di linguaggio comune in base a criteri di criteri, gestito al file di configurazione, versione e assembly.</span><span class="sxs-lookup"><span data-stu-id="a3f54-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3f54-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a3f54-104">Methods</span></span>  
  
|<span data-ttu-id="a3f54-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a3f54-105">Method</span></span>|<span data-ttu-id="a3f54-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3f54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3f54-107">GetRequestedRuntime (metodo)</span><span class="sxs-lookup"><span data-stu-id="a3f54-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="a3f54-108">Fornisce un'interfaccia CLR preferita in base a criteri di criteri, i file di configurazione, versione e assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="a3f54-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f54-109">Note</span><span class="sxs-lookup"><span data-stu-id="a3f54-109">Remarks</span></span>  
 <span data-ttu-id="a3f54-110">È possibile ottenere un riferimento a questa interfaccia chiamando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funzione come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a3f54-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="a3f54-111">Questa interfaccia non è effettivamente caricare o attivare il CLR, ma restituisce semplicemente la versione CLR preferita in base alle versioni disponibili che sono installate o caricate.</span><span class="sxs-lookup"><span data-stu-id="a3f54-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="a3f54-112">Il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API di hosting consolida i criteri in modo che gli host con esigenze specifiche possono utilizzare le funzionalità di base senza incorrere in problemi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="a3f54-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="a3f54-113">Ad esempio, molte delle esportazioni MSCorEE.dll verrà associato a un CLR specifico, anche se un metodo potrebbe non richiederlo.</span><span class="sxs-lookup"><span data-stu-id="a3f54-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="a3f54-114">Il [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumerazione fornisce criteri di associazione che sono comuni alla maggior parte degli host.</span><span class="sxs-lookup"><span data-stu-id="a3f54-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f54-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3f54-115">Requirements</span></span>  
 <span data-ttu-id="a3f54-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f54-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f54-117">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="a3f54-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3f54-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3f54-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f54-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f54-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f54-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f54-120">See Also</span></span>  
 [<span data-ttu-id="a3f54-121">Interfacce di Hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="a3f54-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="a3f54-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a3f54-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a3f54-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="a3f54-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
