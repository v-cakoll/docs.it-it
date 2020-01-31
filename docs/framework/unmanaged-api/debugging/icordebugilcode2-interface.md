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
ms.openlocfilehash: 30008d6cc98f7d0d0501d67e18703ed5a344d43a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794370"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="bb140-102">Interfaccia ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="bb140-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="bb140-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="bb140-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bb140-104">Estende logicamente l'interfaccia [ICorDebugILCode](icordebugilcode-interface.md) per fornire i metodi che restituiscono il token per la firma della variabile locale di una funzione e che mappano gli offset del linguaggio intermedio (il) instrumentato del profiler agli offset il di metodo originali.</span><span class="sxs-lookup"><span data-stu-id="bb140-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb140-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb140-105">Methods</span></span>  
  
|<span data-ttu-id="bb140-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb140-106">Method</span></span>|<span data-ttu-id="bb140-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb140-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb140-108">Metodo GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="bb140-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="bb140-109">Restituisce una mappa dagli offset IL instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="bb140-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="bb140-110">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="bb140-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="bb140-111">Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.</span><span class="sxs-lookup"><span data-stu-id="bb140-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb140-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bb140-112">Requirements</span></span>  
 <span data-ttu-id="bb140-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb140-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb140-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb140-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb140-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb140-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb140-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb140-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb140-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb140-117">See also</span></span>

- [<span data-ttu-id="bb140-118">Interfaccia ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="bb140-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="bb140-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb140-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="bb140-120">Debug</span><span class="sxs-lookup"><span data-stu-id="bb140-120">Debugging</span></span>](index.md)
