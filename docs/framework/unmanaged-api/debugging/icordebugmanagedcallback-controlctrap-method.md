---
title: Metodo ICorDebugManagedCallback::ControlCTrap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4794fb0383435f828626497036ad3458df2173
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204991"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="660ca-102">Metodo ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="660ca-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="660ca-103">Notifica al debugger che CTRL + C viene intercettata nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="660ca-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="660ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="660ca-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="660ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="660ca-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="660ca-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui viene intercettata CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="660ca-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="660ca-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="660ca-107">Return Value</span></span>  
  
|<span data-ttu-id="660ca-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="660ca-108">HRESULT</span></span>|<span data-ttu-id="660ca-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="660ca-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="660ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="660ca-110">S_OK</span></span>|<span data-ttu-id="660ca-111">Il debugger gestirà le trap di CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="660ca-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="660ca-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="660ca-112">S_FALSE</span></span>|<span data-ttu-id="660ca-113">Il debugger non gestirà il trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="660ca-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="660ca-114">Note</span><span class="sxs-lookup"><span data-stu-id="660ca-114">Remarks</span></span>  
 <span data-ttu-id="660ca-115">Per questo callback vengono arrestati tutti i domini applicazione all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="660ca-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="660ca-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="660ca-116">Requirements</span></span>  
 <span data-ttu-id="660ca-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="660ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="660ca-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="660ca-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="660ca-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="660ca-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="660ca-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="660ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="660ca-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="660ca-121">See also</span></span>

- [<span data-ttu-id="660ca-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="660ca-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
