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
ms.openlocfilehash: 2e6798c2574167ec1a013429b380d8fa6c878dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416563"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="0dfdd-102">Metodo ICorDebugThread2::GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="0dfdd-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="0dfdd-103">Ottiene l'identificatore del thread del sistema operativo per ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="0dfdd-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dfdd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0dfdd-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0dfdd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0dfdd-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="0dfdd-106">[out] L'identificatore del thread del sistema operativo per il thread.</span><span class="sxs-lookup"><span data-stu-id="0dfdd-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dfdd-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0dfdd-107">Requirements</span></span>  
 <span data-ttu-id="0dfdd-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dfdd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dfdd-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0dfdd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dfdd-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0dfdd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dfdd-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dfdd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
