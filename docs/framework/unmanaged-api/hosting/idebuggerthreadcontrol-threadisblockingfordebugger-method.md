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
ms.openlocfilehash: 9766c71c568c9661cf284e9c05eb2dd7634a95aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437430"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="aab37-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="aab37-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="aab37-103">Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="aab37-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aab37-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="aab37-105">Note</span><span class="sxs-lookup"><span data-stu-id="aab37-105">Remarks</span></span>  
 <span data-ttu-id="aab37-106">Il `ThreadIsBlockingForDebugger` metodo sarà sempre chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="aab37-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="aab37-107">Il `ThreadIsBlockingForDebugger` metodo consente all'host la possibilità di eseguire un'altra azione mentre il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="aab37-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab37-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aab37-108">Requirements</span></span>  
 <span data-ttu-id="aab37-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aab37-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab37-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="aab37-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aab37-111">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aab37-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aab37-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aab37-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab37-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aab37-113">See Also</span></span>  
 [<span data-ttu-id="aab37-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="aab37-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
