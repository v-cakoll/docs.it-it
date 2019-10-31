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
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141026"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="ce781-102">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ce781-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="ce781-103">Implementa un metodo di callback che consente all'host di notificare al Common Language Runtime (CLR) lo stato delle richieste di I/O specificate.</span><span class="sxs-lookup"><span data-stu-id="ce781-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce781-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ce781-104">Methods</span></span>  
  
|<span data-ttu-id="ce781-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ce781-105">Method</span></span>|<span data-ttu-id="ce781-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce781-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce781-107">Metodo OnComplete</span><span class="sxs-lookup"><span data-stu-id="ce781-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="ce781-108">Notifica a CLR lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ce781-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce781-109">Note</span><span class="sxs-lookup"><span data-stu-id="ce781-109">Remarks</span></span>  
 <span data-ttu-id="ce781-110">L'host implementa l'astrazione di completamento I/O usando l'interfaccia [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ce781-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="ce781-111">CLR esegue richieste di I/O tramite questa interfaccia e l'host notifica al runtime il risultato di tali richieste usando l'interfaccia `ICLRIoCompletionManager`.</span><span class="sxs-lookup"><span data-stu-id="ce781-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce781-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce781-112">Requirements</span></span>  
 <span data-ttu-id="ce781-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce781-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce781-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ce781-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce781-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ce781-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce781-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce781-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce781-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce781-117">See also</span></span>

- [<span data-ttu-id="ce781-118">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ce781-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="ce781-119">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ce781-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="ce781-120">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ce781-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
