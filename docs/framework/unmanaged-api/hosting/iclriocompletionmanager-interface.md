---
title: Interfaccia ICLRIoCompletionManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="87029-102">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87029-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="87029-103">Implementa un metodo di callback che consente all'host di common language runtime (CLR) di notifica dello stato dei / o specificato richiede.</span><span class="sxs-lookup"><span data-stu-id="87029-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87029-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="87029-104">Methods</span></span>  
  
|<span data-ttu-id="87029-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="87029-105">Method</span></span>|<span data-ttu-id="87029-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87029-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87029-107">Metodo OnComplete</span><span class="sxs-lookup"><span data-stu-id="87029-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="87029-108">Notifica dello stato di una richiesta dei / o che è stato effettuato mediante una chiamata a CLR il [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="87029-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87029-109">Note</span><span class="sxs-lookup"><span data-stu-id="87029-109">Remarks</span></span>  
 <span data-ttu-id="87029-110">L'host implementa l'astrazione di completamento i/o tramite il [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="87029-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="87029-111">CLR effettua le richieste dei / o tramite questa interfaccia e l'host notifica il runtime il risultato di tali richieste utilizzando il `ICLRIoCompletionManager` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="87029-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87029-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87029-112">Requirements</span></span>  
 <span data-ttu-id="87029-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87029-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87029-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="87029-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87029-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87029-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87029-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87029-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87029-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87029-117">See Also</span></span>  
 [<span data-ttu-id="87029-118">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87029-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="87029-119">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="87029-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="87029-120">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="87029-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
