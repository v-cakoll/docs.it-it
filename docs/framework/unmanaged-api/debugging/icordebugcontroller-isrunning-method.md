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
ms.openlocfilehash: 4605b893169ccfc592aae0d07dc032f455314cc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412732"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="224d1-102">Metodo ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="224d1-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="224d1-103">Ottiene un valore che indica se il thread del processo attualmente in esecuzione liberamente.</span><span class="sxs-lookup"><span data-stu-id="224d1-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="224d1-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="224d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="224d1-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="224d1-106">[out] Un puntatore a un valore che è `true` se il thread del processo in esecuzione liberamente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="224d1-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="224d1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="224d1-107">Requirements</span></span>  
 <span data-ttu-id="224d1-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="224d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="224d1-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="224d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="224d1-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="224d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="224d1-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="224d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224d1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="224d1-112">See Also</span></span>  
 
