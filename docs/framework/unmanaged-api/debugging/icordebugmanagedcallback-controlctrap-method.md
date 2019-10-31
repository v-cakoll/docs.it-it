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
ms.openlocfilehash: da35db8a943fda5fb3fbf4126684bb9cb7243001
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137422"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="7d569-102">Metodo ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="7d569-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="7d569-103">Notifica al debugger che la combinazione di tasti CTRL + C è intrappolata nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="7d569-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d569-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d569-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d569-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d569-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7d569-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui viene intercettata la combinazione di tasti CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="7d569-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d569-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7d569-107">Return Value</span></span>  
  
|<span data-ttu-id="7d569-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d569-108">HRESULT</span></span>|<span data-ttu-id="7d569-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d569-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d569-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d569-110">S_OK</span></span>|<span data-ttu-id="7d569-111">Il debugger gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="7d569-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="7d569-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7d569-112">S_FALSE</span></span>|<span data-ttu-id="7d569-113">Il debugger non gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="7d569-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d569-114">Note</span><span class="sxs-lookup"><span data-stu-id="7d569-114">Remarks</span></span>  
 <span data-ttu-id="7d569-115">Tutti i domini applicazione all'interno del processo vengono arrestati per questo callback.</span><span class="sxs-lookup"><span data-stu-id="7d569-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d569-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d569-116">Requirements</span></span>  
 <span data-ttu-id="7d569-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d569-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d569-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d569-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d569-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d569-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d569-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d569-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d569-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d569-121">See also</span></span>

- [<span data-ttu-id="7d569-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7d569-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
