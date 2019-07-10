---
title: Metodo IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc91ff0676fcec5d614f9d6fa4850eb2c81086b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779501"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="3f917-102">Metodo IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="3f917-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="3f917-103">Notifica all'host che il runtime viene ripresa dei thread dopo un'operazione di garbage collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="3f917-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f917-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f917-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f917-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f917-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="3f917-106">[in] La generazione in cui è stata eseguita una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3f917-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f917-107">Note</span><span class="sxs-lookup"><span data-stu-id="3f917-107">Remarks</span></span>  
 <span data-ttu-id="3f917-108">Non modificare la pianificazione di tutti i thread durante il `SuspensionEnding` callback.</span><span class="sxs-lookup"><span data-stu-id="3f917-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f917-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f917-109">Requirements</span></span>  
 <span data-ttu-id="3f917-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f917-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f917-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f917-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f917-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3f917-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f917-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f917-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f917-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f917-114">See also</span></span>

- [<span data-ttu-id="3f917-115">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="3f917-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
