---
title: ICorDebugFrame Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame
helpviewer_keywords: ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2acc825f6592eae80f67e7614ca45f175b6756d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframe-interface1"></a><span data-ttu-id="b2ce5-102">ICorDebugFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="b2ce5-102">ICorDebugFrame Interface1</span></span>
<span data-ttu-id="b2ce5-103">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2ce5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b2ce5-104">Methods</span></span>  
  
|<span data-ttu-id="b2ce5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b2ce5-105">Method</span></span>|<span data-ttu-id="b2ce5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2ce5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2ce5-107">CreateStepper (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="b2ce5-108">Ottiene un oggetto ICorDebugStepper esegua operazioni di debug passo a passo in base a questa `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="b2ce5-109">GetCallee (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="b2ce5-110">Ottiene un puntatore per il `ICorDebugFrame` nella catena di chiamata di questo frame oppure restituisce null se si tratta del frame più interno nella catena di corrente.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="b2ce5-111">GetCaller (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="b2ce5-112">Ottiene un puntatore per il `ICorDebugFrame` nella catena corrente che ha chiamato questo frame o restituisce null se questa è la cornice più esterna della catena.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="b2ce5-113">GetChain (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="b2ce5-114">Ottiene un puntatore a ICorDebugChain questo `ICorDebugFrame` fa parte di.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="b2ce5-115">GetCode (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="b2ce5-116">Ottiene un puntatore all'oggetto ICorDebugCode associata a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b2ce5-117">GetFunction (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="b2ce5-118">Ottiene un puntatore all'oggetto ICorDebugFunction che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b2ce5-119">GetFunctionToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="b2ce5-120">Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b2ce5-121">GetStackRange (metodo)</span><span class="sxs-lookup"><span data-stu-id="b2ce5-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="b2ce5-122">Ottiene l'intervallo di indirizzi assoluti dello stack frame rappresentato da questo `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2ce5-123">Note</span><span class="sxs-lookup"><span data-stu-id="b2ce5-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2ce5-124">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b2ce5-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2ce5-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2ce5-125">Requirements</span></span>  
 <span data-ttu-id="b2ce5-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2ce5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ce5-127">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b2ce5-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2ce5-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2ce5-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2ce5-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ce5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ce5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2ce5-130">See Also</span></span>  
 [<span data-ttu-id="b2ce5-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b2ce5-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
