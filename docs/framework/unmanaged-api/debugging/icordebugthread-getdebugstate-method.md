---
title: Metodo ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762454"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="9682d-102">Metodo ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="9682d-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="9682d-103">Ottiene lo stato di debug corrente di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9682d-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9682d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9682d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9682d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9682d-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="9682d-106">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugThreadState che descrive lo stato di debug corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="9682d-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9682d-107">Note</span><span class="sxs-lookup"><span data-stu-id="9682d-107">Remarks</span></span>  
 <span data-ttu-id="9682d-108">Se il processo è inattivo, `pState` rappresenta lo stato di debug che esisterebbe per questo thread se il processo di proseguire, non lo stato attuale di questo thread.</span><span class="sxs-lookup"><span data-stu-id="9682d-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9682d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9682d-109">Requirements</span></span>  
 <span data-ttu-id="9682d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9682d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9682d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9682d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9682d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9682d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9682d-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9682d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
