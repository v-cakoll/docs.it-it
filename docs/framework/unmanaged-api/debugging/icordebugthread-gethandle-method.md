---
title: Metodo ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54981be7104eb04ac6347ad13b61a69f40d4377c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770619"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="26f74-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="26f74-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="26f74-103">Ottiene l'handle corrente per la parte attiva del ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="26f74-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26f74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26f74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26f74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26f74-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="26f74-106">[out] Un puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="26f74-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26f74-107">Note</span><span class="sxs-lookup"><span data-stu-id="26f74-107">Remarks</span></span>  
 <span data-ttu-id="26f74-108">L'handle può cambiare quando viene eseguita, il processo e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="26f74-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="26f74-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="26f74-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="26f74-110">Il debugger deve duplicarla prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="26f74-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26f74-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26f74-111">Requirements</span></span>  
 <span data-ttu-id="26f74-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26f74-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26f74-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26f74-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26f74-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26f74-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26f74-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26f74-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
