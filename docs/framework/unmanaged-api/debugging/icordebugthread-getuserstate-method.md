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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987072"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="8f72c-102">Metodo ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="8f72c-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="8f72c-103">Ottiene lo stato corrente dell'ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8f72c-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f72c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f72c-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f72c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f72c-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8f72c-106">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugUserState che descrivono lo stato utente corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="8f72c-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f72c-107">Note</span><span class="sxs-lookup"><span data-stu-id="8f72c-107">Remarks</span></span>  
 <span data-ttu-id="8f72c-108">Lo stato utente del thread è lo stato del thread quando viene esaminato dal programma che viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="8f72c-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="8f72c-109">Un thread può avere più bit di stato impostato.</span><span class="sxs-lookup"><span data-stu-id="8f72c-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f72c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f72c-110">Requirements</span></span>  
 <span data-ttu-id="8f72c-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f72c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f72c-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f72c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f72c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f72c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f72c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f72c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
