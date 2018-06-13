---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5861762242412d7ab6f0c02f2b8f5c149f9453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420179"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="0069f-102">Metodo ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="0069f-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="0069f-103">Notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0069f-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0069f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0069f-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0069f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0069f-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="0069f-106">[in] Membro di [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumerazione</span><span class="sxs-lookup"><span data-stu-id="0069f-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0069f-107">Note</span><span class="sxs-lookup"><span data-stu-id="0069f-107">Remarks</span></span>  
 <span data-ttu-id="0069f-108">Il debugger chiama questo metodo per notificare [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0069f-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0069f-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0069f-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0069f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0069f-110">Requirements</span></span>  
 <span data-ttu-id="0069f-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0069f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0069f-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0069f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0069f-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0069f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0069f-114">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0069f-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0069f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0069f-115">See Also</span></span>  
 [<span data-ttu-id="0069f-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="0069f-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="0069f-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0069f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
