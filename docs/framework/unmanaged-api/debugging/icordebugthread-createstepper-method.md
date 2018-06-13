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
ms.openlocfilehash: 626f313c41c85e08901648f429d99c829ba35e2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419000"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="5ac2e-102">Metodo ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="5ac2e-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="5ac2e-103">Crea un oggetto ICorDebugStepper che consente l'esecuzione passo passo del frame attivo di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5ac2e-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ac2e-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ac2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5ac2e-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="5ac2e-106">[out] Un puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione passo passo del frame attivo del thread.</span><span class="sxs-lookup"><span data-stu-id="5ac2e-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ac2e-107">Note</span><span class="sxs-lookup"><span data-stu-id="5ac2e-107">Remarks</span></span>  
 <span data-ttu-id="5ac2e-108">Il frame attivo potrebbe contenere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="5ac2e-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="5ac2e-109">Il `ICorDebugStepper` interfaccia deve essere utilizzata per eseguire il debug passo effettivo.</span><span class="sxs-lookup"><span data-stu-id="5ac2e-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ac2e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ac2e-110">Requirements</span></span>  
 <span data-ttu-id="5ac2e-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ac2e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ac2e-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5ac2e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ac2e-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5ac2e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ac2e-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ac2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
