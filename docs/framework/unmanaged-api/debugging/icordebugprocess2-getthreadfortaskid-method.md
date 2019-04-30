---
title: Metodo ICorDebugProcess2::GetThreadForTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa1f6852544dddcdf514b14710ade3949818c93e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948869"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="94974-102">Metodo ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="94974-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="94974-103">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="94974-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94974-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94974-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94974-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94974-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="94974-106">[in] L'identificatore dell'attività.</span><span class="sxs-lookup"><span data-stu-id="94974-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="94974-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread2 che rappresenta il thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="94974-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94974-108">Note</span><span class="sxs-lookup"><span data-stu-id="94974-108">Remarks</span></span>  
 <span data-ttu-id="94974-109">L'host può impostare l'identificatore dell'attività usando il [SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="94974-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94974-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94974-110">Requirements</span></span>  
 <span data-ttu-id="94974-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94974-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94974-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94974-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94974-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94974-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94974-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94974-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
