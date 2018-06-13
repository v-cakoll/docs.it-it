---
title: ICorDebugFrame Interface1
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
ms.openlocfilehash: f3d6c1a2bfd66e275b506d4465731c48cd7c6515
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416631"
---
# <a name="icordebugframe-interface1"></a><span data-ttu-id="8861f-102">ICorDebugFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="8861f-102">ICorDebugFrame Interface1</span></span>
<span data-ttu-id="8861f-103">Rappresenta un frame sullo stack corrente.</span><span class="sxs-lookup"><span data-stu-id="8861f-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8861f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8861f-104">Methods</span></span>  
  
|<span data-ttu-id="8861f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8861f-105">Method</span></span>|<span data-ttu-id="8861f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8861f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8861f-107">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="8861f-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="8861f-108">Ottiene un oggetto ICorDebugStepper esegua operazioni di debug passo a passo in base a questa `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8861f-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="8861f-109">Metodo GetCallee</span><span class="sxs-lookup"><span data-stu-id="8861f-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="8861f-110">Ottiene un puntatore per il `ICorDebugFrame` nella catena di chiamata di questo frame oppure restituisce null se si tratta del frame più interno nella catena di corrente.</span><span class="sxs-lookup"><span data-stu-id="8861f-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8861f-111">Metodo GetCaller</span><span class="sxs-lookup"><span data-stu-id="8861f-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="8861f-112">Ottiene un puntatore per il `ICorDebugFrame` nella catena corrente che ha chiamato questo frame o restituisce null se questa è la cornice più esterna della catena.</span><span class="sxs-lookup"><span data-stu-id="8861f-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8861f-113">Metodo GetChain</span><span class="sxs-lookup"><span data-stu-id="8861f-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="8861f-114">Ottiene un puntatore a ICorDebugChain questo `ICorDebugFrame` fa parte di.</span><span class="sxs-lookup"><span data-stu-id="8861f-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="8861f-115">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="8861f-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="8861f-116">Ottiene un puntatore all'oggetto ICorDebugCode associata a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="8861f-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8861f-117">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="8861f-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="8861f-118">Ottiene un puntatore all'oggetto ICorDebugFunction che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="8861f-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8861f-119">Metodo GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="8861f-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="8861f-120">Ottiene il token di metadati per la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="8861f-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8861f-121">Metodo GetStackRange</span><span class="sxs-lookup"><span data-stu-id="8861f-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="8861f-122">Ottiene l'intervallo di indirizzi assoluti dello stack frame rappresentato da questo `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8861f-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8861f-123">Note</span><span class="sxs-lookup"><span data-stu-id="8861f-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8861f-124">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8861f-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8861f-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8861f-125">Requirements</span></span>  
 <span data-ttu-id="8861f-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8861f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8861f-127">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8861f-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8861f-128">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8861f-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8861f-129">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8861f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8861f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8861f-130">See Also</span></span>  
 [<span data-ttu-id="8861f-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8861f-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
