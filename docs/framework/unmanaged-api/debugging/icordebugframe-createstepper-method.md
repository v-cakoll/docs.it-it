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
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205455"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="fdacf-102">Metodo ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="fdacf-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="fdacf-103">Ottiene un oggetto stepper che consente al debugger di eseguire operazioni di esecuzione dei progressi rispetto a questo ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="fdacf-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdacf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdacf-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdacf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fdacf-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="fdacf-106">out Puntatore all'indirizzo di un oggetto ICorDebugStepper che consente al debugger di eseguire operazioni di esecuzione dei progressi rispetto al frame corrente.</span><span class="sxs-lookup"><span data-stu-id="fdacf-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdacf-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fdacf-107">Remarks</span></span>  
 <span data-ttu-id="fdacf-108">Se il frame non è attivo, l'oggetto stepper dovrà in genere tornare al frame prima del completamento del passaggio.</span><span class="sxs-lookup"><span data-stu-id="fdacf-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdacf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdacf-109">Requirements</span></span>  
 <span data-ttu-id="fdacf-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdacf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdacf-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdacf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdacf-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdacf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdacf-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdacf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
