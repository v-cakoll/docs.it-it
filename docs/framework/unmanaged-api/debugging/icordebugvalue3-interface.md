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
ms.openlocfilehash: d70a6f5c1df771c514f5f91770b4c53c55fec364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420669"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="87827-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="87827-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="87827-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="87827-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87827-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="87827-104">Methods</span></span>  
  
|<span data-ttu-id="87827-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="87827-105">Method</span></span>|<span data-ttu-id="87827-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87827-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87827-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="87827-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="87827-108">Ottiene le dimensioni, in byte, di questo `ICorDebugValue3` oggetto.</span><span class="sxs-lookup"><span data-stu-id="87827-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87827-109">Note</span><span class="sxs-lookup"><span data-stu-id="87827-109">Remarks</span></span>  
 <span data-ttu-id="87827-110">Il [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensioni dell'oggetto che va da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="87827-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="87827-111">Nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="87827-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="87827-112">Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="87827-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87827-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87827-113">Requirements</span></span>  
 <span data-ttu-id="87827-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87827-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87827-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="87827-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87827-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="87827-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87827-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87827-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87827-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87827-118">See Also</span></span>  
    
    
 [<span data-ttu-id="87827-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="87827-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="87827-120">Debug</span><span class="sxs-lookup"><span data-stu-id="87827-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
