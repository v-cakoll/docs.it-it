---
title: Metodo ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89182739633984011aaab3d7900d376b6db5ef99
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476204"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="ae96d-102">Metodo ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="ae96d-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="ae96d-103">Crea un oggetto ICorDebugStepper che consente l'esecuzione di istruzioni tramite il frame attivo di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="ae96d-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae96d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae96d-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae96d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae96d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="ae96d-106">[out] Un puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione di istruzioni tramite il frame attivo del thread.</span><span class="sxs-lookup"><span data-stu-id="ae96d-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae96d-107">Note</span><span class="sxs-lookup"><span data-stu-id="ae96d-107">Remarks</span></span>  
 <span data-ttu-id="ae96d-108">Il frame attivo potrebbe contenere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="ae96d-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="ae96d-109">Il `ICorDebugStepper` interfaccia deve essere usata per eseguire l'effettiva esecuzione delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ae96d-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae96d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae96d-110">Requirements</span></span>  
 <span data-ttu-id="ae96d-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae96d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae96d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae96d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae96d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae96d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae96d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae96d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
