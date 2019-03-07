---
title: Metodo ICorDebugProcess::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5d81564a34ed8e7ef75840e3a174661c36f5411
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498086"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="2ccdf-102">Metodo ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="2ccdf-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="2ccdf-103">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="2ccdf-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ccdf-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ccdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ccdf-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="2ccdf-106">[out] Un puntatore a un `HPROCESS` che rappresenta l'handle del processo.</span><span class="sxs-lookup"><span data-stu-id="2ccdf-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ccdf-107">Note</span><span class="sxs-lookup"><span data-stu-id="2ccdf-107">Remarks</span></span>  
 <span data-ttu-id="2ccdf-108">L'handle recuperato è di proprietà dell'interfaccia di debug.</span><span class="sxs-lookup"><span data-stu-id="2ccdf-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="2ccdf-109">Il debugger deve duplicazione dell'handle prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="2ccdf-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ccdf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ccdf-110">Requirements</span></span>  
 <span data-ttu-id="2ccdf-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ccdf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccdf-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ccdf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ccdf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ccdf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ccdf-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccdf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
