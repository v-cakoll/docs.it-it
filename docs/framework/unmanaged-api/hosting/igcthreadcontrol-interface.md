---
title: Interfaccia IGCThreadControl
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134794"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="9336d-102">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="9336d-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="9336d-103">Fornisce metodi per partecipare alla pianificazione dei thread che altrimenti verrebbero bloccati per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9336d-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9336d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9336d-104">Methods</span></span>  
  
|<span data-ttu-id="9336d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9336d-105">Method</span></span>|<span data-ttu-id="9336d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9336d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9336d-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="9336d-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="9336d-108">Notifica all'host che il Runtime sta riprendendo i thread dopo una Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="9336d-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="9336d-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="9336d-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="9336d-110">Notifica all'host che il Runtime sta iniziando una sospensione di thread per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="9336d-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="9336d-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="9336d-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="9336d-112">Notifica all'host che il thread che effettua la chiamata sta per essere bloccato, ad esempio per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="9336d-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9336d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9336d-113">Requirements</span></span>  
 <span data-ttu-id="9336d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9336d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9336d-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9336d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9336d-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9336d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9336d-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9336d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9336d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9336d-118">See also</span></span>

- [<span data-ttu-id="9336d-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9336d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
