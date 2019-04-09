---
title: Metodo IGCThreadControl::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd6c1dff30bce8857b9fb4092670667109932c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094082"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="69cf6-102">Metodo IGCThreadControl::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="69cf6-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="69cf6-103">Notifica all'host che il thread che effettua la chiamata sta per bloccare, ad esempio per un'operazione di garbage collection o altri sospensione.</span><span class="sxs-lookup"><span data-stu-id="69cf6-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cf6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69cf6-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="69cf6-105">Note</span><span class="sxs-lookup"><span data-stu-id="69cf6-105">Remarks</span></span>  
 <span data-ttu-id="69cf6-106">L'host può scegliere all'interno di `ThreadIsBlockingForSuspension` callback se si desidera modificare la pianificazione di un thread.</span><span class="sxs-lookup"><span data-stu-id="69cf6-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cf6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69cf6-107">Requirements</span></span>  
 <span data-ttu-id="69cf6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69cf6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69cf6-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69cf6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69cf6-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="69cf6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="69cf6-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="69cf6-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69cf6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69cf6-112">See also</span></span>

- [<span data-ttu-id="69cf6-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="69cf6-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
