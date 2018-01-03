---
title: Metodo ICorDebugProcess::ClearCurrentException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ClearCurrentException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905ade7e5c44861b4ad6e7eb57fe7d3e3e9e3002
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="e2930-102">Metodo ICorDebugProcess::ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="e2930-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="e2930-103">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="e2930-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2930-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2930-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2930-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2930-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e2930-106">[in] L'ID del thread in cui l'eccezione non gestita corrente verrà cancellato.</span><span class="sxs-lookup"><span data-stu-id="e2930-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2930-107">Note</span><span class="sxs-lookup"><span data-stu-id="e2930-107">Remarks</span></span>  
 <span data-ttu-id="e2930-108">Chiamare questo metodo prima di chiamare [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) quando un thread ha segnalato un'eccezione non gestita che deve essere ignorata dall'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="e2930-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="e2930-109">Ciò consente di correggere in sospeso in banda (IB) sia gli eventi di fuori banda (OOB) sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="e2930-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="e2930-110">Tutti i punti di interruzione fuori banda e passo-passo eccezioni vengono automaticamente deselezionate.</span><span class="sxs-lookup"><span data-stu-id="e2930-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="e2930-111">Utilizzare [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) intercettare corrente delle eccezioni in un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="e2930-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2930-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2930-112">Requirements</span></span>  
 <span data-ttu-id="e2930-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2930-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2930-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e2930-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2930-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2930-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2930-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2930-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
