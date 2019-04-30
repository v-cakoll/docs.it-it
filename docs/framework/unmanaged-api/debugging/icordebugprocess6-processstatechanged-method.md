---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4dcee3b396d9533f3169db1ea54a6cdc6086c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948590"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="aa838-102">Metodo ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="aa838-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="aa838-103">Invia una notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="aa838-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa838-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa838-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa838-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa838-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="aa838-106">[in] Un membro del [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumerazione</span><span class="sxs-lookup"><span data-stu-id="aa838-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa838-107">Note</span><span class="sxs-lookup"><span data-stu-id="aa838-107">Remarks</span></span>  
 <span data-ttu-id="aa838-108">Il debugger chiama questo metodo per notificare [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="aa838-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa838-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="aa838-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa838-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa838-110">Requirements</span></span>  
 <span data-ttu-id="aa838-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa838-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa838-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa838-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa838-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa838-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa838-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa838-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa838-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa838-115">See also</span></span>

- [<span data-ttu-id="aa838-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="aa838-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="aa838-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="aa838-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
