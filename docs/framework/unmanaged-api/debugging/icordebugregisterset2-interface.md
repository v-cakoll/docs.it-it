---
title: Interfaccia ICorDebugRegisterSet2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2
helpviewer_keywords: ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26967f50ded62f935a705c25eed58314b77bedd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="809ac-102">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="809ac-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="809ac-103">Estende le funzionalità del [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interfaccia per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="809ac-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="809ac-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="809ac-104">Methods</span></span>  
  
|<span data-ttu-id="809ac-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="809ac-105">Method</span></span>|<span data-ttu-id="809ac-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="809ac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="809ac-107">GetRegisters (metodo)</span><span class="sxs-lookup"><span data-stu-id="809ac-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="809ac-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="809ac-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="809ac-109">GetRegistersAvailable (metodo)</span><span class="sxs-lookup"><span data-stu-id="809ac-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="809ac-110">Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="809ac-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="809ac-111">SetRegisters (metodo)</span><span class="sxs-lookup"><span data-stu-id="809ac-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="809ac-112">Non implementato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="809ac-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="809ac-113">Note</span><span class="sxs-lookup"><span data-stu-id="809ac-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="809ac-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="809ac-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809ac-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="809ac-115">Requirements</span></span>  
 <span data-ttu-id="809ac-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="809ac-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="809ac-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="809ac-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="809ac-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="809ac-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="809ac-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="809ac-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809ac-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="809ac-120">See Also</span></span>  
 [<span data-ttu-id="809ac-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="809ac-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="809ac-122">ICorDebugRegisterSet (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="809ac-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
