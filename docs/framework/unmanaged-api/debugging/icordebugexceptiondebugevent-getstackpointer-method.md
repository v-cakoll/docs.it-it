---
title: Metodo ICorDebugExceptionDebugEvent::GetStackPointer
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976018"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="d0873-102">Metodo ICorDebugExceptionDebugEvent::GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="d0873-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="d0873-103">Ottiene il puntatore dello stack per questo evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d0873-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0873-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0873-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0873-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0873-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="d0873-106">[out] Puntatore all'indirizzo del puntatore dello stack per l'attuale evento di debug per le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d0873-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="d0873-107">Per ulteriori informazioni, vedere le sezione Note.</span><span class="sxs-lookup"><span data-stu-id="d0873-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0873-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d0873-108">Remarks</span></span>  
 <span data-ttu-id="d0873-109">Il significato di questo puntatore dello stack dipende dal tipo di evento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0873-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d0873-110">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="d0873-110">Event type</span></span>|<span data-ttu-id="d0873-111">Significato del valore `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="d0873-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="d0873-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d0873-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d0873-113">Puntatore dello stack per il frame che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d0873-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="d0873-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d0873-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d0873-115">Puntatore dello stack per il frame di codice utente più vicino al punto dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="d0873-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="d0873-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d0873-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d0873-117">Puntatore dello stack per il frame che contiene il gestore catch.</span><span class="sxs-lookup"><span data-stu-id="d0873-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="d0873-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d0873-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d0873-119">`pStackPointer` è **Null**.</span><span class="sxs-lookup"><span data-stu-id="d0873-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d0873-120">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d0873-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="d0873-121">Il tipo di evento è disponibile dal metodo [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d0873-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0873-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0873-122">Requirements</span></span>  
 <span data-ttu-id="d0873-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0873-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0873-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0873-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0873-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0873-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0873-126">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0873-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0873-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0873-127">See also</span></span>

- [<span data-ttu-id="d0873-128">Interfaccia ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d0873-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d0873-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d0873-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
