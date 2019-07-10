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
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771797"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="62dab-102">Metodo ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="62dab-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="62dab-103">Crea un oggetto ICorDebugStepper che consente l'esecuzione di istruzioni tramite il frame attivo di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="62dab-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62dab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62dab-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62dab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62dab-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="62dab-106">[out] Un puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione di istruzioni tramite il frame attivo del thread.</span><span class="sxs-lookup"><span data-stu-id="62dab-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62dab-107">Note</span><span class="sxs-lookup"><span data-stu-id="62dab-107">Remarks</span></span>  
 <span data-ttu-id="62dab-108">Il frame attivo potrebbe contenere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="62dab-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="62dab-109">Il `ICorDebugStepper` interfaccia deve essere usata per eseguire l'effettiva esecuzione delle istruzioni.</span><span class="sxs-lookup"><span data-stu-id="62dab-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62dab-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62dab-110">Requirements</span></span>  
 <span data-ttu-id="62dab-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62dab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62dab-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62dab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62dab-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62dab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62dab-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62dab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
