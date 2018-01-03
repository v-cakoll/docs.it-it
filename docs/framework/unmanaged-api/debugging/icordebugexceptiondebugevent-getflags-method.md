---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6e7767ca5467f69dc7f53728bda9daf5f08331c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="0ca6a-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="0ca6a-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="0ca6a-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0ca6a-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ca6a-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ca6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ca6a-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="0ca6a-106">[out] Un puntatore a un [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) valore che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0ca6a-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ca6a-107">Note</span><span class="sxs-lookup"><span data-stu-id="0ca6a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ca6a-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ca6a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca6a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ca6a-109">Requirements</span></span>  
 <span data-ttu-id="0ca6a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ca6a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca6a-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0ca6a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ca6a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ca6a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ca6a-113">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca6a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca6a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ca6a-114">See Also</span></span>  
 [<span data-ttu-id="0ca6a-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0ca6a-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="0ca6a-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0ca6a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
