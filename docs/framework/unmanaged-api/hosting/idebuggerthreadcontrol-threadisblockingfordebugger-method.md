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
ms.openlocfilehash: aa72c136e98f80df6d2868c447e1c535ae61af06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739628"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="6b583-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="6b583-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="6b583-103">Notifica all'host che riguarda il thread che sta inviando il callback al blocco all'interno di servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="6b583-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b583-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b583-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6b583-105">Note</span><span class="sxs-lookup"><span data-stu-id="6b583-105">Remarks</span></span>  
 <span data-ttu-id="6b583-106">Il `ThreadIsBlockingForDebugger` metodo sarà sempre chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="6b583-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="6b583-107">Il `ThreadIsBlockingForDebugger` metodo consente all'host di un'opportunità per eseguire un'altra azione mentre il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="6b583-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b583-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b583-108">Requirements</span></span>  
 <span data-ttu-id="6b583-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b583-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b583-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b583-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b583-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6b583-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b583-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b583-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b583-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b583-113">See also</span></span>
- [<span data-ttu-id="6b583-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="6b583-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
