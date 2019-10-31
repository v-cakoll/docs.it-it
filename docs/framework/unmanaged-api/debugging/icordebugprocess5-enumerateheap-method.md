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
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129654"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="e8008-102">Metodo ICorDebugProcess5::EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="e8008-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="e8008-103">Ottiene un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e8008-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8008-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8008-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8008-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8008-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e8008-106">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) che è un enumeratore per gli oggetti che risiedono nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e8008-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8008-107">Note</span><span class="sxs-lookup"><span data-stu-id="e8008-107">Remarks</span></span>  
 <span data-ttu-id="e8008-108">Prima di chiamare il metodo `ICorDebugProcess5::EnumerateHeap`, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del campo `areGCStructuresValid` dell'oggetto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nel relativo lo stato corrente è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="e8008-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="e8008-109">Inoltre, il `ICorDebugProcess5::EnumerateHeap` restituisce `E_FAIL` se ci si connette troppo presto nella durata del processo, prima dell'allocazione della memoria per l'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e8008-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="e8008-110">L'oggetto interfaccia [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare gli oggetti [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="e8008-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="e8008-111">Questo metodo popola l'oggetto raccolta [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) con istanze [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che forniscono informazioni su tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e8008-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="e8008-112">La raccolta può includere anche istanze di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che forniscono informazioni sugli oggetti che non sono radice da alcun oggetto, ma che non sono stati ancora raccolti dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="e8008-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8008-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8008-113">Requirements</span></span>  
 <span data-ttu-id="e8008-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8008-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8008-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8008-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8008-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8008-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8008-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8008-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8008-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8008-118">See also</span></span>

- [<span data-ttu-id="e8008-119">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="e8008-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="e8008-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e8008-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
