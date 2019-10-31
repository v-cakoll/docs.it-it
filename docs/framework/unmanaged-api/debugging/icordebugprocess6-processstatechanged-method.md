---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123425"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="98c2c-102">Metodo ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="98c2c-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="98c2c-103">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98c2c-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98c2c-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98c2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98c2c-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="98c2c-106">in Membro dell'enumerazione [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="98c2c-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98c2c-107">Note</span><span class="sxs-lookup"><span data-stu-id="98c2c-107">Remarks</span></span>  
 <span data-ttu-id="98c2c-108">Il debugger chiama questo metodo per notificare a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="98c2c-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98c2c-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="98c2c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98c2c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98c2c-110">Requirements</span></span>  
 <span data-ttu-id="98c2c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98c2c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98c2c-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98c2c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98c2c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98c2c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98c2c-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98c2c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c2c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c2c-115">See also</span></span>

- [<span data-ttu-id="98c2c-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="98c2c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="98c2c-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="98c2c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
