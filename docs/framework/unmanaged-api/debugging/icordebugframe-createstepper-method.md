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
ms.openlocfilehash: 3fe3cbc4bad83496bcc58aaea60e6724b1d1f06c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988897"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="6533d-102">Metodo ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="6533d-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="6533d-103">Ottiene un gestore di istruzioni che consente al debugger di eseguire operazioni di debug passo a passo ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="6533d-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6533d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6533d-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6533d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6533d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="6533d-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugStepper che consente al debugger di eseguire operazioni di debug passo a passo rispetto al frame corrente.</span><span class="sxs-lookup"><span data-stu-id="6533d-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6533d-107">Note</span><span class="sxs-lookup"><span data-stu-id="6533d-107">Remarks</span></span>  
 <span data-ttu-id="6533d-108">Se il frame non è attivo, l'oggetto gestore di istruzioni in genere deve restituire al frame prima che venga completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="6533d-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6533d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6533d-109">Requirements</span></span>  
 <span data-ttu-id="6533d-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6533d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6533d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6533d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6533d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6533d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6533d-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6533d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
