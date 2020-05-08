---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976044"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="7ea4d-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="7ea4d-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="7ea4d-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7ea4d-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ea4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ea4d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ea4d-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="7ea4d-106">out Puntatore a un valore [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) che indica se l'eccezione può essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="7ea4d-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ea4d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7ea4d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ea4d-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ea4d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ea4d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ea4d-109">Requirements</span></span>  
 <span data-ttu-id="7ea4d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ea4d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ea4d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ea4d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ea4d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ea4d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ea4d-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ea4d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea4d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea4d-114">See also</span></span>

- [<span data-ttu-id="7ea4d-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7ea4d-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="7ea4d-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7ea4d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
