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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703557"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="223fa-102">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="223fa-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="223fa-103">Implementa un metodo di callback che consente all'host di notificare al Common Language Runtime (CLR) lo stato delle richieste di I/O specificate.</span><span class="sxs-lookup"><span data-stu-id="223fa-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="223fa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="223fa-104">Methods</span></span>  
  
|<span data-ttu-id="223fa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="223fa-105">Method</span></span>|<span data-ttu-id="223fa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="223fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="223fa-107">Metodo OnComplete</span><span class="sxs-lookup"><span data-stu-id="223fa-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="223fa-108">Notifica a CLR lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="223fa-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="223fa-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="223fa-109">Remarks</span></span>  
 <span data-ttu-id="223fa-110">L'host implementa l'astrazione di completamento I/O usando l'interfaccia [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="223fa-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="223fa-111">CLR esegue richieste di I/O tramite questa interfaccia e l'host notifica al runtime il risultato di tali richieste usando l' `ICLRIoCompletionManager` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="223fa-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="223fa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="223fa-112">Requirements</span></span>  
 <span data-ttu-id="223fa-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="223fa-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223fa-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="223fa-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="223fa-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="223fa-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="223fa-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="223fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223fa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="223fa-117">See also</span></span>

- [<span data-ttu-id="223fa-118">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="223fa-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="223fa-119">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="223fa-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="223fa-120">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="223fa-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
