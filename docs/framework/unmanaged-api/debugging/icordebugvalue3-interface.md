---
title: ICorDebugValue3 Interface
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
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791089"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="99c94-102">ICorDebugValue3 Interface</span><span class="sxs-lookup"><span data-stu-id="99c94-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="99c94-103">Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire supporto per matrici di dimensioni maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="99c94-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99c94-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="99c94-104">Methods</span></span>  
  
|<span data-ttu-id="99c94-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="99c94-105">Method</span></span>|<span data-ttu-id="99c94-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c94-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99c94-107">Metodo GetSize64</span><span class="sxs-lookup"><span data-stu-id="99c94-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="99c94-108">Ottiene le dimensioni in byte di questo oggetto `ICorDebugValue3`.</span><span class="sxs-lookup"><span data-stu-id="99c94-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c94-109">Note</span><span class="sxs-lookup"><span data-stu-id="99c94-109">Remarks</span></span>  
 <span data-ttu-id="99c94-110">Il metodo [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) restituisce le dimensioni dell'oggetto che variano da 0 a 2.147.483.647 byte.</span><span class="sxs-lookup"><span data-stu-id="99c94-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="99c94-111">Nella .NET Framework 4,5, le dimensioni delle matrici possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="99c94-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="99c94-112">L'interfaccia `ICorDebugValue3` consente di determinare le dimensioni di queste matrici.</span><span class="sxs-lookup"><span data-stu-id="99c94-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c94-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="99c94-113">Requirements</span></span>  
 <span data-ttu-id="99c94-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99c94-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c94-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99c94-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99c94-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99c94-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99c94-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c94-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c94-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99c94-118">See also</span></span>

- [<span data-ttu-id="99c94-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="99c94-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="99c94-120">Debug</span><span class="sxs-lookup"><span data-stu-id="99c94-120">Debugging</span></span>](index.md)
