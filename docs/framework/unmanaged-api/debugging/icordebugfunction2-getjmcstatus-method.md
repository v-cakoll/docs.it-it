---
title: Metodo ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137812"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="63e54-102">Metodo ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="63e54-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="63e54-103">Ottiene un valore che indica se la funzione rappresentata da questo oggetto ICorDebugFunction2 è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="63e54-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63e54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63e54-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63e54-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="63e54-106">out Puntatore a un valore booleano `true`, se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false`.</span><span class="sxs-lookup"><span data-stu-id="63e54-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63e54-107">Note</span><span class="sxs-lookup"><span data-stu-id="63e54-107">Remarks</span></span>  
 <span data-ttu-id="63e54-108">Se non è possibile eseguire il debug della funzione rappresentata da questo `ICorDebugFunction2`, `pbIsJustMyCode` sarà sempre `false`.</span><span class="sxs-lookup"><span data-stu-id="63e54-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63e54-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63e54-109">Requirements</span></span>  
 <span data-ttu-id="63e54-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63e54-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63e54-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63e54-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63e54-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63e54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63e54-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63e54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
