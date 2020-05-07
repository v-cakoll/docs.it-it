---
title: Interfaccia ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: 6f66e4a903be2e9b12a573f74638a62c58005689
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893460"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="daa78-102">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="daa78-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="daa78-103">Fornisce un metodo che estende "ICorDebugCode" e "ICorDebugCode2" per fornire informazioni su un valore restituito gestito.</span><span class="sxs-lookup"><span data-stu-id="daa78-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daa78-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="daa78-104">Methods</span></span>  
  
|<span data-ttu-id="daa78-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="daa78-105">Method</span></span>|<span data-ttu-id="daa78-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daa78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daa78-107">Metodo GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="daa78-107">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="daa78-108">Per un offset IL specificato, ottiene gli offset nativi in cui deve essere inserito un punto di interruzione in modo che il debugger possa ottenere il valore restituito da una funzione.</span><span class="sxs-lookup"><span data-stu-id="daa78-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daa78-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="daa78-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="daa78-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="daa78-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daa78-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="daa78-111">Requirements</span></span>  
 <span data-ttu-id="daa78-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daa78-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daa78-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daa78-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daa78-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daa78-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daa78-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daa78-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa78-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daa78-116">See also</span></span>

- [<span data-ttu-id="daa78-117">Interfaccia ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="daa78-117">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="daa78-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="daa78-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
