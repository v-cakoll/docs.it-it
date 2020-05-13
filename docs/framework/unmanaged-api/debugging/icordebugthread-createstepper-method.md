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
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379713"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="79bac-102">Metodo ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="79bac-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="79bac-103">Crea un oggetto ICorDebugStepper che consente l'esecuzione di un'istruzione alla volta nel frame attivo di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="79bac-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79bac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79bac-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79bac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79bac-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="79bac-106">out Puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione di un'istruzione alla volta nel frame attivo del thread.</span><span class="sxs-lookup"><span data-stu-id="79bac-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79bac-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="79bac-107">Remarks</span></span>  
 <span data-ttu-id="79bac-108">Il frame attivo può essere codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="79bac-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="79bac-109">`ICorDebugStepper`È necessario utilizzare l'interfaccia per eseguire l'esecuzione dell'istruzione effettiva.</span><span class="sxs-lookup"><span data-stu-id="79bac-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79bac-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79bac-110">Requirements</span></span>  
 <span data-ttu-id="79bac-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79bac-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79bac-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79bac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79bac-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79bac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79bac-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79bac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
