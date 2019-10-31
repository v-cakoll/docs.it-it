---
title: Interfaccia ICorDebugValue3
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140212"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="74357-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="74357-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="74357-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire supporto per matrici di dimensioni maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="74357-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74357-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="74357-104">Methods</span></span>  
  
|<span data-ttu-id="74357-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="74357-105">Method</span></span>|<span data-ttu-id="74357-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74357-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74357-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="74357-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="74357-108">Ottiene le dimensioni in byte di questo oggetto `ICorDebugValue3`.</span><span class="sxs-lookup"><span data-stu-id="74357-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74357-109">Note</span><span class="sxs-lookup"><span data-stu-id="74357-109">Remarks</span></span>  
 <span data-ttu-id="74357-110">Il metodo [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) restituisce le dimensioni dell'oggetto che variano da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="74357-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="74357-111">Nella .NET Framework 4,5, le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="74357-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="74357-112">L'interfaccia `ICorDebugValue3` consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="74357-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74357-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74357-113">Requirements</span></span>  
 <span data-ttu-id="74357-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74357-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74357-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74357-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74357-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74357-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74357-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74357-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74357-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74357-118">See also</span></span>

- [<span data-ttu-id="74357-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="74357-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="74357-120">Debug</span><span class="sxs-lookup"><span data-stu-id="74357-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
