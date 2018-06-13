---
title: ICorDebugHandleValue Interface1
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
ms.openlocfilehash: ed6ba8a738b4086b9150e0a1c7b300a519fa3092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419107"
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="53d68-102">ICorDebugHandleValue Interface1</span><span class="sxs-lookup"><span data-stu-id="53d68-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="53d68-103">Sottoclasse di ICorDebugReferenceValue che rappresenta un valore di riferimento a cui il debugger ha creato un handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="53d68-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53d68-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="53d68-104">Methods</span></span>  
  
|<span data-ttu-id="53d68-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="53d68-105">Method</span></span>|<span data-ttu-id="53d68-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53d68-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53d68-107">Metodo Dispose</span><span class="sxs-lookup"><span data-stu-id="53d68-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="53d68-108">Rilascia l'handle di cui fa riferimento questo `ICorDebugHandleValue` oggetto senza rilasciare esplicitamente il puntatore di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="53d68-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="53d68-109">Metodo GetHandleType</span><span class="sxs-lookup"><span data-stu-id="53d68-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="53d68-110">Ottiene un valore di CorDebugHandleType che descrive il tipo di cui fa riferimento l'handle `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="53d68-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53d68-111">Note</span><span class="sxs-lookup"><span data-stu-id="53d68-111">Remarks</span></span>  
 <span data-ttu-id="53d68-112">Un `ICorDebugReferenceValue` oggetto viene invalidato da un'interruzione dell'esecuzione di codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="53d68-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="53d68-113">Un `ICorDebugHandleValue` mantiene il riferimento durante le interruzioni e sulle continuazioni, fino a quando non viene rilasciato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="53d68-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53d68-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="53d68-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d68-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53d68-115">Requirements</span></span>  
 <span data-ttu-id="53d68-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53d68-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d68-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="53d68-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53d68-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="53d68-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53d68-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d68-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d68-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53d68-120">See Also</span></span>  
 [<span data-ttu-id="53d68-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="53d68-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
