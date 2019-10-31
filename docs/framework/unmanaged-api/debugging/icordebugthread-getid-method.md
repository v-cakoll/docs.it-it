---
title: Metodo ICorDebugThread::GetID
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: 48d2af96b50bf77347256b3d5860405e460a09d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133444"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="bfbfa-102">Metodo ICorDebugThread::GetID</span><span class="sxs-lookup"><span data-stu-id="bfbfa-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="bfbfa-103">Ottiene l'identificatore del sistema operativo corrente della parte attiva di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="bfbfa-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfbfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfbfa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfbfa-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="bfbfa-106">out Identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="bfbfa-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfbfa-107">Note</span><span class="sxs-lookup"><span data-stu-id="bfbfa-107">Remarks</span></span>  
 <span data-ttu-id="bfbfa-108">L'identificatore del sistema operativo può essere modificato durante l'esecuzione di un processo e può essere un valore diverso per diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="bfbfa-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfbfa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfbfa-109">Requirements</span></span>  
 <span data-ttu-id="bfbfa-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfbfa-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfbfa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfbfa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfbfa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfbfa-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
