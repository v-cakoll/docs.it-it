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
ms.openlocfilehash: cd04e6d8bed86039b6f43985a8fb712b4612f76d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418350"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="eb1b8-102">Metodo ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="eb1b8-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="eb1b8-103">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="eb1b8-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb1b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb1b8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb1b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb1b8-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="eb1b8-106">[in] Identificatore dell'attività.</span><span class="sxs-lookup"><span data-stu-id="eb1b8-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="eb1b8-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread2 che rappresenta il thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="eb1b8-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb1b8-108">Note</span><span class="sxs-lookup"><span data-stu-id="eb1b8-108">Remarks</span></span>  
 <span data-ttu-id="eb1b8-109">L'host è possibile impostare l'identificatore di attività tramite il [SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="eb1b8-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb1b8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb1b8-110">Requirements</span></span>  
 <span data-ttu-id="eb1b8-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb1b8-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="eb1b8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb1b8-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="eb1b8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb1b8-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb1b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
