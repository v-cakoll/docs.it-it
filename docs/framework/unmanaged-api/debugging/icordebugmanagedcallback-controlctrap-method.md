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
ms.openlocfilehash: 63f7bf8c09480b9ce2cfb8eb8dc66e4a6133ef8f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777479"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="c5f69-102">Metodo ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="c5f69-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="c5f69-103">Notifica al debugger che la combinazione di tasti CTRL + C è intrappolata nel processo di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="c5f69-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5f69-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5f69-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5f69-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c5f69-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui viene intercettata la combinazione di tasti CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="c5f69-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5f69-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c5f69-107">Return Value</span></span>  
  
|<span data-ttu-id="c5f69-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5f69-108">HRESULT</span></span>|<span data-ttu-id="c5f69-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5f69-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5f69-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5f69-110">S_OK</span></span>|<span data-ttu-id="c5f69-111">Il debugger gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="c5f69-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="c5f69-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c5f69-112">S_FALSE</span></span>|<span data-ttu-id="c5f69-113">Il debugger non gestirà la trap CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="c5f69-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f69-114">Note</span><span class="sxs-lookup"><span data-stu-id="c5f69-114">Remarks</span></span>  
 <span data-ttu-id="c5f69-115">Tutti i domini applicazione all'interno del processo vengono arrestati per questo callback.</span><span class="sxs-lookup"><span data-stu-id="c5f69-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f69-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c5f69-116">Requirements</span></span>  
 <span data-ttu-id="c5f69-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5f69-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f69-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5f69-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5f69-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5f69-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5f69-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f69-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f69-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5f69-121">See also</span></span>

- [<span data-ttu-id="c5f69-122">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c5f69-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
