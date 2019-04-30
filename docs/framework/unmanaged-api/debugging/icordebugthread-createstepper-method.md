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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987188"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="03232-102">Metodo ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="03232-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="03232-103">Crea un oggetto ICorDebugStepper che consente l'esecuzione di istruzioni tramite il frame attivo di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="03232-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03232-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03232-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03232-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03232-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="03232-106">[out] Un puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione di istruzioni tramite il frame attivo del thread.</span><span class="sxs-lookup"><span data-stu-id="03232-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03232-107">Note</span><span class="sxs-lookup"><span data-stu-id="03232-107">Remarks</span></span>  
 <span data-ttu-id="03232-108">Il frame attivo potrebbe contenere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="03232-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="03232-109">Il `ICorDebugStepper` interfaccia deve essere usata per eseguire l'effettiva esecuzione delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="03232-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03232-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03232-110">Requirements</span></span>  
 <span data-ttu-id="03232-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03232-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03232-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03232-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03232-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03232-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03232-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03232-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
