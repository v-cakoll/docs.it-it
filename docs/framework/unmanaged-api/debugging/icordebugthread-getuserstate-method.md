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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4deaa3ab4b14fbd32d45841966cfac9e33b9f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487850"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="c42e3-102">Metodo ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="c42e3-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="c42e3-103">Ottiene lo stato corrente dell'ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c42e3-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c42e3-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c42e3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c42e3-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="c42e3-106">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugUserState che descrivono lo stato utente corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="c42e3-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c42e3-107">Note</span><span class="sxs-lookup"><span data-stu-id="c42e3-107">Remarks</span></span>  
 <span data-ttu-id="c42e3-108">Lo stato utente del thread è lo stato del thread quando viene esaminato dal programma che viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="c42e3-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="c42e3-109">Un thread può avere più bit di stato impostato.</span><span class="sxs-lookup"><span data-stu-id="c42e3-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c42e3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c42e3-110">Requirements</span></span>  
 <span data-ttu-id="c42e3-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c42e3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c42e3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c42e3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c42e3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c42e3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c42e3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c42e3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
