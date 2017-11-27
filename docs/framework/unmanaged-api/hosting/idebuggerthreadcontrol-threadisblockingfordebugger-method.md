---
title: Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5b14818f06fec78cfc2cff9ea66548c9ee87bb4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="8ca67-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="8ca67-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="8ca67-103">Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="8ca67-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ca67-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ca67-105">Note</span><span class="sxs-lookup"><span data-stu-id="8ca67-105">Remarks</span></span>  
 <span data-ttu-id="8ca67-106">Il `ThreadIsBlockingForDebugger` metodo sarà sempre chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="8ca67-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="8ca67-107">Il `ThreadIsBlockingForDebugger` metodo consente all'host la possibilità di eseguire un'altra azione mentre il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="8ca67-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca67-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ca67-108">Requirements</span></span>  
 <span data-ttu-id="8ca67-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ca67-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ca67-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8ca67-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ca67-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ca67-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ca67-112">**Versioni di .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca67-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca67-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ca67-113">See Also</span></span>  
 [<span data-ttu-id="8ca67-114">IDebuggerThreadControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8ca67-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
