---
title: Metodo ICorDebugThread2::GetVolatileOSThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9bf96371798b38bc392bc6bbd8f6fe8f97c7969
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501968"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="a54dd-102">Metodo ICorDebugThread2::GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="a54dd-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="a54dd-103">Ottiene l'identificatore del thread del sistema operativo per ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="a54dd-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a54dd-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a54dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a54dd-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="a54dd-106">[out] L'identificatore del thread del sistema operativo per questo thread.</span><span class="sxs-lookup"><span data-stu-id="a54dd-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a54dd-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a54dd-107">Requirements</span></span>  
 <span data-ttu-id="a54dd-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a54dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a54dd-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a54dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a54dd-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a54dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a54dd-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a54dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
