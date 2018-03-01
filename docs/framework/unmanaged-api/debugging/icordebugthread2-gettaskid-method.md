---
title: Metodo ICorDebugThread2::GetTaskID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1b94478a0dfb8cc4d90dea611620238024634799
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="40565-102">Metodo ICorDebugThread2::GetTaskID</span><span class="sxs-lookup"><span data-stu-id="40565-102">ICorDebugThread2::GetTaskID Method</span></span>
<span data-ttu-id="40565-103">Ottiene l'identificatore dell'attività in esecuzione su questo thread.</span><span class="sxs-lookup"><span data-stu-id="40565-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40565-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40565-104">Syntax</span></span>  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40565-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40565-105">Parameters</span></span>  
 `pTaskId`  
 <span data-ttu-id="40565-106">[out] Un puntatore all'identificatore di attività in esecuzione sul thread rappresentato dall'oggetto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="40565-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40565-107">Note</span><span class="sxs-lookup"><span data-stu-id="40565-107">Remarks</span></span>  
 <span data-ttu-id="40565-108">Un'attività può essere eseguito solo sul thread se il thread è associato a una connessione.</span><span class="sxs-lookup"><span data-stu-id="40565-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="40565-109">`GetTaskID`restituisce zero in `pTaskId` se il thread non è associato a una connessione.</span><span class="sxs-lookup"><span data-stu-id="40565-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40565-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40565-110">Requirements</span></span>  
 <span data-ttu-id="40565-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40565-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40565-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="40565-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40565-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40565-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40565-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40565-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
