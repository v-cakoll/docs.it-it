---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e5aad3e95668525fe607bf4e90b4e05b2b58cad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="5c7f7-102">Metodo ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="5c7f7-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="5c7f7-103">Notifica [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c7f7-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c7f7-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c7f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c7f7-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="5c7f7-106">[in] Membro di [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumerazione</span><span class="sxs-lookup"><span data-stu-id="5c7f7-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c7f7-107">Note</span><span class="sxs-lookup"><span data-stu-id="5c7f7-107">Remarks</span></span>  
 <span data-ttu-id="5c7f7-108">Il debugger chiama questo metodo per notificare [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5c7f7-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c7f7-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5c7f7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c7f7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c7f7-110">Requirements</span></span>  
 <span data-ttu-id="5c7f7-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c7f7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c7f7-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5c7f7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c7f7-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c7f7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c7f7-114">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c7f7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c7f7-115">See Also</span></span>  
 [<span data-ttu-id="5c7f7-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="5c7f7-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="5c7f7-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5c7f7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
