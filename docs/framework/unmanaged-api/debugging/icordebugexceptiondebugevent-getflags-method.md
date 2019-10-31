---
title: 'Metodo ICorDebugExceptionDebugEvent:: GetFlags'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 6c330ce5b375daacdf257eda16fd5e34012f5d69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084761"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="9bb91-102">Metodo ICorDebugExceptionDebugEvent:: GetFlags</span><span class="sxs-lookup"><span data-stu-id="9bb91-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="9bb91-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9bb91-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bb91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bb91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bb91-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="9bb91-106">out Puntatore a un valore [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) che indica se l'eccezione può essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="9bb91-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bb91-107">Note</span><span class="sxs-lookup"><span data-stu-id="9bb91-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bb91-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9bb91-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb91-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bb91-109">Requirements</span></span>  
 <span data-ttu-id="9bb91-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bb91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb91-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bb91-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bb91-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bb91-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bb91-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb91-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb91-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bb91-114">See also</span></span>

- [<span data-ttu-id="9bb91-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9bb91-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="9bb91-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9bb91-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
