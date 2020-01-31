---
title: Metodo ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782924"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="3c0cf-102">Metodo ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="3c0cf-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="3c0cf-103">Ottiene un flag che indica se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c0cf-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c0cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c0cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c0cf-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="3c0cf-106">out Puntatore a un valore [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) che indica se l'eccezione può essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="3c0cf-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c0cf-107">Note</span><span class="sxs-lookup"><span data-stu-id="3c0cf-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0cf-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3c0cf-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c0cf-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3c0cf-109">Requirements</span></span>  
 <span data-ttu-id="3c0cf-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c0cf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c0cf-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c0cf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c0cf-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c0cf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c0cf-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c0cf-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0cf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c0cf-114">See also</span></span>

- [<span data-ttu-id="3c0cf-115">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="3c0cf-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="3c0cf-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3c0cf-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
