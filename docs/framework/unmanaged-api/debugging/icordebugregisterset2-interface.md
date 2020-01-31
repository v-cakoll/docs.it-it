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
ms.openlocfilehash: 161358fab9a4601e7b718321273d493bd84a3228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792016"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="97656-102">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="97656-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="97656-103">Estende le funzionalità dell'interfaccia [ICorDebugRegisterSet](icordebugregisterset-interface.md) per le piattaforme hardware con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="97656-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97656-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="97656-104">Methods</span></span>  
  
|<span data-ttu-id="97656-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="97656-105">Method</span></span>|<span data-ttu-id="97656-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97656-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97656-107">Metodo GetRegisters</span><span class="sxs-lookup"><span data-stu-id="97656-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="97656-108">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="97656-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="97656-109">Metodo GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="97656-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="97656-110">Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="97656-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="97656-111">Metodo SetRegisters</span><span class="sxs-lookup"><span data-stu-id="97656-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="97656-112">Non implementato nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="97656-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97656-113">Note</span><span class="sxs-lookup"><span data-stu-id="97656-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97656-114">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="97656-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97656-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="97656-115">Requirements</span></span>  
 <span data-ttu-id="97656-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97656-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97656-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97656-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97656-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97656-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97656-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97656-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97656-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97656-120">See also</span></span>

- [<span data-ttu-id="97656-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="97656-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="97656-122">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="97656-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
