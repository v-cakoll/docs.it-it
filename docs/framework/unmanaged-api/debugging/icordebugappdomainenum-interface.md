---
title: Interfaccia ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48c222a34e2e78f29c33e49da331d97d409bae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949753"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="93d0b-102">Interfaccia ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="93d0b-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="93d0b-103">Fornisce il `Next` metodo, che restituisce un numero specificato di `ICorDebugAppDomainEnum` valori a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="93d0b-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="93d0b-104">Questa interfaccia è una sottoclasse di "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="93d0b-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93d0b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="93d0b-105">Methods</span></span>  
  
|<span data-ttu-id="93d0b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="93d0b-106">Method</span></span>|<span data-ttu-id="93d0b-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="93d0b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93d0b-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="93d0b-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="93d0b-109">Ottiene il numero specificato di domini applicazione dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="93d0b-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93d0b-110">Note</span><span class="sxs-lookup"><span data-stu-id="93d0b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93d0b-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="93d0b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93d0b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93d0b-112">Requirements</span></span>  
 <span data-ttu-id="93d0b-113">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93d0b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93d0b-114">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="93d0b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93d0b-115">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93d0b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93d0b-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93d0b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d0b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93d0b-117">See also</span></span>

- [<span data-ttu-id="93d0b-118">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="93d0b-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="93d0b-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="93d0b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
