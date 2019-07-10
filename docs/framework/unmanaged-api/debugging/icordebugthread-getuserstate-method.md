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
ms.openlocfilehash: f7d3325c8aee44849ff1fb7a6cc06a0ed7c2c6f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769098"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="bcc99-102">Metodo ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="bcc99-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="bcc99-103">Ottiene lo stato corrente dell'ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="bcc99-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcc99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcc99-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcc99-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="bcc99-106">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugUserState che descrivono lo stato utente corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="bcc99-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcc99-107">Note</span><span class="sxs-lookup"><span data-stu-id="bcc99-107">Remarks</span></span>  
 <span data-ttu-id="bcc99-108">Lo stato utente del thread è lo stato del thread quando viene esaminato dal programma che viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="bcc99-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="bcc99-109">Un thread può avere più bit di stato impostato.</span><span class="sxs-lookup"><span data-stu-id="bcc99-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc99-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcc99-110">Requirements</span></span>  
 <span data-ttu-id="bcc99-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcc99-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcc99-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcc99-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcc99-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcc99-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcc99-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcc99-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
