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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95d9696e29bc1b460c94d7f4d8afd3de82653333
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419630"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="34f79-102">Metodo ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="34f79-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="34f79-103">Ottiene lo stato di debug corrente di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="34f79-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34f79-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34f79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34f79-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="34f79-106">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugThreadState che descrive lo stato di debug corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="34f79-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34f79-107">Note</span><span class="sxs-lookup"><span data-stu-id="34f79-107">Remarks</span></span>  
 <span data-ttu-id="34f79-108">Se il processo è inattivo, `pState` rappresenta lo stato di debug che avrebbe questo thread se il processo continua, non l'effettivo stato corrente di questo thread.</span><span class="sxs-lookup"><span data-stu-id="34f79-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f79-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34f79-109">Requirements</span></span>  
 <span data-ttu-id="34f79-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f79-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="34f79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f79-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="34f79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f79-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
