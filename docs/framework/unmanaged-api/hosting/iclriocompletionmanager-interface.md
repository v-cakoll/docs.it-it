---
title: Interfaccia ICLRIoCompletionManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156065"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="4dc09-102">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4dc09-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="4dc09-103">Implementa un metodo di callback che consente all'host di common language runtime (CLR) di inviare una notifica dello stato dei / o specifico le richieste.</span><span class="sxs-lookup"><span data-stu-id="4dc09-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4dc09-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4dc09-104">Methods</span></span>  
  
|<span data-ttu-id="4dc09-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4dc09-105">Method</span></span>|<span data-ttu-id="4dc09-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dc09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4dc09-107">Metodo OnComplete</span><span class="sxs-lookup"><span data-stu-id="4dc09-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="4dc09-108">Invia una notifica dello stato di una richiesta dei / o che è stato effettuato mediante una chiamata a CLR i [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="4dc09-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dc09-109">Note</span><span class="sxs-lookup"><span data-stu-id="4dc09-109">Remarks</span></span>  
 <span data-ttu-id="4dc09-110">L'host implementa l'astrazione di completamento i/o utilizzando il [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4dc09-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="4dc09-111">Common Language Runtime effettua le richieste dei / o tramite questa interfaccia e l'host di notifica il runtime il risultato di tali richieste usando il `ICLRIoCompletionManager` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4dc09-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dc09-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dc09-112">Requirements</span></span>  
 <span data-ttu-id="4dc09-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dc09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dc09-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4dc09-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4dc09-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4dc09-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4dc09-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4dc09-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4dc09-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc09-117">See also</span></span>

- [<span data-ttu-id="4dc09-118">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4dc09-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="4dc09-119">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="4dc09-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="4dc09-120">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4dc09-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
