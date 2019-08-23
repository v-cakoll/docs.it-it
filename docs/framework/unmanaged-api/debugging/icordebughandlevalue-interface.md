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
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915011"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="19c02-102">Interfaccia ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="19c02-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="19c02-103">Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento al quale il debugger ha creato un handle per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="19c02-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19c02-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="19c02-104">Methods</span></span>  
  
|<span data-ttu-id="19c02-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="19c02-105">Method</span></span>|<span data-ttu-id="19c02-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="19c02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19c02-107">Metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="19c02-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="19c02-108">Rilascia l'handle a cui fa riferimento `ICorDebugHandleValue` questo oggetto senza rilasciare in modo esplicito il puntatore all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="19c02-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="19c02-109">Metodo GetHandleType</span><span class="sxs-lookup"><span data-stu-id="19c02-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="19c02-110">Ottiene un valore CorDebugHandleType che descrive il tipo di handle a cui fa riferimento `ICorDebugHandleValue`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="19c02-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c02-111">Note</span><span class="sxs-lookup"><span data-stu-id="19c02-111">Remarks</span></span>  
 <span data-ttu-id="19c02-112">Un `ICorDebugReferenceValue` oggetto viene invalidato da un'operazione break nell'esecuzione del codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="19c02-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="19c02-113">Un `ICorDebugHandleValue` oggetto mantiene il riferimento tramite interruzioni e continuazioni, fino a quando non viene rilasciato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="19c02-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19c02-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="19c02-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c02-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19c02-115">Requirements</span></span>  
 <span data-ttu-id="19c02-116">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c02-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c02-117">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="19c02-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19c02-118">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19c02-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19c02-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c02-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c02-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c02-120">See also</span></span>

- [<span data-ttu-id="19c02-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="19c02-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
