---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af4c7feb7076eeac6089a3255c7832c17a43469b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208839"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="b1af1-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="b1af1-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="b1af1-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b1af1-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1af1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1af1-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1af1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1af1-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="b1af1-106">[out] Un puntatore a un [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) valore che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b1af1-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1af1-107">Note</span><span class="sxs-lookup"><span data-stu-id="b1af1-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1af1-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b1af1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1af1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1af1-109">Requirements</span></span>  
 <span data-ttu-id="b1af1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1af1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1af1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1af1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1af1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1af1-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1af1-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b1af1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1af1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1af1-114">See also</span></span>

- [<span data-ttu-id="b1af1-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b1af1-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="b1af1-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b1af1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
