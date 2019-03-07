---
title: Metodo ICorDebugProcess5::EnumerateHeap
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b9e3444070a394a91cbb5aae8fe9f578c6e0374
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493557"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="a42bc-102">Metodo ICorDebugProcess5::EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="a42bc-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="a42bc-103">Ottiene un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a42bc-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a42bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a42bc-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a42bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a42bc-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="a42bc-106">[out] Un puntatore all'indirizzo di un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto di interfaccia che è un enumeratore per gli oggetti che risiedono nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="a42bc-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a42bc-107">Note</span><span class="sxs-lookup"><span data-stu-id="a42bc-107">Remarks</span></span>  
 <span data-ttu-id="a42bc-108">Prima di chiamare il `ICorDebugProcess5::EnumerateHeap` metodo, è necessario chiamare il [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) metodo ed esaminare il valore del `areGCStructuresValid` campo del valore restituito [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) oggetto da verificare che sia enumerabile heap di garbage collection nello stato corrente.</span><span class="sxs-lookup"><span data-stu-id="a42bc-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="a42bc-109">Inoltre, il `ICorDebugProcess5::EnumerateHeap` restituisce `E_FAIL` se si collega troppo presto nel ciclo di vita del processo, prima di memoria per l'heap gestito viene allocato.</span><span class="sxs-lookup"><span data-stu-id="a42bc-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="a42bc-110">Il [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto di interfaccia è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="a42bc-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="a42bc-111">Questo metodo popola i [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto insieme con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che forniscono informazioni su tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="a42bc-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="a42bc-112">La raccolta può includere [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che forniscono informazioni sugli oggetti che non contiene una radice da qualsiasi oggetto, ma non sono stati ancora raccolti dal garbage collector.</span><span class="sxs-lookup"><span data-stu-id="a42bc-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a42bc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a42bc-113">Requirements</span></span>  
 <span data-ttu-id="a42bc-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a42bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a42bc-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a42bc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a42bc-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a42bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a42bc-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a42bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42bc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a42bc-118">See also</span></span>
- [<span data-ttu-id="a42bc-119">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="a42bc-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="a42bc-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a42bc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
