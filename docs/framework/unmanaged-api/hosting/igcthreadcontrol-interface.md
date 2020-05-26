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
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805124"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="5b56d-102">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="5b56d-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="5b56d-103">Fornisce metodi per partecipare alla pianificazione dei thread che altrimenti verrebbero bloccati per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5b56d-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b56d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5b56d-104">Methods</span></span>  
  
|<span data-ttu-id="5b56d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5b56d-105">Method</span></span>|<span data-ttu-id="5b56d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b56d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b56d-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="5b56d-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="5b56d-108">Notifica all'host che il Runtime sta riprendendo i thread dopo una Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="5b56d-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="5b56d-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="5b56d-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="5b56d-110">Notifica all'host che il Runtime sta iniziando una sospensione di thread per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="5b56d-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="5b56d-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="5b56d-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="5b56d-112">Notifica all'host che il thread che effettua la chiamata sta per essere bloccato, ad esempio per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="5b56d-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b56d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b56d-113">Requirements</span></span>  
 <span data-ttu-id="5b56d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b56d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b56d-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5b56d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b56d-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5b56d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b56d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b56d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b56d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b56d-118">See also</span></span>

- [<span data-ttu-id="5b56d-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5b56d-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
