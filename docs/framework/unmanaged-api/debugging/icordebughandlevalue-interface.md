---
title: Interfaccia ICorDebugHandleValue
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775661"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="4af1d-102">Interfaccia ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="4af1d-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="4af1d-103">Sottoclasse di interfaccia ICorDebugReferenceValue che rappresenta un valore di riferimento a cui il debugger ha creato un handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="4af1d-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4af1d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4af1d-104">Methods</span></span>  
  
|<span data-ttu-id="4af1d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4af1d-105">Method</span></span>|<span data-ttu-id="4af1d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4af1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4af1d-107">Metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="4af1d-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="4af1d-108">Rilascia l'handle fa riferimento questo `ICorDebugHandleValue` oggetto senza rilasciare in modo esplicito il puntatore di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4af1d-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="4af1d-109">Metodo GetHandleType</span><span class="sxs-lookup"><span data-stu-id="4af1d-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="4af1d-110">Ottiene un valore CorDebugHandleType che descrive il tipo di handle fa riferimento questo `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="4af1d-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4af1d-111">Note</span><span class="sxs-lookup"><span data-stu-id="4af1d-111">Remarks</span></span>  
 <span data-ttu-id="4af1d-112">Un `ICorDebugReferenceValue` oggetto viene invalidato da un'interruzione nell'esecuzione del codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="4af1d-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="4af1d-113">Un `ICorDebugHandleValue` mantiene il riferimento durante le interruzioni e sulle continuazioni, fino a quando non viene rilasciato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="4af1d-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af1d-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4af1d-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af1d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4af1d-115">Requirements</span></span>  
 <span data-ttu-id="4af1d-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af1d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af1d-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4af1d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af1d-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af1d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af1d-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af1d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af1d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af1d-120">See also</span></span>

- [<span data-ttu-id="4af1d-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4af1d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
