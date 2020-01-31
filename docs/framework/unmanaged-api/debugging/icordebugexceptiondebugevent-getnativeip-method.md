---
title: Metodo ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 31af92dae47027b7285b422a05014b081d7e39a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788678"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="465c7-102">Metodo ICorDebugExceptionDebugEvent::GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="465c7-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="465c7-103">Ottiene il puntatore alle istruzioni native per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="465c7-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="465c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="465c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="465c7-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="465c7-106">[out] Puntatore al puntatore alle istruzioni per l'attuale evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="465c7-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="465c7-107">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="465c7-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="465c7-108">Note</span><span class="sxs-lookup"><span data-stu-id="465c7-108">Remarks</span></span>  
 <span data-ttu-id="465c7-109">Il significato di questo puntatore alle istruzioni dipende dal tipo di evento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="465c7-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="465c7-110">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="465c7-110">Event type</span></span>|<span data-ttu-id="465c7-111">Significato del valore `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="465c7-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="465c7-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="465c7-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="465c7-113">L'indirizzo dell'istruzione in errore.</span><span class="sxs-lookup"><span data-stu-id="465c7-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="465c7-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="465c7-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="465c7-115">Indirizzo del codice nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) in cui l'esecuzione riprende se non è stata generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="465c7-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="465c7-116">L'eccezione potrebbe determinare o non determinare codice diverso, ad esempio il blocco catch di una `try/catch/finally` che deve essere eseguito nel frame.</span><span class="sxs-lookup"><span data-stu-id="465c7-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="465c7-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="465c7-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="465c7-118">Indirizzo del codice in cui viene avviata l'esecuzione `catch` gestore nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="465c7-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="465c7-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="465c7-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="465c7-120">`pIP` è 0.</span><span class="sxs-lookup"><span data-stu-id="465c7-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="465c7-121">Il tipo di evento è disponibile dal metodo [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="465c7-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="465c7-122">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="465c7-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="465c7-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="465c7-123">Requirements</span></span>  
 <span data-ttu-id="465c7-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="465c7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="465c7-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="465c7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="465c7-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="465c7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="465c7-127">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="465c7-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465c7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="465c7-128">See also</span></span>

- [<span data-ttu-id="465c7-129">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="465c7-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="465c7-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="465c7-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
