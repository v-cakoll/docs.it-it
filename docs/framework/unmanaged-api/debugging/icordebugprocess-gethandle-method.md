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
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128877"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="a1276-102">Metodo ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="a1276-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="a1276-103">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="a1276-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1276-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1276-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1276-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1276-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="a1276-106">out Puntatore a un `HPROCESS` che rappresenta l'handle del processo.</span><span class="sxs-lookup"><span data-stu-id="a1276-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1276-107">Note</span><span class="sxs-lookup"><span data-stu-id="a1276-107">Remarks</span></span>  
 <span data-ttu-id="a1276-108">L'handle recuperato è di proprietà dell'interfaccia di debug.</span><span class="sxs-lookup"><span data-stu-id="a1276-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="a1276-109">Il debugger deve duplicare l'handle prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="a1276-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1276-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1276-110">Requirements</span></span>  
 <span data-ttu-id="a1276-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1276-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1276-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1276-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1276-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1276-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1276-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1276-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
