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
ms.openlocfilehash: 3662ed8a3fda5881b0e0929a830d19b0d805299f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411031"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="dee02-102">Metodo ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="dee02-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="dee02-103">Ottiene un gestore di istruzioni che consente al debugger di eseguire operazioni di debug passo a passo ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="dee02-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dee02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dee02-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dee02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dee02-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="dee02-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugStepper che consente al debugger di eseguire operazioni di debug passo a passo relative al frame corrente.</span><span class="sxs-lookup"><span data-stu-id="dee02-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dee02-107">Note</span><span class="sxs-lookup"><span data-stu-id="dee02-107">Remarks</span></span>  
 <span data-ttu-id="dee02-108">Se il frame non è attivo, l'oggetto di gestore di istruzioni in genere dovrà restituire al frame prima che il completamento del passaggio.</span><span class="sxs-lookup"><span data-stu-id="dee02-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dee02-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dee02-109">Requirements</span></span>  
 <span data-ttu-id="dee02-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dee02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dee02-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="dee02-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dee02-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dee02-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dee02-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dee02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
