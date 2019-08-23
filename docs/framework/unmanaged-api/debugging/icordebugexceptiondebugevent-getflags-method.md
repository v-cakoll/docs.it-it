---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbe6f6a2953c3f815606e881b86a693b7a0e6ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951905"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="3074f-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="3074f-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="3074f-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3074f-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3074f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3074f-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3074f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3074f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="3074f-106">out Puntatore a un valore [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) che indica se l'eccezione può essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="3074f-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3074f-107">Note</span><span class="sxs-lookup"><span data-stu-id="3074f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3074f-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3074f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3074f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3074f-109">Requirements</span></span>  
 <span data-ttu-id="3074f-110">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3074f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3074f-111">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3074f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3074f-112">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3074f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3074f-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3074f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3074f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3074f-114">See also</span></span>

- [<span data-ttu-id="3074f-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="3074f-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="3074f-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3074f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
