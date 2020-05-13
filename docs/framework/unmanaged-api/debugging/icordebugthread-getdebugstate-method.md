---
title: Metodo ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 13125f60f596cb8a80d9c42c51a979f632de494b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379750"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="a5862-102">Metodo ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="a5862-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="a5862-103">Ottiene lo stato di debug corrente di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a5862-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5862-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5862-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5862-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5862-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="a5862-106">out Puntatore a una combinazione bit per bit di valori di enumerazione CorDebugThreadState che descrive lo stato di debug corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="a5862-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5862-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a5862-107">Remarks</span></span>  
 <span data-ttu-id="a5862-108">Se il processo è attualmente arrestato, `pState` rappresenta lo stato di debug esistente per il thread se il processo deve essere continuato, non lo stato corrente effettivo di questo thread.</span><span class="sxs-lookup"><span data-stu-id="a5862-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5862-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5862-109">Requirements</span></span>  
 <span data-ttu-id="a5862-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5862-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5862-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5862-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5862-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5862-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5862-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5862-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
