---
title: Metodo ICorDebugProcess2::GetThreadForTaskID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetThreadForTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af63e6cf0d7e4b51f9365c1ccc4ac78158c091bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a><span data-ttu-id="0be9b-102">Metodo ICorDebugProcess2::GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="0be9b-102">ICorDebugProcess2::GetThreadForTaskID Method</span></span>
<span data-ttu-id="0be9b-103">Ottiene il thread su cui è in esecuzione l'attività con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="0be9b-103">Gets the thread on which the task with the specified identifier is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0be9b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0be9b-105">Parameters</span></span>  
 `taskid`  
 <span data-ttu-id="0be9b-106">[in] Identificatore dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0be9b-106">[in] The identifier of the task.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="0be9b-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread2 che rappresenta il thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="0be9b-107">[out] A pointer to the address of an ICorDebugThread2 object that represents the thread to be retrieved.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be9b-108">Note</span><span class="sxs-lookup"><span data-stu-id="0be9b-108">Remarks</span></span>  
 <span data-ttu-id="0be9b-109">L'host è possibile impostare l'identificatore di attività tramite il [SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="0be9b-109">The host can set the task identifier by using the [ICLRTask::SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be9b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0be9b-110">Requirements</span></span>  
 <span data-ttu-id="0be9b-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be9b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be9b-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0be9b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0be9b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be9b-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
