---
title: Metodo ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 4cfacb7f3303947ec8b11362fde82649687889d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792657"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="d6333-102">Metodo ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="d6333-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="d6333-103">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="d6333-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6333-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6333-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6333-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6333-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d6333-106">in ID del thread in cui verrà cancellata l'eccezione non gestita corrente.</span><span class="sxs-lookup"><span data-stu-id="d6333-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6333-107">Note</span><span class="sxs-lookup"><span data-stu-id="d6333-107">Remarks</span></span>  
 <span data-ttu-id="d6333-108">Chiamare questo metodo prima di chiamare [ICorDebugController:: continue](icordebugcontroller-continue-method.md) quando un thread ha segnalato un'eccezione non gestita che deve essere ignorata dall'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="d6333-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="d6333-109">Questa operazione eliminerà gli eventi in banda (IB) e fuori banda (OOB) in attesa sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="d6333-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="d6333-110">Tutti i punti di interruzione OOB e le eccezioni a singolo passaggio vengono cancellati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d6333-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="d6333-111">Usare [ICorDebugThread2:: InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) per intercettare l'eccezione gestita corrente su un thread.</span><span class="sxs-lookup"><span data-stu-id="d6333-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6333-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d6333-112">Requirements</span></span>  
 <span data-ttu-id="d6333-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6333-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6333-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6333-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6333-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6333-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6333-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6333-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
