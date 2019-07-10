---
title: Metodo ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd105a5cbdb857aaa902e60968ff1d94473259b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754236"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="568a9-102">Metodo ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="568a9-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="568a9-103">Ottiene un gestore di istruzioni che consente al debugger di eseguire operazioni di debug passo a passo ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="568a9-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="568a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="568a9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="568a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="568a9-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="568a9-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugStepper che consente al debugger di eseguire operazioni di debug passo a passo rispetto al frame corrente.</span><span class="sxs-lookup"><span data-stu-id="568a9-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="568a9-107">Note</span><span class="sxs-lookup"><span data-stu-id="568a9-107">Remarks</span></span>  
 <span data-ttu-id="568a9-108">Se il frame non è attivo, l'oggetto gestore di istruzioni in genere deve restituire al frame prima che venga completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="568a9-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="568a9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="568a9-109">Requirements</span></span>  
 <span data-ttu-id="568a9-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="568a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="568a9-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="568a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="568a9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="568a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="568a9-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="568a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
