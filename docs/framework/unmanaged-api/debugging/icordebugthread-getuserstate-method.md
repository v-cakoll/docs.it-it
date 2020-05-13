---
title: Metodo ICorDebugThread::GetUserState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378851"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="94565-102">Metodo ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="94565-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="94565-103">Ottiene lo stato utente corrente di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="94565-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94565-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94565-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94565-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94565-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="94565-106">out Puntatore a una combinazione bit per bit di valori di Enumerazione CorDebugUserState che descrivono lo stato utente corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="94565-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94565-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="94565-107">Remarks</span></span>  
 <span data-ttu-id="94565-108">Lo stato utente del thread è lo stato del thread quando viene esaminato dal programma di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="94565-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="94565-109">Un thread può avere più bit di stato impostati.</span><span class="sxs-lookup"><span data-stu-id="94565-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94565-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94565-110">Requirements</span></span>  
 <span data-ttu-id="94565-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94565-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94565-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94565-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94565-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94565-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94565-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94565-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
