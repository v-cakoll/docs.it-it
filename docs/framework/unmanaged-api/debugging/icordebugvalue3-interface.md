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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4bf3605331e6900fd890e49bb3f71f4ca4409c7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377587"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="6ba6f-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="6ba6f-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="6ba6f-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici di dimensioni superiori a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="6ba6f-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ba6f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6ba6f-104">Methods</span></span>  
  
|<span data-ttu-id="6ba6f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6ba6f-105">Method</span></span>|<span data-ttu-id="6ba6f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ba6f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ba6f-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="6ba6f-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="6ba6f-108">Ottiene la dimensione, espressa in byte, di questo `ICorDebugValue3` oggetto.</span><span class="sxs-lookup"><span data-stu-id="6ba6f-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ba6f-109">Note</span><span class="sxs-lookup"><span data-stu-id="6ba6f-109">Remarks</span></span>  
 <span data-ttu-id="6ba6f-110">Il [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensione di oggetto compreso nell'intervallo da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="6ba6f-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="6ba6f-111">In .NET Framework 4.5, le dimensioni delle matrici possono superare 2 GB.</span><span class="sxs-lookup"><span data-stu-id="6ba6f-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="6ba6f-112">Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="6ba6f-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ba6f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ba6f-113">Requirements</span></span>  
 <span data-ttu-id="6ba6f-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ba6f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ba6f-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ba6f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ba6f-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ba6f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ba6f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ba6f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba6f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ba6f-118">See also</span></span>

- [<span data-ttu-id="6ba6f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6ba6f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6ba6f-120">Debug</span><span class="sxs-lookup"><span data-stu-id="6ba6f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
