---
title: Interfaccia ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27dbd8b5013937bb97f37113687405c988c1fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142662"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="be06f-102">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="be06f-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="be06f-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="be06f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="be06f-104">Estende logicamente il [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaccia per fornire i metodi che restituiscono il token di firma della variabile locale di una funzione e che eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) agli offset linguaggio intermedio del metodo originale viene eseguito l'offset.</span><span class="sxs-lookup"><span data-stu-id="be06f-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be06f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="be06f-105">Methods</span></span>  
  
|<span data-ttu-id="be06f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="be06f-106">Method</span></span>|<span data-ttu-id="be06f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be06f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be06f-108">Metodo GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="be06f-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="be06f-109">Restituisce una mappa dagli offset IL instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="be06f-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="be06f-110">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="be06f-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="be06f-111">Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.</span><span class="sxs-lookup"><span data-stu-id="be06f-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be06f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be06f-112">Requirements</span></span>  
 <span data-ttu-id="be06f-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be06f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be06f-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be06f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be06f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be06f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="be06f-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="be06f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be06f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be06f-117">See also</span></span>

- [<span data-ttu-id="be06f-118">Interfaccia ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="be06f-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="be06f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="be06f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="be06f-120">Debug</span><span class="sxs-lookup"><span data-stu-id="be06f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
