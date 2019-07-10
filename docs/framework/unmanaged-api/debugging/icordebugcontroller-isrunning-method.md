---
title: Metodo ICorDebugController::IsRunning
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99dbe5c5da5b8c169e34aa29afca507cc6624f0f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748799"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="492be-102">Metodo ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="492be-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="492be-103">Ottiene un valore che indica se il thread del processo attualmente in esecuzione liberamente.</span><span class="sxs-lookup"><span data-stu-id="492be-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="492be-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="492be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="492be-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="492be-106">[out] Un puntatore a un valore che rappresenta `true` se il thread nel processo esegue liberamente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="492be-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="492be-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="492be-107">Requirements</span></span>  
 <span data-ttu-id="492be-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="492be-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492be-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="492be-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="492be-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="492be-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="492be-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492be-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="492be-112">See also</span></span>
