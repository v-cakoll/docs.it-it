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
ms.openlocfilehash: 89ea9f221ad55063e4186cc27cc8038334d800d4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892873"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="31a8a-102">Metodo ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="31a8a-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="31a8a-103">Ottiene un valore che indica se i thread del processo sono attualmente in esecuzione liberamente.</span><span class="sxs-lookup"><span data-stu-id="31a8a-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31a8a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31a8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31a8a-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="31a8a-106">out Puntatore a un valore che è `true` se i thread del processo vengono eseguiti liberamente; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="31a8a-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31a8a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31a8a-107">Requirements</span></span>  
 <span data-ttu-id="31a8a-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a8a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a8a-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31a8a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31a8a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31a8a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31a8a-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31a8a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a8a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31a8a-112">See also</span></span>
