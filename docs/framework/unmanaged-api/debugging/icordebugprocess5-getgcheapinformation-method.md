---
title: Metodo ICorDebugProcess5::GetGCHeapInformation
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 3aa9fe884b16a239f5105dd262edeb8fc3e4abaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084410"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="7cbff-102">Metodo ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="7cbff-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="7cbff-103">Fornisce informazioni generali sull'heap di Garbage Collection, ad esempio se è attualmente enumerabile.</span><span class="sxs-lookup"><span data-stu-id="7cbff-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cbff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cbff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7cbff-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="7cbff-106">out Puntatore a un valore [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) che fornisce informazioni generali sull'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7cbff-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cbff-107">Note</span><span class="sxs-lookup"><span data-stu-id="7cbff-107">Remarks</span></span>  
 <span data-ttu-id="7cbff-108">È necessario chiamare il metodo `ICorDebugProcess5::GetGCHeapInformation` prima di enumerare le aree heap o singoli heap per assicurarsi che le strutture Garbage Collection nel processo siano attualmente valide.</span><span class="sxs-lookup"><span data-stu-id="7cbff-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="7cbff-109">Non è possibile eseguire il percorso dell'heap Garbage Collection mentre è in corso una raccolta.</span><span class="sxs-lookup"><span data-stu-id="7cbff-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="7cbff-110">In caso contrario, è possibile che l'enumerazione acquisisca Garbage Collection strutture che non sono valide.</span><span class="sxs-lookup"><span data-stu-id="7cbff-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cbff-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cbff-111">Requirements</span></span>  
 <span data-ttu-id="7cbff-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cbff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cbff-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cbff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cbff-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cbff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cbff-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cbff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbff-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cbff-116">See also</span></span>

- [<span data-ttu-id="7cbff-117">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="7cbff-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="7cbff-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7cbff-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
