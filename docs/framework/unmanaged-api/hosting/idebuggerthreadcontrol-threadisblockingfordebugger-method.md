---
title: Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9324e1596913fdafb13239dbefd631cbe3c6ffe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780481"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="2e55c-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="2e55c-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="2e55c-103">Notifica all'host che riguarda il thread che sta inviando il callback al blocco all'interno di servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="2e55c-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e55c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e55c-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e55c-105">Note</span><span class="sxs-lookup"><span data-stu-id="2e55c-105">Remarks</span></span>  
 <span data-ttu-id="2e55c-106">Il `ThreadIsBlockingForDebugger` metodo sarà sempre chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="2e55c-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="2e55c-107">Il `ThreadIsBlockingForDebugger` metodo consente all'host di un'opportunità per eseguire un'altra azione mentre il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="2e55c-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e55c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e55c-108">Requirements</span></span>  
 <span data-ttu-id="2e55c-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e55c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e55c-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e55c-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e55c-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2e55c-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e55c-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e55c-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e55c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e55c-113">See also</span></span>

- [<span data-ttu-id="2e55c-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="2e55c-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
