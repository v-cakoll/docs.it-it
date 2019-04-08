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
ms.openlocfilehash: da2759219901a4f49808300ea3b038b10ce2d032
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101172"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="6b45c-102">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="6b45c-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="6b45c-103">Estende le funzionalità dei [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interfaccia per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="6b45c-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b45c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6b45c-104">Methods</span></span>  
  
|<span data-ttu-id="6b45c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6b45c-105">Method</span></span>|<span data-ttu-id="6b45c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b45c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b45c-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="6b45c-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="6b45c-108">Ottiene il valore di ogni registro (nel computer che esegue codice) che viene specificato per la maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="6b45c-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="6b45c-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="6b45c-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="6b45c-110">Ottiene una matrice di byte che fornisce una bitmap di registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="6b45c-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="6b45c-111">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="6b45c-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="6b45c-112">Non è implementata in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="6b45c-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b45c-113">Note</span><span class="sxs-lookup"><span data-stu-id="6b45c-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b45c-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6b45c-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b45c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b45c-115">Requirements</span></span>  
 <span data-ttu-id="6b45c-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b45c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b45c-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b45c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b45c-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b45c-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6b45c-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6b45c-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b45c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b45c-120">See also</span></span>

- [<span data-ttu-id="6b45c-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6b45c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6b45c-122">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="6b45c-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
