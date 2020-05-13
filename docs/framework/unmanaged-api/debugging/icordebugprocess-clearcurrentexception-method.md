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
ms.openlocfilehash: b8d20de990ff4a27a82590342494a307c986457e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207400"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="47d6b-102">Metodo ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="47d6b-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="47d6b-103">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="47d6b-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47d6b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47d6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="47d6b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="47d6b-106">in ID del thread in cui verrà cancellata l'eccezione non gestita corrente.</span><span class="sxs-lookup"><span data-stu-id="47d6b-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d6b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47d6b-107">Remarks</span></span>  
 <span data-ttu-id="47d6b-108">Chiamare questo metodo prima di chiamare [ICorDebugController:: continue](icordebugcontroller-continue-method.md) quando un thread ha segnalato un'eccezione non gestita che deve essere ignorata dall'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="47d6b-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="47d6b-109">Questa operazione eliminerà gli eventi in banda (IB) e fuori banda (OOB) in attesa sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="47d6b-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="47d6b-110">Tutti i punti di interruzione OOB e le eccezioni a singolo passaggio vengono cancellati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="47d6b-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="47d6b-111">Usare [ICorDebugThread2:: InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) per intercettare l'eccezione gestita corrente su un thread.</span><span class="sxs-lookup"><span data-stu-id="47d6b-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d6b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47d6b-112">Requirements</span></span>  
 <span data-ttu-id="47d6b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47d6b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d6b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47d6b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47d6b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47d6b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47d6b-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
