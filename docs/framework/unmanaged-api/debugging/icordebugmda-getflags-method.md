---
title: Metodo ICorDebugMDA::GetFlags
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48a08261d3ed17fbbb1a040f356ed341ca863a53
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468936"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="b0cd5-102">Metodo ICorDebugMDA::GetFlags</span><span class="sxs-lookup"><span data-stu-id="b0cd5-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="b0cd5-103">Ottiene i flag associati l'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b0cd5-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0cd5-104">Syntax</span></span>  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0cd5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0cd5-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="b0cd5-106">[in] Una combinazione bit per bit del [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) valori di enumerazione che specificano le impostazioni dei flag per questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="b0cd5-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0cd5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0cd5-107">Requirements</span></span>  
 <span data-ttu-id="b0cd5-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0cd5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0cd5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0cd5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0cd5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0cd5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0cd5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0cd5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cd5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0cd5-112">See also</span></span>
- [<span data-ttu-id="b0cd5-113">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="b0cd5-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="b0cd5-114">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="b0cd5-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
