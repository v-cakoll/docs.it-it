---
title: Interfaccia ICorDebugILFrame4
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="daf84-102">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="daf84-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="daf84-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="daf84-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="daf84-104">Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="daf84-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="daf84-105">L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.</span><span class="sxs-lookup"><span data-stu-id="daf84-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daf84-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="daf84-106">Methods</span></span>  
  
|<span data-ttu-id="daf84-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="daf84-107">Method</span></span>|<span data-ttu-id="daf84-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daf84-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daf84-109">Metodo EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="daf84-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="daf84-110">Restituisce un elenco delle variabili locali disponibili nel frame corrente.</span><span class="sxs-lookup"><span data-stu-id="daf84-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="daf84-111">Metodo GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="daf84-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="daf84-112">Restituisce il codice eseguito da questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="daf84-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="daf84-113">Metodo GetLocalVariableEx</span><span class="sxs-lookup"><span data-stu-id="daf84-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="daf84-114">Restituisce il valore di una variabile locale nel frame del linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="daf84-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daf84-115">Note</span><span class="sxs-lookup"><span data-stu-id="daf84-115">Remarks</span></span>  
 <span data-ttu-id="daf84-116">Questi metodi offrono funzionalità aggiuntive oltre a quelle fornite dal [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), e [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="daf84-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="daf84-117">Ogni metodo include un parametro `flags` che specifica se le variabili locali aggiuntive o il codice definito dalla richiesta ReJIT di un profiler sono visibili.</span><span class="sxs-lookup"><span data-stu-id="daf84-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf84-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="daf84-118">Requirements</span></span>  
 <span data-ttu-id="daf84-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf84-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf84-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="daf84-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daf84-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf84-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf84-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf84-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf84-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf84-123">See Also</span></span>  
 [<span data-ttu-id="daf84-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="daf84-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="daf84-125">Debug</span><span class="sxs-lookup"><span data-stu-id="daf84-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
