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
ms.openlocfilehash: 4e5939e9e74899a33f28927c4fda09d0a8fb30a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209734"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="f64e0-102">Metodo ICorDebugMDA::GetFlags</span><span class="sxs-lookup"><span data-stu-id="f64e0-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="f64e0-103">Ottiene i flag associati all'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f64e0-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f64e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f64e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f64e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f64e0-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="f64e0-106">in Combinazione bit per bit dei valori di enumerazione [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) che specificano le impostazioni dei flag per questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f64e0-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f64e0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f64e0-107">Requirements</span></span>  
 <span data-ttu-id="f64e0-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f64e0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f64e0-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f64e0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f64e0-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f64e0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f64e0-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f64e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64e0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f64e0-112">See also</span></span>

- [<span data-ttu-id="f64e0-113">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="f64e0-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="f64e0-114">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f64e0-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
