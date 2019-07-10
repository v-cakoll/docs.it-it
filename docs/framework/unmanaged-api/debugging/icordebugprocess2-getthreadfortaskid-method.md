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
ms.openlocfilehash: c85040a31966a92ead6ca4786f62852f17923056
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736928"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="3becb-102">Metodo ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="3becb-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="3becb-103">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="3becb-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3becb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3becb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3becb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3becb-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="3becb-106">[in] L'identificatore dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3becb-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="3becb-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread2 che rappresenta il thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3becb-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3becb-108">Note</span><span class="sxs-lookup"><span data-stu-id="3becb-108">Remarks</span></span>  
 <span data-ttu-id="3becb-109">L'host può impostare l'identificatore dell'attività usando il [SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3becb-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3becb-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3becb-110">Requirements</span></span>  
 <span data-ttu-id="3becb-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3becb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3becb-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3becb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3becb-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3becb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3becb-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3becb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
