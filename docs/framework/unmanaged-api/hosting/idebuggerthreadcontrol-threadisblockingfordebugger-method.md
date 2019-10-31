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
ms.openlocfilehash: 067d4e844055206543e5c7fb409296b0d0a7a549
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134945"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="7473b-102">Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="7473b-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="7473b-103">Notifica all'host che il thread che sta inviando questo callback sta per bloccarsi nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="7473b-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7473b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7473b-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="7473b-105">Note</span><span class="sxs-lookup"><span data-stu-id="7473b-105">Remarks</span></span>  
 <span data-ttu-id="7473b-106">Il metodo `ThreadIsBlockingForDebugger` sarà sempre chiamato su un thread di Runtime.</span><span class="sxs-lookup"><span data-stu-id="7473b-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="7473b-107">Il metodo `ThreadIsBlockingForDebugger` offre all'host la possibilità di eseguire un'altra azione durante il blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="7473b-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7473b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7473b-108">Requirements</span></span>  
 <span data-ttu-id="7473b-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7473b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7473b-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7473b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7473b-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7473b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7473b-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7473b-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7473b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7473b-113">See also</span></span>

- [<span data-ttu-id="7473b-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="7473b-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
