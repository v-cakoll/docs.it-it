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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134264"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="7be0e-102">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="7be0e-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="7be0e-103">Fornisce metodi per partecipare alla pianificazione di thread verrebbe bloccato in caso contrario, per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7be0e-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7be0e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7be0e-104">Methods</span></span>  
  
|<span data-ttu-id="7be0e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7be0e-105">Method</span></span>|<span data-ttu-id="7be0e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7be0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7be0e-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="7be0e-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="7be0e-108">Notifica all'host che il runtime viene ripresa dei thread dopo un'operazione di garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="7be0e-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7be0e-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="7be0e-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="7be0e-110">Notifica all'host di runtime è l'avvio di una sospensione di thread per una garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="7be0e-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="7be0e-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="7be0e-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="7be0e-112">Notifica all'host che il thread che effettua la chiamata sta per bloccare, ad esempio per un'operazione di garbage collection o altri sospensione.</span><span class="sxs-lookup"><span data-stu-id="7be0e-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7be0e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7be0e-113">Requirements</span></span>  
 <span data-ttu-id="7be0e-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be0e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be0e-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7be0e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7be0e-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7be0e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7be0e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be0e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be0e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7be0e-118">See also</span></span>

- [<span data-ttu-id="7be0e-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7be0e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
