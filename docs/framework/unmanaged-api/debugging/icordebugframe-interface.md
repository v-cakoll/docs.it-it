---
title: Interfaccia ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222568"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="724dd-102">Interfaccia ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="724dd-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="724dd-103">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="724dd-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="724dd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="724dd-104">Methods</span></span>  
  
|<span data-ttu-id="724dd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="724dd-105">Method</span></span>|<span data-ttu-id="724dd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="724dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="724dd-107">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="724dd-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="724dd-108">Ottiene un oggetto ICorDebugStepper per eseguire operazioni di debug passo a passo in base a questa `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="724dd-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="724dd-109">Metodo GetCallee</span><span class="sxs-lookup"><span data-stu-id="724dd-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="724dd-110">Ottiene un puntatore per il `ICorDebugFrame` nella catena di corrente che questo frame chiamato, o restituisce null se questo è il frame più interno nella catena.</span><span class="sxs-lookup"><span data-stu-id="724dd-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="724dd-111">Metodo GetCaller</span><span class="sxs-lookup"><span data-stu-id="724dd-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="724dd-112">Ottiene un puntatore per il `ICorDebugFrame` nella catena di corrente che ha chiamato questo frame, o restituisce null se questo è il frame più esterno della catena.</span><span class="sxs-lookup"><span data-stu-id="724dd-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="724dd-113">Metodo GetChain</span><span class="sxs-lookup"><span data-stu-id="724dd-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="724dd-114">Ottiene un puntatore a ICorDebugChain si `ICorDebugFrame` fa parte di.</span><span class="sxs-lookup"><span data-stu-id="724dd-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="724dd-115">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="724dd-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="724dd-116">Ottiene un puntatore all'oggetto ICorDebugCode associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="724dd-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="724dd-117">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="724dd-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="724dd-118">Ottiene un puntatore alla funzione ICorDebugFunction che contiene il codice associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="724dd-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="724dd-119">Metodo GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="724dd-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="724dd-120">Ottiene il token di metadati per la funzione che contiene il codice associato a questo frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="724dd-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="724dd-121">Metodo GetStackRange</span><span class="sxs-lookup"><span data-stu-id="724dd-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="724dd-122">Ottiene l'intervallo di indirizzi assoluti dello stack frame rappresentato da questo `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="724dd-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="724dd-123">Note</span><span class="sxs-lookup"><span data-stu-id="724dd-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="724dd-124">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="724dd-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724dd-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="724dd-125">Requirements</span></span>  
 <span data-ttu-id="724dd-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="724dd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724dd-127">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="724dd-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="724dd-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="724dd-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="724dd-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="724dd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724dd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="724dd-130">See also</span></span>

- [<span data-ttu-id="724dd-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="724dd-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
