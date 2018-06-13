---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b9c07b010447b4a437febb4b60565111a85c8d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415457"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="5d733-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="5d733-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="5d733-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5d733-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d733-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d733-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d733-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d733-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="5d733-106">[out] Un puntatore a un [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) valore che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5d733-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d733-107">Note</span><span class="sxs-lookup"><span data-stu-id="5d733-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d733-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5d733-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d733-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d733-109">Requirements</span></span>  
 <span data-ttu-id="5d733-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d733-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d733-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5d733-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d733-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5d733-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d733-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d733-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d733-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d733-114">See Also</span></span>  
 [<span data-ttu-id="5d733-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5d733-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="5d733-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5d733-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
