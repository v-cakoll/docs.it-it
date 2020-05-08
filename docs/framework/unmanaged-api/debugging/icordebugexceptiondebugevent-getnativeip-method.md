---
title: Metodo ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 82dc892f3081c9f33ff7a2f363c326091f7cf039
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976031"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="4239c-102">Metodo ICorDebugExceptionDebugEvent::GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="4239c-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="4239c-103">Ottiene il puntatore alle istruzioni native per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4239c-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4239c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4239c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4239c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4239c-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="4239c-106">[out] Puntatore al puntatore alle istruzioni per l'attuale evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4239c-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="4239c-107">Per ulteriori informazioni, vedere le sezione Note.</span><span class="sxs-lookup"><span data-stu-id="4239c-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4239c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4239c-108">Remarks</span></span>  
 <span data-ttu-id="4239c-109">Il significato di questo puntatore alle istruzioni dipende dal tipo di evento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4239c-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="4239c-110">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="4239c-110">Event type</span></span>|<span data-ttu-id="4239c-111">Significato del valore `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="4239c-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="4239c-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="4239c-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="4239c-113">L'indirizzo dell'istruzione in errore.</span><span class="sxs-lookup"><span data-stu-id="4239c-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="4239c-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="4239c-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="4239c-115">Indirizzo del codice nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) in cui l'esecuzione riprende se non è stata generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="4239c-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="4239c-116">L'eccezione potrebbe determinare o non determinare codice diverso, ad esempio il blocco catch di una `try/catch/finally` che deve essere eseguito nel frame.</span><span class="sxs-lookup"><span data-stu-id="4239c-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="4239c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="4239c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="4239c-118">Indirizzo del codice in `catch` cui viene avviata l'esecuzione del gestore nel frame indicato dal metodo [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4239c-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="4239c-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="4239c-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="4239c-120">`pIP` è 0.</span><span class="sxs-lookup"><span data-stu-id="4239c-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="4239c-121">Il tipo di evento è disponibile dal metodo [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4239c-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4239c-122">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4239c-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4239c-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4239c-123">Requirements</span></span>  
 <span data-ttu-id="4239c-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4239c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4239c-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4239c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4239c-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4239c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4239c-127">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4239c-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4239c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4239c-128">See also</span></span>

- [<span data-ttu-id="4239c-129">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="4239c-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="4239c-130">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4239c-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
