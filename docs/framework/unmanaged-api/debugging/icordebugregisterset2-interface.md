---
title: Interfaccia ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f4947a9b6c0e3fd87ee474111f143d273c1d7b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422794"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="02646-102">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="02646-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="02646-103">Estende le funzionalità del [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interfaccia per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="02646-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02646-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="02646-104">Methods</span></span>  
  
|<span data-ttu-id="02646-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="02646-105">Method</span></span>|<span data-ttu-id="02646-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02646-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02646-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="02646-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="02646-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="02646-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="02646-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="02646-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="02646-110">Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="02646-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="02646-111">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="02646-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="02646-112">Non implementato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="02646-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02646-113">Note</span><span class="sxs-lookup"><span data-stu-id="02646-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02646-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="02646-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02646-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02646-115">Requirements</span></span>  
 <span data-ttu-id="02646-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02646-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02646-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="02646-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02646-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="02646-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02646-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02646-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02646-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02646-120">See Also</span></span>  
 [<span data-ttu-id="02646-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="02646-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="02646-122">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="02646-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
