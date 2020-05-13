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
ms.openlocfilehash: d01936481ec139757566d5b96cb95ea887cb8c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378061"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="1e0bf-102">Metodo ICorDebugThread::GetID</span><span class="sxs-lookup"><span data-stu-id="1e0bf-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="1e0bf-103">Ottiene l'identificatore del sistema operativo corrente della parte attiva di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="1e0bf-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e0bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e0bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e0bf-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="1e0bf-106">out Identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="1e0bf-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e0bf-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1e0bf-107">Remarks</span></span>  
 <span data-ttu-id="1e0bf-108">L'identificatore del sistema operativo può essere modificato durante l'esecuzione di un processo e può essere un valore diverso per diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="1e0bf-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e0bf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e0bf-109">Requirements</span></span>  
 <span data-ttu-id="1e0bf-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e0bf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e0bf-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e0bf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e0bf-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e0bf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e0bf-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e0bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
