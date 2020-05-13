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
ms.openlocfilehash: 9386c77cc98df17d797d5886e1603ffc4824b6dc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205242"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="d046d-102">Metodo ICorDebugProcess5::EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="d046d-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="d046d-103">Ottiene un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="d046d-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d046d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d046d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d046d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d046d-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="d046d-106">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugHeapEnum](icordebugheapenum-interface.md) che è un enumeratore per gli oggetti che risiedono nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="d046d-106">[out] A pointer to the address of an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d046d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d046d-107">Remarks</span></span>  
 <span data-ttu-id="d046d-108">Prima di chiamare il `ICorDebugProcess5::EnumerateHeap` metodo, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del `areGCStructuresValid` campo dell'oggetto [COR_HEAPINFO](cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nello stato corrente sia enumerabile.</span><span class="sxs-lookup"><span data-stu-id="d046d-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="d046d-109">Inoltre, `ICorDebugProcess5::EnumerateHeap` restituisce `E_FAIL` se ci si connette troppo presto alla durata del processo, prima dell'allocazione della memoria per l'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="d046d-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="d046d-110">L'oggetto interfaccia [ICorDebugHeapEnum](icordebugheapenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_HEAPOBJECT](cor-heapobject-structure.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="d046d-110">The [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="d046d-111">Questo metodo popola l'oggetto raccolta [ICorDebugHeapEnum](icordebugheapenum-interface.md) con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze che forniscono informazioni su tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="d046d-111">This method populates the [ICorDebugHeapEnum](icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="d046d-112">La raccolta può includere anche [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze che forniscono informazioni sugli oggetti che non sono radice da alcun oggetto, ma che non sono stati ancora raccolti dall'Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="d046d-112">The collection may also include [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d046d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d046d-113">Requirements</span></span>  
 <span data-ttu-id="d046d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d046d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d046d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d046d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d046d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d046d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d046d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d046d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d046d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d046d-118">See also</span></span>

- [<span data-ttu-id="d046d-119">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="d046d-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d046d-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d046d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
