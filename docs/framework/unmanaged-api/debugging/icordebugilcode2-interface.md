---
title: Interfaccia ICorDebugILCode2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILCode2
api_location: mscordbi.dll
api_type: COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fd6b7b6b097010a307abbc260cda7c4b73e0f00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="e67e5-102">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="e67e5-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="e67e5-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="e67e5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e67e5-104">Estende logicamente il [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaccia da fornire metodi che restituiscono il token per la firma di variabile locale di una funzione ed eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) che viene eseguito l'offset di linguaggio intermedio del metodo originale viene eseguito l'offset.</span><span class="sxs-lookup"><span data-stu-id="e67e5-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e67e5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e67e5-105">Methods</span></span>  
  
|<span data-ttu-id="e67e5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e67e5-106">Method</span></span>|<span data-ttu-id="e67e5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e67e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e67e5-108">Metodo GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="e67e5-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="e67e5-109">Restituisce una mappa dagli offset IL instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="e67e5-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="e67e5-110">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="e67e5-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="e67e5-111">Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.</span><span class="sxs-lookup"><span data-stu-id="e67e5-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e67e5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e67e5-112">Requirements</span></span>  
 <span data-ttu-id="e67e5-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e67e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67e5-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e67e5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e67e5-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e67e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e67e5-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67e5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e67e5-117">See Also</span></span>  
 [<span data-ttu-id="e67e5-118">Interfaccia ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="e67e5-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [<span data-ttu-id="e67e5-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e67e5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e67e5-120">Debug</span><span class="sxs-lookup"><span data-stu-id="e67e5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
