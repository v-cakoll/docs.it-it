---
title: Metodo ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38d0ad7d84484c3b061429ee6cc1c38bc59586a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517266"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="d2d09-102">Metodo ICorDebugExceptionDebugEvent::GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="d2d09-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="d2d09-103">Ottiene il puntatore alle istruzioni native per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d2d09-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d09-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2d09-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2d09-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2d09-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="d2d09-106">[out] Puntatore al puntatore alle istruzioni per l'attuale evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d2d09-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="d2d09-107">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="d2d09-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2d09-108">Note</span><span class="sxs-lookup"><span data-stu-id="d2d09-108">Remarks</span></span>  
 <span data-ttu-id="d2d09-109">Il significato di questo puntatore alle istruzioni dipende dal tipo di evento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d2d09-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d2d09-110">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="d2d09-110">Event type</span></span>|<span data-ttu-id="d2d09-111">Significato del valore `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="d2d09-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="d2d09-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d2d09-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2d09-113">L'indirizzo dell'istruzione in errore.</span><span class="sxs-lookup"><span data-stu-id="d2d09-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="d2d09-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d2d09-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2d09-115">L'indirizzo di codice nel frame indicato dal [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) metodo in cui riprenderebbe l'esecuzione se non fosse stata generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="d2d09-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="d2d09-116">L'eccezione potrebbe determinare o non determinare codice diverso, ad esempio il blocco catch di una `try/catch/finally` che deve essere eseguito nel frame.</span><span class="sxs-lookup"><span data-stu-id="d2d09-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="d2d09-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d2d09-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2d09-118">Indirizzo del codice dove `catch` esecuzione del gestore verrà avviato nel frame indicato dal [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d2d09-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="d2d09-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d2d09-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2d09-120">`pIP` è 0.</span><span class="sxs-lookup"><span data-stu-id="d2d09-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="d2d09-121">Il tipo di evento è disponibile il [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d2d09-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2d09-122">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d2d09-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2d09-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2d09-123">Requirements</span></span>  
 <span data-ttu-id="d2d09-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2d09-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2d09-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2d09-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2d09-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2d09-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2d09-127">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2d09-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d09-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2d09-128">See also</span></span>
- [<span data-ttu-id="d2d09-129">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d2d09-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d2d09-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d2d09-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
