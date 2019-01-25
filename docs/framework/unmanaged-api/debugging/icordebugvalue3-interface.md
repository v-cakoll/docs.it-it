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
ms.openlocfilehash: 34e1dd6adaa9906babca80f4cc610c157bd00534
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648245"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="db10e-102">Interfaccia ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="db10e-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="db10e-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici di dimensioni superiori a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="db10e-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db10e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="db10e-104">Methods</span></span>  
  
|<span data-ttu-id="db10e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="db10e-105">Method</span></span>|<span data-ttu-id="db10e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db10e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db10e-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="db10e-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="db10e-108">Ottiene la dimensione, espressa in byte, di questo `ICorDebugValue3` oggetto.</span><span class="sxs-lookup"><span data-stu-id="db10e-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db10e-109">Note</span><span class="sxs-lookup"><span data-stu-id="db10e-109">Remarks</span></span>  
 <span data-ttu-id="db10e-110">Il [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo restituisce una dimensione di oggetto compreso nell'intervallo da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="db10e-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="db10e-111">Nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="db10e-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="db10e-112">Il `ICorDebugValue3` interfaccia consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="db10e-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db10e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db10e-113">Requirements</span></span>  
 <span data-ttu-id="db10e-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db10e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db10e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db10e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db10e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db10e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db10e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db10e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db10e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db10e-118">See also</span></span>


- [<span data-ttu-id="db10e-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="db10e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="db10e-120">Debug</span><span class="sxs-lookup"><span data-stu-id="db10e-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
