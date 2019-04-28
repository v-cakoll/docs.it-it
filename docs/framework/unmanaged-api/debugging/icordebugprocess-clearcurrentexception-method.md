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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f014f9213a4b9a2d5119af9a6dceebb9a9d54b52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775603"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="0cda2-102">Metodo ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="0cda2-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="0cda2-103">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0cda2-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cda2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cda2-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cda2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cda2-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0cda2-106">[in] L'ID del thread in cui l'eccezione non gestita corrente verrà cancellato.</span><span class="sxs-lookup"><span data-stu-id="0cda2-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cda2-107">Note</span><span class="sxs-lookup"><span data-stu-id="0cda2-107">Remarks</span></span>  
 <span data-ttu-id="0cda2-108">Chiamare questo metodo prima di chiamare [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) quando un thread ha segnalato un'eccezione non gestita che deve essere ignorata dall'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="0cda2-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="0cda2-109">Ciò consente di correggere in sospeso in banda (IB) sia gli eventi di out-of-band (OOB) sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0cda2-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="0cda2-110">Tutti i punti di interruzione OOB e passo a passo eccezioni vengono automaticamente cancellate.</span><span class="sxs-lookup"><span data-stu-id="0cda2-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="0cda2-111">Uso [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) intercettare corrente delle eccezioni in un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="0cda2-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cda2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cda2-112">Requirements</span></span>  
 <span data-ttu-id="0cda2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cda2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cda2-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cda2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cda2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cda2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cda2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cda2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
